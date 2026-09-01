# Design spec — RAM

## What this part is

System memory. On this build it is the **binding constraint** — the part most likely to be
what actually stops you, and the part whose market is worst right now.

## Hard compatibility constraint

**DDR5 UDIMM, non-ECC.** The locked board has 4 DDR5 slots.

**This rules out every DDR4 kit**, including the Corsair DDR4 32 GB listing at $140 that has
been under consideration. DDR4 does not fit AM5 and never will. Delete it from the watchlist.

## Currently aimed-for spec

| Field | Target |
|---|---|
| Type | DDR5 UDIMM, non-ECC |
| Speed | **DDR5-6000** |
| Timing | **CL30** target — but the Plan A bundle ships **CL36**, which is accepted |
| Profile | **EXPO** (AMD's profile; XMP-only kits usually train but EXPO is the safe buy) |
| Config now | 2 × 32 GB (leaves 2 slots free) |
| Config target | 64 GB |
| Ceiling | 128 GB (4 × 32 GB) — board supports 256 GB |

**Buy 2 × 32 GB, not 4 × 16 GB.** Two sticks now keeps the upgrade path to 128 GB open. Four
sticks caps you at 64 GB forever without throwing kits away.

## Why DDR5-6000 CL30 specifically

It is the AM5 sweet spot — it matches the memory controller's 1:1 FCLK ratio. Faster kits
cost more and often train down. This is not a place to spend extra.

**On CL36 in the Plan A bundle.** The G.Skill Flare X5 kit in the Micro Center bundle is
DDR5-6000 **CL36**, not CL30. The looser timing costs a low single-digit percentage in
latency-sensitive work and essentially nothing in the capacity-bound workloads that dominate
here. **Accepted deliberately** — it is not worth paying separately for CL30 when the kit
arrives inside a bundle that is already the best value in the build. Noted so it is a known
deviation rather than a surprise.

**Micro Center prices this kit at $479.99 standalone**, well above the $404 best-tracked
price. The bundle is the cheap route to RAM; buying it there alone is not.

## The 4-DIMM speed caveat

AM5 runs 4 populated DIMM slots at reduced speed (~4800–5200 rather than 6000). This is a
real effect but a **low-cost one for this workload**: concurrent builds, VMs and emulators
are *capacity*-bound, not bandwidth-bound. Losing some bandwidth to gain 32 GB is a good
trade here. It costs a little in gaming, where you are not bandwidth-limited anyway.

## Why 64 GB is the real target

Measured and estimated concurrent pressure:

| Consumer | Footprint |
|---|---|
| Dart analysis server | 2–6 GB **per open project** |
| Gradle daemon | 2–4 GB per concurrent build |
| Android emulator | 2–4 GB each (4 AVDs exist today, ~30 GB on disk) |
| Windows 11 VM | 8–16 GB dedicated |
| Trading program NNs | one thread per net, capped at 80% of cores |
| SteamOS host + browser + Claude Code | several GB |

32 GB is a **floor you will hit weekly**, not a comfortable configuration. It is workable
only if you avoid running the Windows VM and multiple Claude Code instances simultaneously.

## Market warning

DDR5 is in an AI-datacenter-driven shortage — roughly 300% up in six months, with Gartner
forecasting a ~130% memory cost surge through 2026. A 64 GB kit that bottomed at $159 is
~$869 today.

**Consequences:** buy RAM early rather than late; nothing suggests a drop before December;
used DDR5 is worth watching for the first time ever; and **do not cut RAM to save money** —
the second kit will cost more later, not less.
