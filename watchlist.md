# PC Deal Watch — Watchlist

Owner: Josh, Whitewater WI. **Rewritten 2026-08-31** for the locked AM5 architecture.
This file is the nightly task's entry point. It is deliberately short — the detail lives in
the folders it points to.

---

## Read these first, every run

| Read | For |
|---|---|
| `design-spec/00_architecture.md` | The compatibility contract. **A listing that conflicts with it is not a deal.** |
| `design-spec/<part>.md` | Exact slot/interface requirements for the part in question |
| `market-prices/<part>.md` | Observed prices and the **buy triggers** — these define "meaningful drop" |
| `notable-listings/<part>.md` | What's already been surfaced, and the standing recommendation |
| `ledger.md` | Everything already seen and every price recorded. Append here. |

Part files exist for: `motherboard`, `cpu`, `ram`, `gpu`, `storage`, `cooling`, `case`,
`psu`, `ups`. Whole machines and mixed lots go in `notable-listings/whole-systems.md`.

---

## The locked architecture — hard filters

**Socket AM5 · MSI MAG B850 Tomahawk MAX WiFi · DDR5 · Bazzite · 5-year lifecycle.**

**GPU vendor is now open.** Bazzite supports AMD and NVIDIA both. AMD is still the pick on
price and Linux driver quality, not on compatibility — evaluate NVIDIA cards, don't filter
them out. A 16 GB NVIDIA card meaningfully under $470 is a legitimate buy.

Reject on sight, at any price:

- ❌ **DDR4** anything — does not fit AM5
- ❌ **AM4, LGA1700, LGA1851** CPUs and motherboards
- ❌ **Air coolers** — water cooling is a stated hard requirement
- ❌ **Used PSUs**, at any price, from any seller
- ❌ **Used SSDs**; DRAM-less, QLC, or Gen5 drives
- ❌ GPUs under 16 GB VRAM
- ❌ Boards with fewer than 4 DIMM slots

No 3.5" drive bay or HBA requirement — the NAS is a separate box, built later.

## Budget

Tower target **$1,000–1,500**, stretch **$1,500–2,500**. Realistic build currently prices at
**~$1,926** (~$2,170 all in). Running total and cut sequence: `market-prices/00_budget-ledger.md`.

Buying incrementally — a single great part deal is in scope even when the whole build isn't.

## Buying rules

- Used is fine; **heavily used is not**. Sellers must have good ratings.
- **Search radius: 40 mi of Whitewater WI** (widened 2026-08-31 — the 20 mi market had
  essentially no AM5 parts at all). Reaches Madison, Milwaukee, Rockford, Crystal Lake IL.
- **Always flag the drive on anything beyond ~25 mi.** Fuel at $5/gal and 24–27 mpg works out
  to roughly **$0.40 per mile of one-way distance, round trip**. So a 50-mile-away part
  carries ~$20 of fuel; quote the real price as asking + drive.
- **Micro Center = Westmont IL**, 200 mi round trip. Factor **$66 all-in** (fuel, tolls, and
  the IL-vs-WI sales tax difference) before calling anything a saving.
- Private-party sales in Illinois carry no sales tax — only fuel and tolls apply.

## Market conditions

- **DDR5 and NAND are in an AI-driven shortage** — ~3–5× their all-time lows, no relief
  expected before December. Black Friday discounts a percentage off an inflated price.
- **RDNA 3 GPUs are inverted** — new cards sell above their own used prices. Never pay
  $799–895 for a new 7900 GRE or 7800 XT.
- **CPUs, boards, cases, PSUs, coolers are healthy.** No urgency in those categories.

## Sources — split by who checks them

**The nightly cloud task (6pm CST, automated):** Micro Center, Newegg, Amazon, Best Buy,
B&H · Reddit r/buildapcsales and r/hardwareswap · Slickdeals PC hardware · Newegg
**open-box** specifically for the Arctic Liquid Freezer III 360.

**Live sessions with Claude (on request):** Facebook Marketplace, ~20 mi of Whitewater.
The scheduled task cannot reach Marketplace — it is login-walled and the task could not be
bound to a computer with a signed-in browser. Instead the nightly report ends with a line
naming which parts are worth a local sweep, and those sweeps are done interactively.

## Highest-value finds

Ranked by how much they'd actually change the build:

1. **Used DDR5-6000 2×32 GB from a rated seller ≤ $600** — the best single find available
2. **A used AM5 system with 64 GB DDR5 under $1,400** — would beat the staged parts plan outright
3. **Micro Center AM5 3-in-1 bundle ≤ $700** — the biggest standing lever
4. **Arctic Liquid Freezer III 360 open-box ≤ $65**
5. **2 TB Gen4 NVMe with DRAM ≤ $250** — un-defers the second drive
