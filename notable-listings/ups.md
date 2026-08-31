# Notable listings — UPS

Spec: `../design-spec/ups.md` · Prices: `../market-prices/ups.md`
**Last verified: 2026-08-31**

## Recommendation

**Do nothing yet.** This is deliberately the last part to buy — it does nothing until the
machine is assembled and the trading program is actually running overnight on it. The price
is stable at ~$180 and the unit is widely stocked, so there is no risk in waiting.

Set a passive alert at **$150** and take it if one appears; otherwise buy at ~$180 at the end
of the build.

## Live listings

| Item | Price | Source | Verdict |
|---|---|---|---|
| **CyberPower CP1500PFCLCD** (1500 VA / 1000 W, pure sine) | **~$180** | retail, widely stocked | **The pick** — buy last |
| Same unit, list price | $229.95 | PCPartPicker | Pass — $180 is the real street price |

## Marketplace listings

**None pursued.** Used UPS units are a poor buy: the battery is the expensive part, its
remaining life is invisible from a listing, and a used unit is usually a $50 battery in a
$30 box. If a genuinely cheap local unit appears, price it as *hardware minus a $50 battery
replacement* before deciding.

## The gating spec

**Pure sine wave output.** Any listing or alternative that does not explicitly state pure
sine wave is rejected regardless of price, VA rating or brand. Modern active-PFC power
supplies — including both PSU candidates in this build — can misbehave on the stepped
waveform cheaper units produce, sometimes refusing to transfer to battery at all. A cheap
simulated-sine unit is worse than no UPS, because it presents as protection and isn't.

## Action

1. Passive alert at **CP1500PFCLCD < $150**.
2. Buy at ~$180 once the build is assembled and running.
3. **Then do the actual work:** configure `nut` or CyberPower's Linux daemon to trigger a
   graceful shutdown on battery. An unconfigured UPS just delays the same hard power loss by
   four minutes. Buying it is not finishing it.
4. Wire tower and network gear to the battery outlets; monitors to surge-only.

## Ongoing

Budget **~$50 around year 3–4** for a replacement battery, so a tired battery isn't mistaken
for a dead unit and replaced wholesale.

## Filter rules for the nightly watch

Ignore: simulated/stepped sine wave units · standby (offline) topology · units below 1000 W ·
all used UPS units. This is a low-priority category — do not surface anything here unless it
is the specified model under $150.
