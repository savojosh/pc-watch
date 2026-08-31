# Market prices — UPS

Spec: `../design-spec/ups.md` · Target: **CyberPower CP1500PFCLCD**

**Market health: STABLE.** No shortage, no urgency.
**Budget: ~$180**

## Observed prices

| Date | Part | Source | Price |
|---|---|---|---|
| 2026-08-31 | CyberPower CP1500PFCLCD | retail | **~$180** |
| — | Same unit, dream build listing | PCPartPicker | $229.95 |

The dream build's $229.95 was list price. ~$180 is the ordinary street price and the
correct budget number.

## Reading the market

This category is boring in a good way. Prices move within a narrow band, sales are regular,
and there is no supply pressure. The unit has been a standard recommendation for years and
is widely stocked.

**This is the last part to buy** — it does nothing until the machine is assembled and the
trading program is actually running on it. Deferring it is the second-cleanest budget cut
available, after the 2 TB data SSD.

## Buy triggers

- **CP1500PFCLCD at ≤ $180**: buy, when the rest of the build is done.
- **At ≤ $150**: strong buy, take it early.
- Do not pay above $200. This unit goes on sale regularly.

## The spec that gates everything

**Pure sine wave output is required, not preferred.** Modern active-PFC power supplies —
including every candidate in `psu.md` — can behave badly on the stepped/simulated waveform
that cheaper line-interactive units produce, sometimes refusing to transfer to battery at
all. A cheaper simulated-sine UPS is worse than no UPS, because it presents as protection
and is not.

Any listing or alternative that does not explicitly state **pure sine wave** should be
rejected regardless of price, VA rating, or brand.

## Hidden ongoing cost

The battery is a **consumable**. Expect a replacement around year 3–4 of the five-year
window at roughly **$50**. Budget for it so it isn't mistaken for a dead unit and replaced
wholesale.

## Do not track

Simulated/stepped sine wave units at any price. Standby (offline) topology units. Units
below 1000 W capacity. Used UPS units — the battery is the expensive part and its remaining
life is invisible from a listing, so a used unit is usually a $50 battery in a $30 box.
