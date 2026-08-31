# Notable listings — GPU

Spec: `../design-spec/gpu.md` · Prices: `../market-prices/gpu.md`
**Last verified: 2026-08-31**

## Recommendation

**Buy a new PowerColor Reaper RX 9060 XT 16 GB at ~$470.** In an inverted market where new
RDNA 3 cards cost more than used ones, the current-gen card at $470 beats a used 7800 XT at
$460 on warranty, wear and driver support — and it satisfies the no-heavily-used-parts rule
outright.

**Set an alert at $450 and buy on any dip.** Do not chase the 7900 GRE.

## Live listings

| Item | Price | Source | Verdict |
|---|---|---|---|
| **RX 9060 XT 16 GB (PowerColor Reaper), new** | **$470** | Amazon | **PURSUE** — the pick |
| RX 7800 XT 16 GB, used | ~$460 | eBay (avg) | Alternative — wider bus, but unknown history |
| RX 7900 GRE 16 GB, used | ~$575 | eBay (avg) | Stretch — 25–30% faster, $105 more |
| RX 7900 GRE 16 GB, new | $799 | Amazon | **DO NOT BUY** — scarcity tax |
| RX 7800 XT 16 GB, new | $895 | Amazon | **DO NOT BUY** — costs 2× its own used price |

## Marketplace listings

| # | Item | Price | Location | Verdict |
|---|---|---|---|---|
| 6 | "PC Parts" lot — **RTX 4060 8 GB** NIB | $325 | Janesville | **DEAD — resolved 2026-08-31.** Seller confirmed it is an RTX 4060 with 8 GB. Fails the 16 GB VRAM floor, would bottleneck the build at ultrawide, and $325 is above market for a 4060 regardless. Moved to Dismissed. The **CPU** in the same lot is still unresolved — see `cpu.md`. |
| 8 | Custom PC w/ RX 6650 XT | $800 | Edgerton | **Pass.** The 6650 XT is a downgrade from the current laptop's 3080 and has 8 GB VRAM. |

## 40 mi sweep — 2026-08-31

| Item | Price | Location | Drive | Verdict |
|---|---|---|---|---|
| **XFX Speedster SWFT 319 RX 6800 16 GB** | **$350** | Deforest, WI (~55 mi) | ~$22 → real cost ~$372 | **FALLBACK, not an upgrade.** Clears the $450 trigger with 16 GB and beats the 9060 XT in raster. But RDNA 2 (2020), **~250 W vs ~150 W** on a machine already thermally constrained overnight, no warranty, mining risk. The $470 new 9060 XT is still the better buy |
| ASUS TUF RTX 3080 Ti OC | $360 | Germantown, WI | ~$18 | **Reject** — 12 GB, under the VRAM floor |
| EVGA RTX 3080 Ti FTW | $400 | Rockford, IL | ~$18 | **Reject** — 12 GB |
| MSI RTX 3060 Ti Ventus 3X | $250 | Waukesha, WI | ~$14 | Reject — 8 GB |
| Nvidia RTX 3070 | $250 | Milwaukee, WI | ~$26 | Reject — 8 GB |
| XFX RX 5700 XT | $180 | Rockford, IL | ~$18 | Reject — 8 GB, RDNA 1 |

**No used RX 7800 XT or 7900 GRE locally.** Still the best possible local find — at ≤ $420
with in-person testing, either would beat the 9060 XT.

Note the RX 6800's power draw is a genuine cost here, not a footnote: the trading program
runs 11 hours nightly and throttles on temperature, so an extra 100 W in the case works
against the machine's main job.

## Action

1. Set an alert: RX 9060 XT 16 GB new **< $450**.
2. Watch Marketplace for RX 7800 XT / 7900 GRE 16 GB. Test in person, always.
3. Message listing #6 for the exact RTX model — worth knowing even if unusable today.
4. **Decide the OS question before buying.** Moving to Bazzite or CachyOS doubles the
   available GPU market. This is the last cheap moment to change that decision.

## Used-card buying checklist

Rated seller · photos of the actual card · POST or benchmark video · test in person · check
for mining wear and evidence of repasting. No exceptions.
