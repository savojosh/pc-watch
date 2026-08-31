# Dream build — PCPartPicker list "001"

Source: https://pcpartpicker.com/user/savjospra/saved/#view=RvHQf7 (user: savjospra)
Reviewed 2026-08-31. Josh describes this as his dream PC.

## The list as saved

| Part | Component | Listed price |
|---|---|---|
| CPU | Intel Core Ultra 9 285K, 24-core (8P+16E), 3.7 GHz | $514.00 |
| CPU Cooler | ARCTIC Liquid Freezer III Pro, 110 CFM AIO | $228.87 |
| Thermal paste | ARCTIC MX-6, 4 g | $9.99 |
| Motherboard | MSI Z890 GAMING PLUS WIFI, ATX, LGA1851 | $209.99 |
| Memory | Silicon Power XPOWER Zenith 64 GB (2×32) DDR5-6000 CL30 | $999.97 |
| Storage | Crucial P510 1 TB, M.2 PCIe 5.0 | $209.99 |
| Storage | Crucial P510 2 TB, M.2 PCIe 5.0 | $339.99 |
| GPU | MSI SHADOW 3X OC GeForce RTX 5070 Ti 16 GB | not priced |
| Case | Fractal Design North XL, full tower ATX | $155.99 |
| PSU | be quiet! Dark Power 13, 1000 W 80+ Titanium | $214.90 |
| UPS | CyberPower CP1500PFCLCD | $229.95 |
| **Listed total** | (GPU excluded) | **$3,113.64** |

**True total with GPU: roughly $4,000–4,400.** The 5070 Ti is running about $900–1,270 in Aug 2026, far above its $749 MSRP.

## Verdict: the bones are right

This is a well-conceived list, and it matches the stated priorities better than anything on Marketplace:
- **285K (24 cores)** is a genuine work CPU — right call over an X3D chip for CPU-based AI and parallel Flutter builds.
- **Liquid Freezer III Pro** is the correct cooler and is what the 285K actually needs under sustained all-core load.
- **North XL** is a full tower with real radiator clearance. Good pairing.
- **64 GB** is the right capacity target for CPU inference.
- **UPS** is a mature inclusion most builds skip.

## What to change

**1. The memory line is the whole build.** $999.97 for 64 GB is not a PCPartPicker glitch — DDR5 has surged roughly 300% in six months on AI datacenter demand. RAM is ~32% of this build's cost. Implications:
- Buy the RAM *first* if buying at all; it is still climbing.
- Consider 2×32 GB now on a 4-slot board and add later only if prices fall (they may not soon).
- Used/secondhand DDR5 is worth watching for the first time ever.

**2. Drop PCIe 5.0 storage.** $550 for 3 TB across two P510s buys sequential speed that neither compiles nor CPU inference use. A good Gen4 drive (SN850X, 990 Pro) at 2–4 TB performs identically for these workloads and saves roughly $200–250 — money better spent on RAM at current prices.

**3. PSU is over-specced.** A 285K + 5070 Ti peaks around 600 W. A quality 850 W Gold/Platinum saves ~$100. Counter-argument: 1000 W Titanium leaves headroom for a much larger GPU later, which is a legitimate reason to keep it.

**4. Skip the MX-6.** The Liquid Freezer III ships with paste pre-applied. Minor, but it's free money.

**5. Nothing here addresses the home-server/NAS goal.** No HDDs, no bay planning. The North XL has limited 3.5" capacity. Decide whether NAS is part of this machine or a separate box.

## The one real strategic question: LGA1851 vs AM5

Josh listed "cheap upgradable base" as a goal, and LGA1851 is the weak point of this list. Intel's socket cadence is short; Arrow Lake may be a one-to-two-generation socket. AM5 is committed well past 2027.

The comparison to run: **Ryzen 9 9950X (16C/32T) on X670E/X870** versus the 285K on Z890. The 9950X is competitive-to-better in compile and CPU-inference throughput, and buys a real upgrade path. The 285K holds advantages in some mixed workloads and idle power.

This does not need resolving today — the RAM decision dominates the budget either way.
