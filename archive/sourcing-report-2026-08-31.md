# Hardware sourcing report — 31 Aug 2026

Scope: every part on build plan v2. Sellers: new retail + reputable used, no heavily-used parts, good-ratings sellers only. GPU priced AMD-first (SteamOS), with the Bazzite/CachyOS escape hatch noted.

## The headline: two of your parts are in a genuine price crisis

This is the single most important finding, and it invalidates a chunk of the v2 estimates.

**DDR5 and NAND are both in an AI-datacenter-driven shortage.** Tom's Hardware's trackers (updated 24–27 Aug 2026):

| Part | Best price now | Lowest ever | v2 estimate |
|---|---|---|---|
| DDR5-6000 32 GB kit | **$404** | $72 | $430 ✅ still accurate |
| DDR5-6000 64 GB kit | **$869** | $159 | $950 ✅ still accurate |
| 1 TB Gen4 (990 Pro) | **$239** | $59 | $100 ❌ **+$139** |
| 2 TB Gen4 (Crucial P310) | **$299** | $93 | $190 ❌ **+$109** |
| 2 TB Gen4 (SN850X) | $328 | $89 | — |

Storage is now ~2.5× the v2 estimate. The RAM estimates held up. Gartner has forecast a ~130% memory cost surge through 2026, and the NAND squeeze is the same story. **Nothing suggests either drops before December.**

Practical consequence: the "buy SSDs on Black Friday" plan in v2 is the weakest part of the sequence. Black Friday discounts a percentage off an inflated price; it does not undo a shortage. If anything, buy storage sooner rather than later, and buy less of it.

## GPU — the AMD market is also inflated

| Card | New | Used (eBay) | Launch MSRP |
|---|---|---|---|
| RX 7900 GRE 16 GB | $799 (Amazon) | **$575** | $550 |
| RX 7800 XT 16 GB | $895 (Amazon) | **$460** | $499 |
| RX 9060 XT 16 GB | **$470** (PowerColor Reaper, Amazon) | — | $349 |

Read carefully: **new RDNA 3 cards are selling above their used prices and far above MSRP** — they're end-of-life and scarce. The used 7800 XT at ~$460 and the new 9060 XT at ~$470 are the same money.

My pick at this moment: **new RX 9060 XT 16 GB at ~$470.** Warranty, no wear, current-gen drivers, 16 GB, and it sidesteps your "no heavily-used hardware" rule entirely. The 7900 GRE is faster (roughly 25–30% at your ~6 MP ultrawide) but costs $105 more used with unknown history, or $329 more new.

The used **7800 XT at $460 from a high-rated seller with photos and a POST/benchmark video** is the value play if you'd rather have the wider memory bus. Do not pay $799–895 for a new 7900 GRE or 7800 XT under any circumstances — that is a scarcity tax, not a price.

*If you go Bazzite or CachyOS instead of SteamOS, NVIDIA reopens and this table should be re-run — but note NVIDIA's 50-series is caught in the same memory shortage, so expect no bargain there either.*

## CPU + motherboard — the one healthy market

The 7900X has been trading **$275–360** through 2026; PC Guide logged **$310.79 at Newegg** (May 2026) as a 30-day low, and HotHardware has covered it at **$275**. It is not shortage-affected. Set a price alert and take anything ≤$300.

**Micro Center bundles are the real lever here.** Their 3-in-1 AM5 bundles have run e.g. Ryzen 9 9900X + MSI X870E-P Pro WiFi + G.Skill Flare X5 32 GB DDR5-6000 for **$649.98**, versus ~$1,110 separately — **~$460 saved**, and that was priced *before* the worst of the RAM spike. Buying that RAM alone today is $404.

A bundle like that is CPU + board + 32 GB for less than CPU + board + RAM bought piecemeal, with a *newer, faster* chip than the 7900X (9900X is Zen 5, same 12C/24T, better IPC, drops into the same 5-year Zen 6 upgrade path).

### Micro Center trip math

Nearest store is **Westmont, IL** — roughly **100 mi each way, 200 mi round trip** from Whitewater.

