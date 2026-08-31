# Deal watch ledger (cloud fallback)

> **This is NOT `C:\Users\jmps2\pc-watch\ledger.md`.** The nightly run was launched as a
> scheduled cloud task with no link to the computer "iron", so `watchlist.md` and `ledger.md`
> could not be read or appended to. This file is the fallback record. **Merge these rows into
> `ledger.md` on iron**, then future runs should go back to using iron's ledger as the source of truth.
>
> Because iron's ledger was unreadable, this run could not honor the "Dismissed" or
> "Seen listings" skip-lists, and "meaningful drop" was measured against the anchors in
> `claude/sourcing-report-2026-08-31.md` and `claude/dream-build-001.md` instead of real price history.

## Run log

| Date (CST) | FB Marketplace | Reddit | Slickdeals | Retail | Notes |
|---|---|---|---|---|---|
| 2026-08-31 | **NOT reachable** — no device bridge in this scheduled cloud run; FB requires the signed-in browser on iron | **NOT reachable** — r/buildapcsales and r/hardwareswap both refused automated fetch (403 / unanswered approval) | reachable | partial | Micro Center product pages do not expose prices to automated fetch (JS-rendered); Amazon blocks fetching via robots.txt — MC and Amazon figures below come from Slickdeals threads, press coverage, or price trackers, and are marked as such |

## Seen listings (new this run)

| Date | Item | Price | Source | Condition / channel | Verdict |
|---|---|---|---|---|---|
| 2026-08-31 | Intel Core Ultra 7 270K Plus (24C/24T, 8P+16E, 5.5 GHz boost, LGA1851, 250 W) | **$199.99** | Micro Center, in-store only, limit 1/household | New, boxed, no heatsink; +2 Intel Gamer Days game codes | **CLEARS** — first time under $200 since launch; was $349.99, prior street $255–310 |
| 2026-08-31 | ARCTIC Liquid Freezer III Pro 360 A-RGB (ACFRE00184A) | **$76.99** | Walmart, 3P seller "EZ Supply" (4.7★, only 36 reviews), fulfilled by Walmart | New | **Clears on price, flagged on seller** — below the $91–100 target and below the best recorded A-RGB price ($91.50); thin seller history is the risk |
| 2026-08-31 | PowerColor RX 9070 GRE Reaper 12 GB @ $479.99 Micro Center | — | Slickdeals / HardForum | — | **Dismissed** — deal marked expired/dead (posted 2026-06-30); current MC price unverifiable |
| 2026-08-31 | Micro Center 270K Plus + MSI Z890 Tomahawk + 32 GB DDR5-6400 bundle @ $649.99 | — | Slickdeals | — | **Dismissed** — expired (posted 2026-03-26). Current bundle prices unreadable; call store #081 to check |

## Price history

All read 2026-08-31. "tracker" = from a price-tracking site, not a direct retailer page read.

| Part | Price | Retailer | Note |
|---|---|---|---|
| Intel Core Ultra 7 270K Plus | $199.99 | Micro Center | in-store only; was $349.99 |
| Intel Core Ultra 9 285K | $529.99 (≈$514 net w/ code BTS3323) | Newegg mktplace | Newegg-direct $579.00 |
| AMD Ryzen 9 7900X | $339.99 | Newegg direct | misses the ≤$300 target |
| AMD Ryzen 9 9900X | $439.00 (≈$389 w/ code BTS2112) | Newegg direct | 3P sellers ~$395 |
| RX 9060 XT 16 GB (XFX Swift) | $459.99 | Newegg | ASRock Challenger $469.99; target was <$450 |
| RX 9070 GRE 12 GB (Gigabyte Gaming OC) | $549.99 | Newegg | was ~$499 early Aug — rising |
| RTX 5070 Ti 16 GB | $1,119 (ASUS Prime, tracker) / $1,149.99 (MSI, Newegg) | Best Buy / Newegg | |
| Samsung 990 Pro 1 TB Gen4 | $239.99 | Newegg + Best Buy | matches the 31 Aug anchor exactly — **not** a drop |
| WD Black SN850X 2 TB | $389.99 (tracker) | Amazon | Newegg-direct out of stock |
| Crucial P310 2 TB | $321.50 | Newegg mktplace | anchor was $299 |
| 32 GB DDR5-6000 CL30 (Patriot Viper Elite 5) | $429.99 | Newegg direct | anchor $404 |
| 64 GB DDR5-6000 CL30 (Corsair Vengeance) | $1,199.99 | Newegg direct | anchor $869 — see caveat below |
| ARCTIC Liquid Freezer III Pro 360 A-RGB | $76.99 / $109.88 | Walmart 3P / ARCTIC direct | Newegg only has a $228.80 China-shipped 3P listing |
| Thermalright Frozen Notte 360 ARGB V2 | $88.99 | Newegg mktplace | |
| NZXT Kraken Elite 360 | $259.99 | Best Buy | |
| Thermaltake Toughpower GT 850 W ATX 3.1 Gold | $79.99 | Newegg direct | top of the $75–80 band — priced fairly, not a deal |
| Fractal Design North XL | $194.99 | Newegg direct | anchor $155.99 |
| Montech AIR 903 MAX | $89.99 | Newegg direct | backordered to ~Oct 2 |
| Lian Li Lancool 216RX | $102.99 | Newegg direct | backordered to ~Sep 1 |
| CyberPower CP1500PFCLCD | $239.95 | B&H | anchor ~$180 |

### Caveat on the 64 GB DDR5 line
The $869 anchor came from a Tom's Hardware best-price tracker; $1,199.99 is one specific
Newegg SKU. This is very likely a SKU/channel difference rather than a 38% overnight jump —
**do not treat it as a confirmed move.** Re-check the tracker before acting.

## Micro Center trip math (recomputed this run)

Westmont IL store #081, ~200 mi round trip from Whitewater, fuel at $5.00/gal:

| | 24 mpg | 27 mpg |
|---|---|---|
| Fuel | $41.67 | $37.04 |
| + IL tolls (~$8) | ~$50 | ~$45 |
| + IL 8% vs WI 5.5% tax on a $200 item | +$5 | +$5 |
| **All-in for a single-part trip** | **~$55** | **~$50** |

Consequence for the 270K Plus: at $199.99 + ~$52 trip = **~$252 effective**, which is roughly
level with the ~$255 Amazon price this chip has traded at. **A trip for this CPU alone does not
pay.** It pays as part of a multi-part trip — which is what the 31 Aug sourcing report already
recommended (go once, with a full list).
