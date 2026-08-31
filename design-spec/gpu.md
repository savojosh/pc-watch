# Design spec — GPU

**Updated 2026-08-31 for Bazzite.** The AMD-only constraint is GONE.

## What this part is

The graphics card. Drives the 21:9 ultrawide. Because the AI work here is CPU-based, it does
essentially nothing for the professional workload today.

## Hard compatibility constraints

1. **PCIe 5.0 x16 slot** on the locked board. Any PCIe card fits and is backward compatible;
   generation is not a constraint.
2. **Either vendor.** Bazzite ships both AMD and NVIDIA images. This replaces the previous
   AMD-only rule, which existed solely because SteamOS has no NVIDIA support (Valve says
   full NVIDIA support is unlikely before 2027).
3. **Physical clearance** — length and slot height against the chosen case, ~330 mm.
4. **16 GB VRAM minimum.**

## Currently aimed-for spec

| Field | Target |
|---|---|
| Vendor | Either — judged on price and Linux driver quality |
| VRAM | **16 GB** |
| Primary pick | **RX 9060 XT 16 GB, new** — ~$470 |
| Value alternative | RX 7800 XT 16 GB, used — ~$460 |
| Stretch | RX 7900 GRE 16 GB — ~$575 used |
| Budget ceiling | $500 |

## Why still AMD, despite NVIDIA now being allowed

The pick did not change, but **the reason did**. It is no longer a compatibility requirement;
it is a market judgment, and it should be re-examined whenever prices move:

- **NVIDIA's 50-series is caught in the same memory shortage** as DDR5 and NAND. There is no
  bargain waiting there — expect to pay more for equivalent VRAM.
- **AMD's open-source Linux drivers remain better** than NVIDIA's on Wayland, and RDNA 4 is
  well supported (Mesa 26.0 brought further RDNA 4 gains). NVIDIA on Linux is far better than
  it was, but AMD is still the lower-friction path.
- At ~$470 for 16 GB, the RX 9060 XT has no NVIDIA equivalent at that price.

**If an NVIDIA card with 16 GB appears meaningfully below $470, it is now a legitimate buy.**
That was not true a day ago. The nightly deal watch should evaluate NVIDIA rather than
filtering it out.

## The CUDA question — now open rather than closed

Previously this build accepted "no CUDA, ever" as the price of SteamOS. **Bazzite removes
that lock-in.** The AI work is CPU-based today so it costs nothing either way, but if that
work ever moves to GPU acceleration, the 2028–29 upgrade can be an NVIDIA card with full
CUDA support. The five-year path is no longer vendor-committed.

## Performance target

Monitor is a 21:9 curved Dell ultrawide — **3440×1440 or 3840×1600, still unconfirmed**.
Either sits near 6 MP; all three candidate cards cover both. Ultrawide support is a non-issue
at the OS layer on Bazzite.

- Normal gaming: 90 FPS, would like **120 FPS**
- Strategy games: **capped at 60 FPS by choice** — game speed over looks
- **Cities: Skylines II will not reach 120 FPS on any OS or card.** Its performance problems
  are cross-platform. The 60 FPS cap is the correct answer there.

## Market warning

RDNA 3 cards are end-of-life and scarce, producing an inverted market:

| Card | New | Used | Launch MSRP |
|---|---|---|---|
| RX 7900 GRE 16 GB | $799 | $575 | $550 |
| RX 7800 XT 16 GB | $895 | $460 | $499 |
| RX 9060 XT 16 GB | **$470** | — | $349 |

**New RDNA 3 cards sell above their own used prices.** Never pay $799–895 for a new 7900 GRE
or 7800 XT — that is a scarcity tax, not a price.

## Buying checklist for used cards

Test in person. Rated seller, photos of the actual card, POST or benchmark video. Check for
mining wear and repasting. No exceptions.

## HDR note

HDR works on Bazzite via gamescope and KDE Plasma 6, but it is the most regression-prone area
in the stack — there are open gamescope issues tied to specific Plasma versions. Bazzite's
atomic rollback means you can escape a bad combination yourself rather than waiting on a
vendor. Test HDR on your specific monitor before relying on it.
