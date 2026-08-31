# 00 — Unified architecture

**Locked 2026-08-31.** This file is the contract. Every other file in `design-spec/`
elaborates one part of it. If a listing conflicts with this file, the listing is wrong.

Target lifecycle: **5 years** (to ~2031) before a required upgrade.

---

## The single decision everything hangs on: Socket AM5

| | AM5 (chosen) | LGA1851 (rejected) |
|---|---|---|
| Vendor commitment | **Confirmed through 2029** (Computex, June 2026) — and AMD declined to call that the end | No comparable commitment |
| Next-gen drop-in | **Zen 6 "Olympic Ridge" confirmed AM5** in AMD's own documentation | Arrow Lake likely a 1–2 generation socket |
| Upgrade at year 3 | Drop in a Zen 6 X3D. Keep board, RAM, cooler, case, PSU | New board + likely new RAM |

A five-year target makes this decisive. **The PCPartPicker "dream build 001" is retired as
an architecture** — the Core Ultra 9 285K, the MSI Z890, and LGA1851 are all out. Its
*shape* survives: high core count, 360 mm AIO, 64 GB, dual NVMe, full-size case, UPS.

**Host OS: Bazzite** (locked 2026-08-31, replacing SteamOS). Bazzite supports both AMD and
NVIDIA, **so there is no GPU vendor constraint.** The GPU is chosen on price and Linux
driver quality alone — which currently still points at AMD, but for market reasons rather
than compatibility ones. See `gpu.md`.

---

## The locked slot/interface matrix

Everything bought for this machine must match this table. No exceptions.

| Interface | Locked value | What this rules out |
|---|---|---|
| CPU socket | **AM5 (LGA1718)** | AM4, LGA1700, LGA1851 |
| Chipset | **B850** | — |
| Memory | **DDR5 UDIMM, non-ECC, EXPO** | **All DDR4** |
| Memory slots | 4 × DIMM, 256 GB max | — |
| GPU interface | **PCIe 5.0 x16** (backward compatible) | — |
| GPU vendor | **Either** — Bazzite supports both | nothing |
| Boot/data drives | **M.2 2280 NVMe**, 4 slots | 2.5" SATA SSDs as primaries |
| Cooler mount | **AM5 bracket**, 360 mm radiator | AM4-only coolers, air coolers |
| Case | **ATX**, 360 mm radiator support | Cases without 360 rad clearance |
| PSU | **ATX 3.1**, 750 W, fully modular | SFX, non-modular |

## The board: MSI MAG B850 Tomahawk MAX WiFi — $230

Chosen over four rivals on one axis: it is the only board in class where **four NVMe drives
and an add-in card can coexist**. Full reasoning in `motherboard.md`.

- 4 DIMM · 4 M.2 (2× Gen5 CPU-direct, 2× Gen4) · 4 SATA
- PCIe 5.0 x16 (never lane-shared) + a **PCIe 4.0 x4 full-length slot that is never disabled**
- 14 × 80 A VRM — ample for a future Zen 6 X3D
- 5GbE Realtek RTL8126, Wi-Fi 7

**Known risk:** the RTL8126 is new silicon with immature Linux support, and there is a live
kernel 6.17 regression affecting Realtek 2.5GbE throughput. Mitigation: the spare x4 slot
takes an Intel NIC for ~$30. No board in this class ships an Intel NIC.

---

## Scope decisions

**NAS is a separate box, later.** Decided 2026-08-31. This machine needs no 3.5" bays and
no HBA card. The likely NAS is this build's own hand-me-down when the Zen 6 chip goes in.

**Host OS is Bazzite.** Decided 2026-08-31 over SteamOS and CachyOS. The reasoning:

- **Games are a tie.** Both run identical Proton and Mesa; no game works on one and not the
  other. His library is a best case — Stellaris and CK3 native, Palworld/Deadlock/CS:II at
  Platinum or Gold — with zero kernel anti-cheat exposure.
- **Development is not a tie.** Tailscale ships in Bazzite's **base image**
  (`ujust enable-tailscale`), so it is rebuilt with every update and cannot be orphaned. On
  SteamOS it is a devrel script installing to `/opt` whose own readme says to rerun it
  periodically — unacceptable for a dependency of an unattended eleven-hour nightly job.
- **`ujust setup-virtualization`** gives a one-command Windows 11 VM including **software
  TPM** (satisfying Win11's TPM 2.0 requirement) and re-applies after reboot. SteamOS has no
  supported path — pacman writes to the image Valve replaces on update.
- Valve publishes **no developer guidance for SteamOS at all**; the GitHub issue asking how
  to make software and systemd services survive updates has gone unanswered since Oct 2025.

**Consequence: the AMD-only GPU constraint is lifted.** NVIDIA is allowed.

**Structural rule that follows from Bazzite:** systemd services do **not** run inside
distrobox containers. Anything unattended — Tailscale, the trading program, libvirtd — lives
as a **host** systemd unit. One distrobox holds Flutter, the Android SDK, JDK/Gradle and
Node; VS Code runs as a host Flatpak and attaches into it. adb udev rules go on the host.

Layout mechanics for the two-drive plan: `storage-layout.md`.

## Five-year path

| When | Move |
|---|---|
| Now | Zen 5 12-core, 32 GB, used/new AMD 16 GB GPU, dual NVMe |
| +6 mo | Second RAM kit → 64 GB. Highest-value upgrade available |
| 2027–28 | **Zen 6 X3D drop-in.** Same board, RAM, cooler, case, PSU. Serves CK3/Stellaris properly |
| 2028–29 | GPU upgrade into the PCIe 5.0 slot |
| Handoff | The displaced CPU + board become the 24/7 trading box / NAS |
