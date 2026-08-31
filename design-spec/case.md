# Design spec — Case

## What this part is

The chassis. On this build its job is narrow and specific: accept a 360 mm radiator, move
enough air for an eleven-hour nightly all-core load, and stay out of the way.

## Hard compatibility constraints

- **ATX** motherboard support (the locked MSI board is full ATX)
- **360 mm radiator support** — front or top. **Verify the exact clearance before buying**;
  this is the single most common mistake in a build like this
- GPU length clearance for a ~330 mm card
- Radiator + fan thickness must not collide with the top DIMM slots

## What is NOT required (decided 2026-08-31)

**3.5" drive bays.** The NAS is a separate box, built later. This build is all-NVMe. That
decision frees the case choice substantially and rules the Fractal North XL's limited bay
count irrelevant rather than a problem.

## Currently aimed-for spec

| Field | Target |
|---|---|
| Form factor | ATX mid tower |
| Airflow | **High-airflow mesh front** — not a solid/glass front panel |
| Radiator | 360 mm, front or top |
| Candidates | **Lancool 216**, Montech Air 903 Max, Phanteks G400A |
| Budget | **$85–100** |

This is a stable, healthy market with no shortage pressure. Buy on any ordinary sale.

## Why mesh, not glass

The thermal requirement here is unusual: sustained all-core load overnight, every night,
with the CPU throttling on temperature. A restrictive front panel costs real degrees, which
costs completed work. Aesthetics are secondary to this and the machine will mostly be
running unattended anyway.

## Listings under consideration — assessment

Two cases have come up on Marketplace. Both are still plausible under the new architecture,
since a case is platform-agnostic:

- **Lian Li Lancool 205 Mesh + CM Elite 240 AIO + fans, $100 (Janesville).** Good utility
  value, roughly break-even against new. **But the bundled 240 mm AIO does not meet the
  cooling spec** — it is a budget unit and undersized for a 12-core chip under sustained
  load. Treat this as a ~$100 case purchase with a spare cooler, not as a cooling solution.
- **Corsair Crystal 680X + 3× LL140, $160 OBO (East Troy).** Dual-chamber with genuinely
  excellent radiator support — a good fit for a serious cooling build. Fair, not a steal.
  Try $110–130. Note it is a glass-front design, which cuts against the airflow preference.

## Checklist before buying any case

1. Confirmed 360 mm radiator clearance, in the specific position you plan to mount it
2. GPU clearance ≥ 330 mm
3. Front panel is mesh or otherwise unrestrictive
4. Enough included fans that you are not immediately buying more
5. Front-panel USB-C, if you want it — cheap to have, annoying to lack
