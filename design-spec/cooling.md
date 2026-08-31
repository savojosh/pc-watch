# Design spec — Cooling

## What this part is

The CPU cooler. A stated top-two priority for this build, alongside the CPU itself — the
current laptop is being replaced specifically because it is thermally buckling.

## Hard compatibility constraints

- **AM5 mounting bracket.** Many older coolers are AM4-only or need a separate bracket
- **360 mm radiator**, which the case must physically accept (top or front)
- Radiator thickness + fans must clear the case's top panel and the RAM
- **Water cooling is a stated requirement.** Air coolers do not satisfy it, and no listing
  offering one should be flagged as a match — regardless of price

## Currently aimed-for spec

| Field | Target |
|---|---|
| Type | **360 mm AIO liquid cooler** |
| Socket | AM5 |
| Target part | **Arctic Liquid Freezer III 360** |
| Budget | **$91–100** new; open-box acceptable down to ~$52–61 |

The Liquid Freezer III was already the right answer on the original dream build and it
survives the platform change unchanged — it is the best sustained-load performance per
dollar available, and sustained all-core load is exactly this machine's overnight profile.

Ships with pre-applied thermal paste. **Do not buy separate paste** (the dream build's
$9.99 MX-6 line is free money).

## Why this matters more here than on a typical build

The trading program runs **23:00–10:00 daily** — eleven hours of sustained all-core load,
every night, unattended. It caps at 80% of cores and **throttles on CPU temperature**, so
cooling capacity translates directly into completed work rather than just lower numbers.
This is a workstation thermal problem, not a gaming one.

It also has to stay quiet enough to run overnight, and cool a future Zen 6 X3D on the same
mount in 2027–28.

## The reliability trade, stated plainly

An AIO has a pump, which is a wear part and a single point of failure; a good air cooler has
none and would likely outlive this build. You have chosen water knowingly. Consequences
worth planning for: expect a pump replacement or cooler swap inside the five-year window,
and keep an eye on coolant temps in the first weeks.

## Open-box note

A sealed AIO is a **low-risk open-box buy** — there is nothing to wear out in shipping and
no consumable beyond the pump itself. Newegg open-box has hit $52–61 for this unit. This is
one of the few places in the build where used/open-box carries genuinely little risk.

## Case fans

Not yet specified. The chosen case should come with enough intake fans; buy extras only if
the case ships short. Do not pay for RGB fan bundles as a reason to buy a case.
