# Notable listings — CPU

Spec: `../design-spec/cpu.md` · Prices: `../market-prices/cpu.md`
**Last verified: 2026-08-31**

## Recommendation

**Call Micro Center Westmont (#081) this week before buying anything else.** The AM5 3-in-1
bundle is the single biggest saving available in this entire build — historically ~$400–460
— and it determines whether the CPU, board and first RAM kit are bought together or
separately. Everything else waits on that phone call.

If no bundle is live, set price alerts and take a **7900X at ≤ $300** or a **9900X at ≤ $360**.

## Live listings

| Item | Price | Source | Link | Verdict |
|---|---|---|---|---|
| **Micro Center AM5 3-in-1 bundle** (CPU + board + 32 GB) | **~$650** when live | Micro Center Westmont #081 | [store](https://www.microcenter.com/site/stores/westmont.aspx) | **PURSUE FIRST** — call to confirm current bundle |
| Ryzen 9 7900X | $275–360 | Newegg / Amazon | — | Buy at ≤ $300 |
| Ryzen 9 9900X | market | Newegg / Amazon | — | Buy at ≤ $360 |

## Marketplace listings — reassessed under the AM5 architecture

| # | Item | Price | Location | Verdict |
|---|---|---|---|---|
**No AMD CPU listings locally.** A live sweep on 2026-08-31 returned **zero** results for
"ryzen" within 20 mi of Whitewater.

> **Search caveat:** that sweep used the terms "ryzen", "ddr5", "gaming pc", "rtx" and
> "9060 xt". It would NOT have matched Intel-titled listings, or anything using a model
> number without those words. Do not read a zero-result Ryzen search as "nothing is
> available" — search by explicit model number before declaring a listing expired.

| # | Item | Price | Location | Status |
|---|---|---|---|---|
| 4 | **Intel i7-14700KF** | **$250**, reduced from $270 | Whitewater | **STILL LIVE, confirmed 2026-08-31.** [Listing](https://www.facebook.com/marketplace/item/1065221752982873/). **Rejected on spec** — see below |
| 3 | Ryzen 7 7800X3D, new/seal broken | $300 | Elkhorn | **Expired** — a "ryzen" search returns nothing |
| 6 | "PC Parts" lot — unspecified "Ryzen" NIB | $200 | Janesville | **Expired** — model never identified |

### Why the 14700KF stays rejected, despite being cheaper

It is a genuinely good chip at a fair price, and on paper the Intel path is cheaper *and*
higher core-count: $250 + a used LGA1700 board (~$120–150) = **~$400 for 20C/28T**, versus
9900X $360 + B850 $230 = **~$590 for 12C/24T**.

It loses anyway, on four counts:

1. **LGA1700 is a finished socket.** No upgrade path, ever. AM5-through-2029 with a
   confirmed Zen 6 drop-in was the whole basis of the architecture decision.
2. **Power and heat.** ~250 W sustained all-core versus ~150 W for a 9900X. The trading
   program runs 11 hours nightly and **throttles on CPU temperature** — so this converts
   directly into less completed overnight work, on the workload that justified the build.
3. **Raptor Lake Vt degradation.** Would require confirming the seller ran BIOS with the
   0x12B microcode, plus a receipt for Intel's extended warranty.
4. **Seller shows no ratings** — only "Joined Facebook in 2015". Fails the good-ratings rule,
   which matters more than usual on a used CPU with a known degradation issue.

**Do not re-flag this listing** even if the price drops further. The rejection is
architectural, not financial.

The one AM5 CPU now available locally is inside the **Eagle whole-system listing** (Ryzen 5
9600X) — see `whole-systems.md`. It is a 6-core part and does not meet the 12-core floor on
its own.

## Action

1. Phone #081, confirm live bundles and stock. **This week.**
2. Message listing #6 asking for the exact Ryzen model number.
3. Set alerts: 7900X < $300, 9900X < $360.
4. **Remove listing #4 from all watchlists** — wrong socket, permanently.

## Expired / removed

- **i7-14700KF $250 (Whitewater)** — removed 2026-08-31, incompatible with locked AM5 platform.
