# Design spec — Motherboard

**Status: LOCKED, two-plan structure as of 2026-08-31.** This is the anchor part; everything
else is chosen to fit it. Both plans are Socket AM5 / B850 / DDR5, so **every other part in
this build is identical either way.** Only the board and CPU differ.

---

## PLAN A (primary) — ASUS ProArt B850-Creator WiFi NEO

Acquired **only** as part of the Micro Center 3-in-1 bundle at **$999.99**
(9950X + this board + 32GB DDR5-6000). Standalone it is ~$291 and not worth buying alone.

[Bundle — Micro Center product 5007458](https://www.microcenter.com/product/5007458/amd-ryzen-9-9950x,-asus-b850-creator-proart-wifi-am5,-gskill-flare-x5-series-32gb-ddr5-6000-kit,-computer-build-bundle)
· **In-store only, no shipping. Limit 1 per household.** Westmont IL, store #081.

| Field | Value |
|---|---|
| Socket / chipset | AM5 / B850 |
| Form factor | ATX |
| Memory | **4 × DDR5**, 256 GB max |
| M.2 | **3** — M.2_1 Gen5 x4 (CPU), M.2_2 Gen5 x4 (CPU), M.2_3 Gen4 x4 (chipset) |
| SATA | 4 |
| Primary GPU slot | PCIe 5.0 x16, CPU-attached |
| **Secondary slot** | **Full-length PCIe 5.0 x8, CPU-attached** — unaffected by any M.2 configuration |
| Third slot | Full-length PCIe 4.0 x4 (chipset) |
| VRM | 14+2+1, 14 × 80 A DrMOS (~1120 A) — ample for the 170 W 9950X |
| LAN | **2 × 5GbE Realtek RTL8126** |
| WiFi | Wi-Fi 7 (Realtek RTL8922AE) |
| USB4 | No (header only) |

### Lane-sharing rules to obey

- **M.2_1 and M.2_2 are CPU-attached and share with nothing.** Use these two first.
- **M.2_3 and the third slot (Gen4 x4) are mutually exclusive** — populating either disables
  the other. Effectively: **2 unconditional M.2 + 1 conditional.**
- **Installing a card in the second slot splits the CPU x16 into x8/x8.** The GPU drops to
  PCIe 5.0 x8 — a sub-2% effect on any current card, and equal to PCIe 4.0 x16 bandwidth.
- SATA is not shared with any M.2 slot.

---

## PLAN B (backup) — MSI MAG B850 Tomahawk MAX WiFi, $229.99

**Use this if the bundle sells out before the money is ready.** Buy the board new from
Newegg, pair with a **Ryzen 9 9900X** and a 32 GB DDR5-6000 **CL30** kit separately. Fully
shippable, no trip required.

> Order the **MAX WiFi**, not the **MAX WiFi II** ($259.99). The names are close enough to
> mis-order.

| Field | Value |
|---|---|
| Memory | 4 × DDR5, 256 GB max |
| M.2 | **4** — M2_1 Gen5 x4 (CPU), M2_2 Gen5 x4 (CPU), M2_3 Gen4 **x2**, M2_4 Gen4 x4 |
| SATA | 4 |
| Primary GPU slot | PCIe 5.0 x16, CPU-attached, **never lane-shared** |
| Secondary slot | Full-length PCIe 4.0 x4 (chipset), **never disabled** — drops to x2 only if M2_3 is populated |
| VRM | 14 × 80 A SPS (~1120 A) |
| LAN | 1 × 5GbE Realtek RTL8126 |
| WiFi | Wi-Fi 7 |

Populating M2_3 drops the secondary slot x4→x2. Prefer M2_1, M2_2, M2_4.

---

## Why Plan A wins, and what it costs

| Priority | ProArt | Tomahawk | Winner |
|---|---|---|---|
| 4 DIMM slots | Yes | Yes | Tie |
| PCIe 5.0 x16 | Yes | Yes, never shared | Tie |
| **Usable secondary slot** | **Gen5 x8, CPU-attached, never affected** | Gen4 x4, chipset | **ProArt — ~4× the bandwidth** |
| M.2 count | 3 (2 unconditional) | 4 | **Tomahawk** |
| NIC on Linux | 2 × Realtek | 1 × Realtek | **Tie — see below** |
| VRM for 170 W | 14 × 80 A | 14 × 80 A | Tie |

**The NIC correction that mattered.** Both boards use the same Realtek RTL8126, which has
immature Linux support. **No board in this class ships an Intel NIC**, so an Intel add-in
card (~$30) is a purchase to plan for **either way** — it is not a workaround specific to
one board. That collapses the NIC question into the expansion-slot question, which the
ProArt wins decisively: the card lands in a CPU-attached Gen5 x8 slot instead of a chipset
Gen4 x4 one.

**What Plan A gives up:** the 4th M.2, and CL30 RAM (the bundle ships CL36). The 4th M.2
mattered mainly for an HBA when the NAS lived in this machine — and the NAS is now a
separate box. The spec needs 2 drives; the ProArt gives 2 unconditionally.

**Unplanned bonus:** dual 5GbE. When the NAS becomes its own box, that allows a direct
high-speed link to it without touching the rest of the network.

## Do not buy

Any AM4, LGA1700 or LGA1851 board. Any board with fewer than 4 DIMM slots. Any board whose
only secondary slots are x1 electrical.
