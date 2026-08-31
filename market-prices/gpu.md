# Market prices — GPU

Spec: `../design-spec/gpu.md` · Target: **RX 9060 XT 16 GB new**, ~$470

**Market health: INVERTED.** New RDNA 3 cards sell above their own used prices.
**Budget: $470, ceiling $500**

## Observed prices — 2026-08-31

| Card | New | Used (eBay avg) | Launch MSRP | New vs MSRP |
|---|---|---|---|---|
| RX 7900 GRE 16 GB | $799 (Amazon) | **$575** | $550 | +45% |
| RX 7800 XT 16 GB | $895 (Amazon) | **$460** | $499 | +79% |
| RX 9060 XT 16 GB | **$470** (PowerColor Reaper, Amazon) | — | $349 | +35% |

## Reading this table

**New RDNA 3 cards cost more than used ones.** The 7800 XT is $895 new and $460 used. That
is not a premium for warranty — it is an end-of-life scarcity tax on cards that are no
longer being made in volume.

The practical consequence: the **new 9060 XT at $470 and the used 7800 XT at $460 are the
same money.** The new card wins on warranty, zero wear, current-generation drivers, and it
satisfies the no-heavily-used-parts rule outright.

The 7900 GRE is roughly 25–30% faster at ~6 MP ultrawide, but costs $105 more used with
unknown history — or $329 more new, which is indefensible.

## Buy triggers

- **RX 9060 XT 16 GB new at ≤ $450**: strong buy, below current market.
- **RX 9060 XT 16 GB new at ≤ $470**: buy, this is the plan.
- **RX 7800 XT 16 GB used at ≤ $420** from a high-rated seller with photos and a POST or
  benchmark video: competitive alternative, flag it.
- **RX 7900 GRE 16 GB used at ≤ $500**: flag — this is the stretch pick at a fair price.

## Hard price ceilings — do not exceed

- **Never pay $799–895 for a new 7900 GRE or 7800 XT.** Under any circumstances. That is
  scarcity pricing on obsolete stock.
- Nothing above $500 without a specific reason.

## NVIDIA — now in scope (changed 2026-08-31)

The host OS is Bazzite, which supports NVIDIA. **The AMD-only filter is removed.** NVIDIA
cards should be priced and evaluated, not skipped.

Expect no bargain, though: NVIDIA's 50-series is caught in the same memory shortage driving
DDR5 and NAND. AMD remains the pick on price and on Linux driver quality (better Wayland
behaviour, better open-source drivers), not on compatibility.

- **Any 16 GB NVIDIA card at ≤ $450**: flag it — that would beat the RX 9060 XT on price and
  reopen CUDA for the future AI work.
- Above $470, AMD wins on both price and driver friction.

## Do not track

Cards below 16 GB VRAM. Mining-farm cards regardless of price or apparent condition.
