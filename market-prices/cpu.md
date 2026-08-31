# Market prices — CPU

Spec: `../design-spec/cpu.md` · Target: **Ryzen 9 9900X**, fallback 7900X

**Market health: HEALTHY — the only genuinely healthy market in this build.**
**Budget: $275–330 standalone**, or folded into a bundle.

## Observed prices

| Date | Part | Source | Price |
|---|---|---|---|
| 2026 (May) | Ryzen 9 7900X | Newegg (30-day low) | **$310.79** |
| 2026 | Ryzen 9 7900X | HotHardware coverage | **$275** |
| 2026 | Ryzen 9 7900X | trading range through the year | $275–360 |
| 2026-08-31 | Ryzen 7 7800X3D (used, Elkhorn) | Marketplace | $300 |

## The Micro Center bundle — the single biggest lever in the build

Micro Center's AM5 **3-in-1 bundles** (CPU + motherboard + 32 GB DDR5) have run, as one
documented example: **Ryzen 9 9900X + MSI X870E-P Pro WiFi + G.Skill Flare X5 32 GB
DDR5-6000 for $649.98**, versus ~$1,110 bought separately — **~$460 saved**.

That example is from a February article and bundle contents rotate weekly. **Treat it as
evidence that bundles are worth ~$400–460, not as a quote.**

Why it matters more now than it did then: it was priced *before* the worst of the DDR5
spike. The 32 GB kit alone is $404 today. A bundle is effectively CPU + board for ~$250.

Note the example bundle ships an X870E board rather than the specified B850 Tomahawk. An
X870E board is a **fine substitute or better** — the constraint is socket AM5 and 4 DIMM
slots, both of which it satisfies. Check its M.2 and expansion-slot layout against
`../design-spec/motherboard.md` before committing.

### Trip cost math

Nearest store: **Westmont, IL**, ~100 mi each way, 200 mi round trip.

| | 24 mpg | 27 mpg |
|---|---|---|
| Gallons | 8.33 | 7.41 |
| Fuel @ $5/gal | $41.65 | $37.05 |
| + IL tolls (~$8) | ~$50 | ~$45 |
| + IL sales tax premium (8% vs WI 5.5%, on ~$650) | ~$16 | ~$16 |
| **All in** | **~$66** | **~$61** |

Plus ~3.5 hours of driving.

**Verdict: a $460 bundle saving clears a $66 trip roughly seven times over. Worth the
drive** — but go once, with a complete list, and only after phoning store #081 that morning
to confirm stock. A trip for a single $100 part is not worth it.

## Buy triggers

- **Bundle at ≤ $700** including 32 GB RAM: strong buy, go immediately.
- **7900X standalone at ≤ $300**: take it.
- **9900X standalone at ≤ $360**: take it.
- Do not pay above $360 for a 12-core standalone; this market does not require it.

## Do not track

Any LGA1700, LGA1851 or AM4 chip. 8-core X3D parts as a *primary* CPU — the X3D purchase is
deliberately deferred to the Zen 6 generation.
