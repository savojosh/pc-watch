# Design spec — PSU

## What this part is

The power supply. The one component whose failure can take other components with it, and
the one most worth not economizing on — while also being a part the original dream build
badly over-specified.

## Hard compatibility constraints

- **ATX** form factor (standard, fits any of the candidate cases)
- **ATX 3.1** — current standard, handles transient spikes properly
- PCIe 8-pin connectors for an AMD GPU (no 12V-2x6 requirement on an AMD card, though
  having one costs nothing and keeps a future NVIDIA option open)
- **Fully modular** — meaningfully easier to build and to keep airflow clean

## Currently aimed-for spec

| Field | Target |
|---|---|
| Wattage | **750 W** |
| Efficiency | 80+ Gold |
| Standard | ATX 3.1 |
| Cabling | Fully modular |
| Candidates | PCCooler CPS KN750, Cooler Master MWE Gold V2 |
| Budget | **$75–80** |

## Wattage reasoning

A Zen 5 12-core plus a 16 GB RDNA GPU peaks around **550 W**. 750 W leaves genuine headroom
for a substantially larger GPU in the 2028–29 upgrade slot without replacing the PSU — which
is the point, on a five-year build.

**The dream build's 1000 W Titanium at $214.90 was over-specified by roughly $135.** The
counter-argument for keeping it — headroom for a much bigger GPU later — is real but does
not justify the premium at 750 W's price point. If a future GPU genuinely needs more than
750 W, buying a second PSU in 2029 will still cost less than the difference today.

Do not go below 750 W. The savings are trivial and the headroom is the entire point.

## Efficiency reasoning

Gold is the right stopping point. Platinum and Titanium cost real money for a few percent,
and the payback period at residential rates is longer than the build's life.

That said, this machine runs **eleven hours a night, every night**, under sustained load —
so efficiency is worth marginally more here than on a typical desktop. It is not worth
$135.

## Market note

Healthy market, no shortage pressure. The earlier $115 estimate was pessimistic; $75–80
buys a fully modular Gold ATX 3.1 unit. Buy on any ordinary sale.

## Do not buy

Used PSUs. This is the one part where the no-heavily-used rule should be absolute — a
degraded unit fails in ways that damage everything downstream, and the savings are small.
Buy this one new, with its warranty.