| | 24 mpg | 27 mpg |
|---|---|---|
| Gallons | 8.33 | 7.41 |
| Fuel @ $5/gal | **$41.65** | **$37.05** |
| + IL tolls (~$8 round trip) | ~$50 | ~$45 |

**Call it $45–50 all-in, plus ~3.5 hours of driving.**

One thing that eats into it: you pay **Illinois sales tax (~8% in Westmont)** on an in-store pickup rather than Wisconsin's 5.5%. On a $650 bundle that's ~$16 extra. So the real trip cost is closer to **$62–66**.

Verdict: a $460-saving bundle clears a $65 trip cost roughly seven times over. **Worth the drive** — but only go once, with a full list, and only after confirming stock at store #081 by phone that morning. A trip for a single $100 part is not worth it.

## Everything else — small, healthy markets

| Part | Target | Notes |
|---|---|---|
| Arctic Liquid Freezer III Pro 360 | **~$91–100** | Amazon has run $91.49; Slickdeals has logged $99.63 shipped. Newegg **open-box has hit $52–61** — a cooler is a low-risk open-box buy (no wear parts beyond the pump, sealed unit). |
| 750 W Gold ATX 3.1 PSU | **$75–80** | PCCooler CPS KN750 has hit $74.99; Cooler Master MWE Gold V2 $73. Both fully modular. Don't overpay — $115 in v2 was pessimistic. |
| Airflow ATX case, 360 mm support | **$85–100** | Lancool 216 / Montech Air 903 Max / Phanteks G400A. Stable market, buy on any sale. |
| CyberPower CP1500PFCLCD | **~$180** | Unchanged. Buy last, as planned. |

## Revised realistic total

| | v2 estimate | Now |
|---|---|---|
| CPU + mobo + 32 GB RAM | $910 | **$650** (Micro Center bundle) |
| GPU | $350–450 | **$470** |
| Boot SSD 1 TB | $100 | **$239** |
| Data SSD 2 TB | $190 | **$299** |
| Cooler | $115 | **$95** |
| PSU | $115 | **$78** |
| Case | $95 | **$95** |
| **Subtotal** | ~$1,925 | **~$1,926** |
| + UPS | | ~$2,106 |
| + IL tax/fuel | | **~$2,170** |

Same total as v2 — but arrived at completely differently. The bundle saves you ~$260 and the PSU/cooler save ~$57; storage gives all of it back and more.

### Where to cut, if $2,170 is too much

1. **Drop the 2 TB data SSD for now (−$299).** Run one 1 TB drive, add the second when NAND normalizes. This breaks your two-drive organization plan temporarily — but $299 for a drive that cost $93 at its floor is the worst dollar in this build. Partition the 1 TB instead as a stopgap.
2. **UPS later (−$180).** Already the plan.
3. **That's $1,690.** Close to the stretch target, and the deferred parts are exactly the ones whose prices should improve.

Do *not* cut RAM to save money — 32 GB is already the floor for SteamOS + Windows VM + your trading NNs, and the second kit later will cost more, not less.

## Recommended action order

1. **This week:** call Micro Center Westmont (store 081), confirm which AM5 3-in-1 bundles are live and in stock. Bundles rotate.
2. **Same trip:** buy bundle + case + PSU + cooler if their in-store prices are competitive. One trip, one tax hit.
3. **Set alerts now:** RX 9060 XT 16 GB under $450; 7900X under $300 (as a bundle fallback).
4. **Watch, don't buy:** SSDs. Check the Tom's tracker every two weeks. Buy the 1 TB when you're ready to install; buy the 2 TB only if it breaks $250.
5. **Marketplace:** keep watching, but with new-GPU prices this inflated, your local listings from the 31 Aug sweep (esp. the 7800X3D at $300) deserve a second look — that CPU is worth more than a 7900X for CK3/Stellaris specifically.

## Caveats

All prices verified 31 Aug 2026 and will move. Micro Center bundle contents rotate weekly and the $649.98 example is from a February article — treat it as evidence that bundles are worth ~$400–460, not as a quote. eBay used prices are averages, not offers.
