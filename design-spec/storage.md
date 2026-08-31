# Design spec — Storage

## What this part is

The NVMe drives. Two of them, deliberately split, so an OS reinstall costs you nothing.

## Hard compatibility constraints

- **M.2 2280 NVMe.** The board has 4 slots: M2_1 Gen5 x4 (CPU), M2_2 Gen5 x4 (CPU),
  M2_3 Gen4 **x2**, M2_4 Gen4 x4
- **Populating M2_3 drops the PCI_E3 expansion slot from x4 to x2.** Fill M2_1, M2_2 and
  M2_4 before M2_3
- 4 SATA ports exist but are not used for primaries

## Currently aimed-for spec

| Drive | Role | Size | Interface | Slot |
|---|---|---|---|---|
| Boot | OS, general use | **1 TB** | Gen4 **with onboard DRAM** | M2_1 |
| Data | Development + games | **2 TB** | Gen4 **with onboard DRAM** | M2_2 |

Target parts: **WD SN850X** or **Samsung 990 Pro**. Both have onboard DRAM.

## Why Gen4-with-DRAM beats Gen5-without

This reverses the original dream build, which specified two DRAM-less Gen5 Crucial P510s.

The actual disk workload here is **many small random writes**, not big sequential reads:
- Android emulator `.qcow2` sparse images growing by random write (~30 GB across 4 AVDs today)
- Gradle's thousands of small files; `build/` and `.dart_tool/` churn on every agentic rebuild
- Once the analysis server and Gradle daemon are warm they are RAM-resident and barely touch disk

That pattern is **latency and DRAM-cache bound**. A Gen4 drive with onboard DRAM handles it
better than a DRAM-less Gen5 drive despite the slower bus. Endurance (TBW) also favours the
DRAM drives, and the agentic rebuild loop generates real write volume over five years.

The Gen5 sequential speed buys nothing that either compiles or CPU inference use. Skipping
it saves ~$200–250.

## Capacity reasoning

Measured footprint on the current machine: **~35–45 GB total** — emulators ~30 GB, Flutter
cache 1.8 GB, Gradle several GB, coursework 717 MB, HuggingFace cache 346 MB.

- **1 TB boot is generous**, deliberately. It is not the pressure point.
- **2 TB data is where the capacity belongs** — it will be consumed mostly by games
  (300–500 GB with 2–4 resident), not development.
- **Open question:** the Steam library size is unmeasured and is the single biggest driver
  of drive-two capacity. If it is large, go 4 TB instead.
- **Future:** a handful of 70B-class quantised models is 150–250 GB. Not needed yet — the
  AI footprint today is one 346 MB vision transformer — but it arrives fast when it arrives.

## The organizational split — solved, see `storage-layout.md`

**Written up in full in `storage-layout.md`.** The short version: on Linux every toolchain
cache already lives under `$HOME`, so putting `/home` on drive two solves the whole problem
in one line of fstab. None of the Windows plan's eight environment-variable redirects are
needed — that complexity was a Windows problem.

Drive 1 → `/`, `/boot`, `/var`. Drive 2 → `/home`, plus `~/vms` for the Windows VM image
(libvirt defaults to `/var/lib/libvirt/images` on drive 1; move it).

Use slots **M2_1 and M2_2**. Avoid M2_3 — it drops the PCI_E3 expansion slot to x2, and that
slot is reserved for an Intel NIC if the Realtek 5GbE misbehaves on Linux.

## Market warning

NAND is in the same AI-driven shortage as DDR5. A 1 TB 990 Pro that bottomed at $59 is $239
today; 2 TB Gen4 is ~$299 against a $93 floor. **Black Friday will discount a percentage off
an inflated price — it will not undo a shortage.**

If the budget needs cutting, the 2 TB data drive is the right thing to defer: partition the
1 TB as a stopgap and buy drive two when NAND normalizes or it breaks $250.
