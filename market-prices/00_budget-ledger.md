# 00 — Budget ledger

**Index into the per-part price files, and the sanity check on total build cost.**
No specific parts or listings here by design — this file exists to answer two questions:
*is the realistic build's cost drifting?* and *is the dream build still fantasy?*

Last reconciled: **2026-08-31**

---

## The two builds

| | Realistic build | Dream build (retired architecture) |
|---|---|---|
| Platform | AM5 · B850 | LGA1851 · Z890 |
| Total | **~$1,926** + $180 UPS = **~$2,106** | **~$4,000–4,400** |
| Vs. target ($1,000–1,500) | **Over by $426–926** | Over by 3× |
| Vs. stretch ($1,500–2,500) | **Inside** | Far outside |

The dream build's *parts* are retired with LGA1851, but the number is kept here as the
reality check it has become: it was never a $1,500 machine, and roughly $1,000 of the gap
was RAM and Gen5 storage that this build deliberately does not buy.

---

## Realistic build — running total

| Part | File | Budgeted | Confidence |
|---|---|---|---|
| CPU + motherboard + 32 GB RAM | [cpu](cpu.md) · [motherboard](motherboard.md) · [ram](ram.md) | **$650** (Micro Center bundle) | Medium — bundles rotate |
| GPU | [gpu](gpu.md) | **$470** | Good |
| Boot SSD 1 TB | [storage](storage.md) | **$239** | Good, but shortage-driven |
| Data SSD 2 TB | [storage](storage.md) | **$299** | Good, but shortage-driven |
| Cooler | [cooling](cooling.md) | **$95** | Good |
| PSU | [psu](psu.md) | **$78** | Good |
| Case | [case](case.md) | **$95** | Good |
| **Subtotal** | | **$1,926** | |
| UPS | [ups](ups.md) | **$180** | Good |
| Micro Center trip (fuel, tolls, IL tax) | — | **$62–66** | Good |
| **All in** | | **~$2,170** | |

---

## Where the money actually goes

| Category | Share | Note |
|---|---|---|
| Storage + RAM | **~40%** | Both in an AI-datacenter shortage. This is the distortion. |
| CPU + board | ~34% | The one healthy market, and where the bundle lever is |
| GPU | ~24% | Inverted market — new RDNA 3 sells above used |
| Case + PSU + cooler | ~14% | Stable, unremarkable, buy on any sale |

## Cut sequence, if $2,170 is too much

Apply in order. Each step names what it actually costs you.

| Cut | Saves | What it costs |
|---|---|---|
| 1. Defer the 2 TB data SSD | **−$299** | Breaks the two-drive plan temporarily. Partition the 1 TB as a stopgap. This is the worst dollar in the build — $299 for a drive that floored at $93. |
| 2. Defer the UPS | **−$180** | Already the plan. No overnight-run protection until bought. |
| **Running total** | **$1,690** | Close to the stretch target, and both deferred parts are the ones whose prices should improve |

**Do not cut RAM.** 32 GB is already the floor for SteamOS + a Windows VM + the trading
process. The second kit will cost more later, not less. If something must give beyond the
two cuts above, it should be GPU tier — not memory.

## Market conditions to keep watching

- **DDR5:** ~300% up in six months. Gartner forecasts ~130% memory cost surge through 2026.
- **NAND:** same story. Storage is ~2.5× earlier estimates.
- **Neither is expected to ease before December.** Black Friday discounts a percentage off
  an inflated price; it does not undo a shortage.
- **RDNA 3 GPUs:** end-of-life and scarce. New prices exceed used prices.
- **CPUs and boards:** healthy. No urgency.

## Reconciliation rule

When any per-part file's "current best" moves more than 10%, update the table above and
re-date this file. If the subtotal crosses **$2,500**, the build has left the stretch budget
and something in the cut sequence needs applying.
