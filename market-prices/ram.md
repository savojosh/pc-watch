# Market prices — RAM

Spec: `../design-spec/ram.md` · Target: **2 × 32 GB DDR5-6000 CL30 EXPO**

**Market health: CRISIS. Worst market in the build.**
**Budget: $404 (32 GB) / $869 (64 GB)**

## Observed prices

| Date | Part | Best price | All-time low | Multiple |
|---|---|---|---|---|
| 2026-08-27 | DDR5-6000 **32 GB** kit | **$404** | $72 | **5.6×** |
| 2026-08-27 | DDR5-6000 **64 GB** kit | **$869** | $159 | **5.5×** |

Source: Tom's Hardware price trackers, updated 24–27 Aug 2026.

## What is happening

AI datacenter demand has driven a memory shortage. DDR5 is up roughly **300% in six months**.
Gartner forecasts a **~130% memory cost surge through 2026**. Nothing in the current data
suggests relief before December.

This single line item is why the realistic build cannot reach the $1,000–1,500 target. RAM
is roughly a third of the build's cost at these prices. At the all-time low, 64 GB would
have been $159 — the difference between that and $869 is most of the budget overrun.

## Strategy under shortage

1. **Buy early, not late.** Waiting has cost money every month this year. The usual advice —
   wait for a sale — is actively wrong in this market.
2. **A Micro Center bundle includes 32 GB.** Given a $404 standalone kit price, that's most
   of the bundle's value. This is the cheapest route to the first 32 GB by a wide margin.
   See `cpu.md`.
3. **Watch used DDR5.** For the first time ever this is worth doing. Secondhand DDR5 has
   historically been pointless to track; at 5.5× the floor it is not.
4. **Do not buy 4 × 16 GB** to save money now. It caps the machine at 64 GB permanently.

## Buy triggers

- **32 GB kit at ≤ $400**: buy.
- **32 GB kit at ≤ $350**: strong buy, this would be a genuine break in the trend.
- **64 GB kit at ≤ $850**: buy if the budget allows.
- **Used 2 × 32 GB DDR5-6000 from a rated seller at ≤ $600**: flag immediately. This is the
  most valuable single find the deal watch could produce.
- **Any meaningful downward trend** across two consecutive weeks: notable, report it.

## Do not track

**All DDR4, at any price.** It does not fit AM5. This specifically retires the Corsair
DDR4 32 GB listing at $140 that was previously under consideration — it was overpriced for
DDR4 *and* incompatible.

Kits above DDR5-6000, and ECC/RDIMM server memory.
