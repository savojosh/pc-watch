# Design spec — Motherboard

**Status: LOCKED. This is the anchor part; everything else is chosen to fit it.**

## What this part is

The board every other component plugs into. It fixes the CPU socket, the memory
generation, how many drives you can attach, and how many expansion cards fit. Choosing it
first is what makes the rest of the build a compatibility problem instead of a guess.

## The pick

**MSI MAG B850 Tomahawk MAX WiFi — $229.99 (Newegg, 2026-08-31)**

> Buy the plain **MAX WiFi**, not the **MAX WiFi II** ($259.99). Confirm the exact SKU
> string before purchase — MSI's naming is close enough to mis-order.

## Locked specifications

| Field | Value |
|---|---|
| Socket | AM5 (LGA1718) |
| Chipset | AMD B850 |
| Form factor | ATX |
| Memory | 4 × DDR5 DIMM, 256 GB max, non-ECC UDIMM, EXPO |
| M.2 | 4 slots — M2_1 Gen5 x4 (CPU), M2_2 Gen5 x4 (CPU), M2_3 Gen4 **x2**, M2_4 Gen4 x4 |
| SATA | 4 × SATA 6 Gb/s |
| Primary GPU slot | PCIe 5.0 x16, CPU-attached, **never lane-shared** |
| Secondary slot | **PCI_E3 — full-length, PCIe 4.0 x4** (+ one PCIe 3.0 x1) |
| VRM | 14 × 80 A SPS Vcore (17 phase total, ~1120 A) |
| LAN | 5GbE Realtek RTL8126 |
| WiFi | Wi-Fi 7, Bluetooth 5.4 |
| USB4 | **No** |

## Why this board and not the others

Four boards were compared in full. The deciding question was: *after a GPU is installed,
can I still add an expansion card while running multiple NVMe drives?*

| Board | Price | The problem |
|---|---|---|
| **MSI B850 Tomahawk MAX WiFi** | **$230** | **None. Worst case PCI_E3 drops x4→x2.** |
| ASRock B850 Steel Legend WiFi | $170 | Populating M2_4 **disables** the x4 slot |
| ASUS TUF Gaming B850-Plus WiFi | $210 | Populating M.2_3 **disables** the x4 slot |
| ASRock X870 Pro RS WiFi | $182 | Only 3 M.2 (one Gen3); M2_2 **disables** the x4 slot |
| Gigabyte B850 AORUS Elite WiFi7 | $210 | **Disqualified** — extra slots are PCIe 3.0 **x1** electrical |

The MSI is the only one where four NVMe drives and an add-in card coexist. Given the
Realtek NIC risk below, keeping a guaranteed-usable slot is not theoretical.

### Re-examined 2026-08-31, and confirmed

A **sealed ASUS TUF Gaming B850-E WiFi appeared locally at $120** — half its $239 retail —
and forced an honest re-test of this choice. It matches on the two hard requirements
(4 DIMM, PCIe 5.0 x16) but has **3 M.2** and a secondary slot that is only **x1 electrical**.

Two arguments said to take it:

1. The x4 slot was justified largely by an **HBA card for the NAS** — and the NAS has since
   become a separate box, which removed that need.
2. The Intel-NIC fallback still works on an x1 slot, since 2.5GbE needs about that much
   bandwidth. And the TUF's RTL8125 2.5GbE is *more* mature on Linux than this board's newer
   RTL8126 5GbE.

**Decision: keep the Tomahawk anyway.** The $110 premium buys a fourth M.2 and a genuine x4
slot — options that are cheap to hold now and impossible to add later, on a board meant to
last five years. Buying new from a retailer also carries a warranty and skips a drive to
Illinois. This is a deliberate choice to pay for optionality, not an oversight.

**X870 is not worth a premium here.** B850 and X870 use the same single Promontory 21 die
and have effectively the same lane budget. X870 only *mandates* USB4 and PCIe 5.0 graphics,
both of which this B850 board already provides (PCIe 5.0) or which you don't need (USB4).

## Lane-sharing rules to obey

- Populating **M2_3** drops PCI_E3 from x4 to x2. Prefer M2_1, M2_2, M2_4 first.
- The x16 GPU slot is **never** affected by M.2 population. Good.
- No documented M.2-vs-SATA disablement.

## Known risks

1. **Realtek RTL8126 5GbE on Linux.** New silicon, immature in-tree support; likely needs a
   recent kernel or an `r8126` DKMS module — awkward on SteamOS's immutable root. There is
   also an open kernel 6.17 regression causing Realtek 2.5GbE throughput to decay over days
   of uptime. **Mitigation: budget ~$30 for an Intel-chipset 2.5GbE card in PCI_E3.**
2. **Zen 6 needs a BIOS update.** AMD confirmed socket compatibility, not per-board support.
   Check MSI's BIOS list before buying a Zen 6 chip in 2027–28.
3. **Keep BIOS current.** AM5 USB dropout quirks have historically been AGESA fixes.

## Do not buy

Any AM4, LGA1700, or LGA1851 board. Any board with fewer than 4 DIMM slots. Any board whose
only secondary slots are x1 electrical.
