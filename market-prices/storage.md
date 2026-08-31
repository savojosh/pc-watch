# Market prices — Storage

Spec: `../design-spec/storage.md` · Target: **1 TB + 2 TB Gen4 NVMe with DRAM**

**Market health: CRISIS.** Same AI-driven NAND shortage as DDR5.
**Budget: $239 (1 TB) + $299 (2 TB) = $538**

## Observed prices — 2026-08-24/27

| Part | Best price | All-time low | Multiple | Earlier estimate |
|---|---|---|---|---|
| **1 TB Gen4** (Samsung 990 Pro) | **$239** | $59 | **4.1×** | $100 — **off by +$139** |
| **2 TB Gen4** (Crucial P310) | **$299** | $93 | **3.2×** | $190 — **off by +$109** |
| 2 TB Gen4 (WD SN850X) | $328 | $89 | 3.7× | — |

Source: Tom's Hardware price trackers.

Storage is now roughly **2.5× the original build estimate.** This single category is what
turned a ~$1,690 build into a ~$1,926 one.

## The Black Friday trap

The original plan was "buy SSDs on Black Friday, they discount hardest." **That reasoning
does not survive a shortage.** Black Friday discounts a percentage off an inflated price; it
does not undo the supply situation that created the inflation. A 20% Black Friday discount
on a $299 drive is $239 — still 2.6× its floor.

If anything, buy storage **sooner rather than later, and buy less of it.**

## Strategy

1. **Buy the 1 TB boot drive when you're ready to install.** It's needed to have a machine.
2. **Buy the 2 TB data drive only if it breaks $250.** Otherwise defer — partition the 1 TB
   as a stopgap. This is the single cleanest budget cut available.
3. **Check the tracker every two weeks**, not daily. This market moves slowly.
4. **Do not substitute a DRAM-less Gen5 drive because it's cheaper per GB.** The whole
   storage argument in this build is that onboard DRAM matters more than bus speed for
   emulator images and Gradle churn.

## Buy triggers

- **1 TB Gen4 with DRAM at ≤ $200**: buy.
- **1 TB Gen4 with DRAM at ≤ $160**: strong buy, meaningful break in trend.
- **2 TB Gen4 with DRAM at ≤ $250**: buy — this is the deferral threshold.
- **2 TB Gen4 with DRAM at ≤ $200**: strong buy.
- **Any sustained two-week downward trend**: notable, report it.

## Do not track

DRAM-less drives (including the Crucial P510 from the original dream build) — the spec
requires onboard DRAM. QLC drives. Gen5 drives, which cost more for speed this workload
cannot use. Used SSDs, where remaining write endurance is invisible from a listing.
