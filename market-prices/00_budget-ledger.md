# 00 — Budget ledger

**Index into the per-part price files, and the sanity check on total build cost.**
No specific listings here by design — this file answers two questions: *is the build's cost
drifting?* and *is the dream build still fantasy?*

Last reconciled: **2026-08-31**, against live Micro Center pricing.

---

## ⚠ Correction — the budget went up $382

An earlier version of this file put the build at **~$2,170**, using a Micro Center bundle
price of **$649.98**. That figure came from a **February 2026 article**, not a live listing.

The live bundle is **$999.99**. The old number was stale by $350 and should not be used.
This file now reflects prices verified on Micro Center's site on 2026-08-31.

Micro Center also prices the 32 GB DDR5-6000 kit at **$479.99** standalone, well above the
$404 best-tracked price used elsewhere in these files. The bundle is the cheap route to RAM;
buying it there alone is not.

---

## The two plans

Both are AM5 / B850 / DDR5. Only CPU and board differ; every other line is identical.

| | **Plan A — bundle** | **Plan B — backup** |
|---|---|---|
| CPU | Ryzen 9 **9950X** (16C/32T, 170 W) | Ryzen 9 9900X (12C/24T, 120 W) |
| Board | ASUS ProArt B850-Creator WiFi NEO | MSI MAG B850 Tomahawk MAX WiFi |
| RAM | 32 GB DDR5-6000 **CL36** | 32 GB DDR5-6000 CL30 |
| CPU+board+RAM | **$999.99** (bundle) | **$994** (separate) |
| Acquisition | In-store, Westmont IL, +$66 trip | Shipped, no trip |
| Risk | **Bundle may sell out.** Limit 1/household | None — stock is routine |

## Running total

| Part | File | Plan A | Plan B |
|---|---|---|---|
| CPU + motherboard + 32 GB RAM | [cpu](cpu.md) · [motherboard](motherboard.md) · [ram](ram.md) | **$999.99** | **$994** |
| Micro Center trip (fuel, tolls, IL tax) | — | $66 | — |
| GPU | [gpu](gpu.md) | $470 | $470 |
| Boot SSD 1 TB | [storage](storage.md) | $239 | $239 |
| Data SSD 2 TB | [storage](storage.md) | $299 | $299 |
| Cooler | [cooling](cooling.md) | $95 | $95 |
| PSU | [psu](psu.md) | $78 | $78 |
| Case | [case](case.md) | $95 | $95 |
| Intel 2.5GbE add-in NIC | [motherboard](motherboard.md) | $30 | $30 |
| **Subtotal** | | **$2,372** | **$2,300** |
| UPS | [ups](ups.md) | $180 | $180 |
| **All in** | | **~$2,552** | **~$2,480** |

**Plan A costs ~$72 more and buys four more cores**, a CPU-attached Gen5 x8 secondary slot,
and dual 5GbE. That is the best value in the entire build.

## Against the budget

| | |
|---|---|
| Target | $1,000–1,500 |
| Stretch | $1,500–2,500 |
| Plan A all-in | **$2,552 — just outside the stretch ceiling** |
| Plan B all-in | **$2,480 — at the ceiling** |

Both need at least one cut to sit comfortably inside the stretch range.

## Cut sequence

Apply in order. Each names what it actually costs.

| Cut | Saves | What it costs |
|---|---|---|
| 1. Defer the 2 TB data SSD | **−$299** | Breaks the two-drive plan temporarily; partition the 1 TB as a stopgap. **The worst dollar in the build** — $299 for a drive that floored at $93 |
| 2. Defer the UPS | **−$180** | Already the plan. No overnight-run protection until bought |
| 3. Defer the Intel NIC | **−$30** | Only buy it if the Realtek NIC actually misbehaves on Linux. May never be needed |
| **Plan A after cuts** | | **~$2,043** |
| **Plan B after cuts** | | **~$1,971** |

**Do not cut RAM.** 32 GB is already the floor for Bazzite + a Windows VM + the trading
process, and the second kit will cost more later, not less. If more must go after the three
cuts above, the GPU tier is next — not memory.

## Where the money goes (Plan A)

| Category | Share | Note |
|---|---|---|
| CPU + board + RAM | ~42% | One bundle. Also the best-value line |
| Storage | ~21% | AI-driven NAND shortage, ~3–4× floor prices |
| GPU | ~18% | Inverted market — new RDNA 3 sells above used |
| Case + PSU + cooler + NIC | ~12% | Stable, unremarkable |
| UPS | ~7% | Buy last |

## Market conditions

- **DDR5 and NAND remain in an AI-driven shortage**, roughly 3–5× all-time lows, with no
  relief expected before December. Black Friday discounts a percentage off an inflated price.
- **RDNA 3 GPUs are inverted** — new cards sell above their own used prices.
- **CPUs, boards, cases, PSUs, coolers are healthy.** No urgency there.

## Reconciliation rules

- When any per-part file's "current best" moves more than 10%, update this table and re-date it.
- **If the Plan A bundle disappears, switch to Plan B and re-date this file.** Bundles rotate
  weekly; confirm stock by phone before driving.
- If a subtotal crosses **$2,600**, something in the cut sequence needs applying.
- **Never carry a price from an article into this file as if it were live.** That mistake
  understated this build by $382.
