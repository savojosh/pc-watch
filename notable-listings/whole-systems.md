# Notable listings — Whole systems & parts lots

Complete machines and mixed lots, which don't belong to a single part file.
**Last verified by live sweep: 2026-08-31.**

## Recommendation

**One live listing, and it is the strongest find so far: the Eagle WI machine at $1,299.**
Under consideration, not yet pursued. It is roughly $600 under parts value and covers every
shortage-inflated component in the build at once — but its CPU is half the cores the spec
requires, so it is a *starting point*, not a finished build.

Everything previously tracked here has **expired**.

---

## LIVE — Gaming PC + 27" 1440p 180Hz monitor, $1,299 firm, Eagle WI

[Listing](https://www.facebook.com/marketplace/item/1615949413652605/) · listed 2026-08-31 ·
seller "Lynna Lee", **73 ratings, Highly rated on Marketplace** · used–like new

Built December 2025, lightly used, **original boxes for all major components except the
case**, Windows 11 activated, will be wiped before sale, seller offers to demonstrate it
working. 3DMark Steel Nomad 3,888 (slightly above the 9060 XT average). Cinebench multi 3,854.

### Specification vs the locked design spec

| Component | Listed | Verdict |
|---|---|---|
| GPU | Sapphire **RX 9060 XT 16GB** | ✅ Exactly the spec'd GPU. $470 new |
| RAM | **32GB DDR5-6000 (2×16)** | ✅ Right spec, right speed. $404 new today |
| PSU | **Corsair RM750e 750W fully modular** | ✅ Meets the PSU spec exactly. ~$90 |
| Motherboard | ASRock B850M Pro-A WiFi | ✅ AM5 / B850, **4 DIMM**, PCIe 5.0, 2.5GbE. Micro-ATX |
| Storage | Samsung 990 EVO Plus 2TB | ⚠️ **DRAM-less HMB** — against the storage spec. ~$250 |
| CPU | Ryzen 5 **9600X** | ❌ **6 cores vs the 12-core floor.** The main failing |
| Cooler | ID-COOLING FROZN A620 PRO | ❌ **Air** — fails the water requirement. ~$40 |
| Case | Okinos walnut **micro-ATX** | ❌ Will not take a 360 mm AIO. ~$90 |
| Monitor | Acer XV272U B3/V3 27" 1440p 180Hz (refurb) | Bonus. ~$200 |

### Valuation

| | |
|---|---|
| Parts value, PC only, at today's prices | **~$1,694** |
| Plus monitor | **~$1,894** |
| Asking | **$1,299 firm** |
| Implied discount | **~$600** |

**The sharper framing:** the four shortage-inflated parts this build needs — GPU $470,
RAM $404, 2TB NVMe $250, PSU $90 — total **$1,214 new**. This machine is $1,299 and throws
in a CPU, motherboard, case, cooler, Windows licence and a 27" 180Hz monitor for $85.

### Path to spec, if bought

| Step | Cost |
|---|---|
| Purchase | $1,299 |
| Add Ryzen 9 9900X later | +$360 |
| ATX case + Arctic Liquid Freezer III 360 | +$190 |
| Sell 9600X (~$180) and case+cooler (~$100) | −$280 |
| **Net** | **~$1,569** |

Against **~$1,926** for the staged parts plan at the same 32 GB — and that plan includes no
monitor and no working machine until December. It also makes the Micro Center bundle
largely unnecessary, since RAM, board, GPU, SSD and PSU would all be covered.

### Open questions before buying

1. Is the RAM **EXPO**-profile, and is it 2×16 in slots 1+3 (leaving the correct pair free)?
2. Would the seller separate the monitor? (Price is firm and he is not in a hurry — asking
   may be counterproductive.)
3. Monitor condition — it was bought refurbished from an Acer reseller.

### Honest risk

The 9600X fails the build's **#1 stated priority** — a great work CPU. Cinebench multi 3,854
is roughly half a 9900X. For concurrent Flutter builds plus a Windows VM plus the overnight
trading process, 6 cores is not adequate as an endpoint. Buying this means committing to a
CPU upgrade later, on a micro-ATX board rather than the spec'd Tomahawk.

Counterweight: it is on **AM5**, so that upgrade is a drop-in, and Zen 6 is confirmed for
the socket through 2029.

---

## EXPIRED — removed 2026-08-31

All confirmed gone in the live sweep. A search for "ryzen" within 20 mi of Whitewater now
returns **zero** results.

| Item | Was | Location |
|---|---|---|
| Skytech: RTX 5080, 9800X3D, 32GB DDR5, 2TB NVMe | $2,899 OBO | Lake Geneva |
| Custom PC: Ryzen 5 3600XT / RX 6650 XT | $800 | Edgerton |
| "PC Parts" lot (Ryzen $200 NIB, RTX 4060 8GB $325 NIB) | itemized | Janesville |

The parts lot resolved before expiring: the GPU was an **RTX 4060 8 GB**, which fails the
16 GB floor. The CPU was never identified.

## Also seen and rejected in this sweep

| Item | Price | Location | Why |
|---|---|---|---|
| NVIDIA RTX 5070 Gaming PC, i9-14900KF | $2,100 | Delavan | **LGA1700** — dead socket |
| Gaming PC, RTX 5060 | $1,100 | Janesville | 5060 is 8GB; below the VRAM floor |
| G.SKILL RipjawsV 32GB (2×16) | $180 | Fort Atkinson | **DDR4** |
| Samsung DDR5-5600 laptop memory | $150 | Janesville | **SODIMM** — laptop form factor |
| Gaming PC | $430 | Whitewater | Unspecified; almost certainly older hardware |

## What a genuinely good whole-system listing looks like

Given the shortage, a used AM5 system is worth more than the sum of its published specs —
its RAM and SSDs were bought at pre-shortage prices. Flag any local listing with:

- **Socket AM5** (X670 / B650 / X870 / B850)
- **12+ core Ryzen**, or a lower-core chip at a price that makes the rest free
- **64 GB DDR5** — that alone is ~$869 today
- **16 GB GPU**, either vendor
- Asking under **$1,400**

## Filter rules

Ignore whole systems on AM4, LGA1700 or LGA1851. Ignore anything under 32 GB RAM or with a
GPU below 16 GB VRAM.
