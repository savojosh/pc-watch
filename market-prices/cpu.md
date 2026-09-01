# Market prices — CPU

Spec: `../design-spec/cpu.md` · **Plan A: Ryzen 9 9950X via bundle. Plan B: Ryzen 9 9900X.**

**Market health: HEALTHY — the only genuinely healthy market in this build.**

## Live Micro Center AM5 bundles — verified 2026-08-31

Read directly from [microcenter.com/site/content/bundle-and-save.aspx](https://www.microcenter.com/site/content/bundle-and-save.aspx).
All are **in-store only, no shipping, limit 1 per household.** Component prices are Micro
Center's own standalone prices.

| Bundle | Price | Reg. | Save | Contents |
|---|---|---|---|---|
| **9950X 3-in-1 ← PLAN A** | **$999.99** | $1,264.97 | **$265** | Ryzen 9 **9950X** ($489.99) + **ASUS ProArt B850-Creator WiFi** ($294.99) + G.Skill Flare X5 **32 GB DDR5-6000 CL36** ($479.99) |
| 9950X motherboard upgrade | $1,199.99 | $1,479.97 | $280 | Same CPU + RAM, ASUS X870E Creator ProArt ($509.99) |
| 9950X3D | $1,049.99 | $1,219.97 | $170 | 9950X3D ($549.99) + Gigabyte X870 Gaming + 32 GB |
| 9850X3D | $919.99 | $1,139.97 | $220 | 9850X3D 8-core ($459.99) + **ASUS B850-E TUF** ($199.99) + 32 GB |
| 9800X3D | $899.99 | $1,059.97 | $160 | 9800X3D 8-core + MSI B850 Gaming Pro + 32 GB |
| 9700X | $699.99 | $989.97 | $290 | 9700X 8-core + Gigabyte B650 Gaming X AX V2 + 32 GB |
| 7800X3D | $749.99 | $969.97 | $220 | 7800X3D 8-core + ASUS B650E MAX + 32 GB |

**[Plan A direct link — product 5007458](https://www.microcenter.com/product/5007458/amd-ryzen-9-9950x,-asus-b850-creator-proart-wifi-am5,-gskill-flare-x5-series-32gb-ddr5-6000-kit,-computer-build-bundle)**

### Two things this table settles

1. **There is no 9900X bundle.** Micro Center's Ryzen 9 tier starts at the 9950X. The
   originally-specced 12-core is a standalone purchase only — which is what Plan B is.
2. **Every 8-core X3D bundle is off-spec.** The 9850X3D at $919.99 is tempting and would be
   excellent for CK3 and Stellaris, but 8 cores badly misses the 12-core floor for
   concurrent Flutter builds plus a VM plus the trading process. The X3D purchase stays
   deferred to the Zen 6 generation as a drop-in upgrade.

### Trip cost — Westmont IL, store #081

~100 mi each way, 200 mi round trip.

| | 24 mpg | 27 mpg |
|---|---|---|
| Fuel @ $5/gal | $41.65 | $37.05 |
| + IL tolls (~$8) | ~$50 | ~$45 |
| + IL sales tax premium (8% vs WI 5.5%, on ~$1,000) | ~$25 | ~$25 |
| **All in** | **~$75** | **~$70** |

Plus ~3.5 hours driving. A $265 bundle saving clears a ~$70–75 trip roughly 3.5× over.
**Worth the drive** — but go once, with a complete list, and phone **(630) 371-5500** that
morning to confirm stock.

## Plan B — standalone prices

| Date | Part | Source | Price |
|---|---|---|---|
| 2026 (May) | Ryzen 9 7900X | Newegg 30-day low | $310.79 |
| 2026 | Ryzen 9 7900X | HotHardware coverage | $275 |
| 2026 | Ryzen 9 7900X | trading range | $275–360 |
| 2026-08-31 | Ryzen 9 9950X | Micro Center standalone | $489.99 |

## Buy triggers

- **The $999.99 bundle: buy on sight**, once the money is ready and stock is confirmed.
- **9900X standalone at ≤ $360** (Plan B): take it.
- **7900X standalone at ≤ $300** (Plan B alternate): take it.
- Do not pay above $360 for a 12-core standalone.

## Standing risk

**Bundles rotate weekly and this one may disappear before the money is ready.** That is the
entire reason Plan B stays specced. Re-check the bundle page before assuming Plan A is live;
if it is gone, switch to Plan B and re-date `00_budget-ledger.md`.

## Do not track

Any LGA1700, LGA1851 or AM4 chip. 8-core X3D parts as a primary CPU.
