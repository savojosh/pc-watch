# Priorities — UPS

## What I actually want from this part

Insurance for the overnight run. The trading program works 23:00–10:00 with nobody watching;
a brief outage at 03:00 costs an entire night's work and leaves the filesystem dirty on a
machine I'm not sitting at.

## Ranked priorities

1. **Pure sine wave output.** Non-negotiable — see below.
2. **Enough runtime for a clean automated shutdown.** Minutes, not hours.
3. **Linux-controllable**, so the shutdown is actually automatic.
4. Capacity beyond that. Not needed.

## Realistic expectations

- **This is not about riding out an outage.** A ~550 W system on a 1000 W unit buys several
  minutes. That's enough to shut down gracefully, which is the entire job. Expecting to keep
  working through a blackout would mean buying something much larger and more expensive.
- **Pure sine wave is a hard requirement, not an upgrade.** Modern active-PFC power supplies
  — including every candidate on my list — can misbehave on the stepped waveform cheaper
  units produce, sometimes refusing to switch to battery at all. A cheap UPS here is worse
  than no UPS, because it looks like protection and isn't.
- **Buying it is not finishing it.** An unconfigured UPS just delays the same hard power
  loss by four minutes. It needs `nut` or CyberPower's Linux daemon set up to trigger a
  graceful shutdown on battery. That configuration is the actual deliverable.
- **The battery is a consumable.** Expect to replace it around year 3–4 of the five-year
  window — budget ~$50 rather than being surprised into a whole new unit.
- **Stable market at ~$180.** No urgency, no shortage.

## Wiring intent

Tower and network gear on the battery outlets. Monitors on surge-only — they're useless
during an unattended overnight run and they drain the battery fast.

## What I'd trade away

Runtime. LCD features. Capacity above 1500 VA. Rack mounting.

## What I would not trade

Pure sine wave, or skipping the shutdown configuration.

## Purchase timing

**Buy last.** It's the most deferrable item in the build, its price is stable, and it does
nothing until the machine is assembled and the trading program is actually running on it.
Deferring it is the second-cleanest budget cut available, after the data SSD.
