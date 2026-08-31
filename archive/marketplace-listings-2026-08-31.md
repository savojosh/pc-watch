# Facebook Marketplace listings reviewed — 2026-08-31

## Build priorities (from Josh)
- Replacing an Asus laptop w/ RTX 3080 that is thermally buckling
- Must run **large CPU-based AI** projects, compile **multiple Flutter apps**, game at **high** settings (ultra preferred)
- Top priority: **great work CPU** + **great water cooling**
- Secondary goals: workstation/AI-ML, upgradable cheap base, gaming, home server/NAS

## The 8 saved listings

| # | Item | Price | Location | Condition |
|---|------|-------|----------|-----------|
| 1 | Corsair DDR4 32GB (2×16) | $140 (was $160, OBO) | Whitewater | Used ~1 month |
| 2 | Lian Li Lancool 205 Mesh Type-C case + CM Elite 240mm AIO + ARGB fans/hub | $100 | Janesville | Like new (~1 wk use) |
| 3 | AMD Ryzen 7 7800X3D | $300 (was $330) | Elkhorn | New, seal broken, never out of casing |
| 4 | Intel i7-14700KF | $250 (was $270) | Whitewater | Used ~1 month |
| 5 | Corsair Crystal 680X RGB white case + 3× LL140 fans | $160 OBO | East Troy | Used couple years |
| 6 | "PC Parts" lot — keyboard $20, keyboard $80, "Ryzen" $200 NIB, "GeForce RTX" $325 NIB | itemized | Janesville | New |
| 7 | Skytech: RTX 5080 16GB, Ryzen 7 9800X3D, 32GB DDR5-6000, 2TB NVMe, X670/AM5, 360mm AIO, 850W Gold, Win11 | $2,899 OBO | Lake Geneva | Like new |
| 8 | Custom PC: Ryzen 5 3600XT, RX 6650 XT, 32GB, 1TB SSD, X570 AORUS Elite WiFi, ID-Cooling SE-214-XT air, Win11 Pro | $800 (was "$2,000") | Edgerton | Like new, ~12 uses |

## Verdicts

**Buy / negotiate**
- **#4 i7-14700KF @ $250** — 20C/28T. By far the best work-CPU-per-dollar in the set for Flutter builds and CPU inference. Caveats: LGA1700 is a dead-end socket (no upgrade path), and Raptor Lake 13th/14th-gen has the known Vt degradation issue — confirm the seller ran BIOS with the 0x12B microcode and ask for purchase date/receipt for Intel's extended warranty.
- **#2 case + 240mm AIO @ $100** — solid utility buy; Lancool 205 Mesh + CM Elite 240 + fans is roughly break-even to new. But a CM Elite 240 is a budget AIO, not "great water cooling" for a 14700K-class chip.

**Pass**
- **#1 DDR4 32GB @ $140** — badly overpriced; comparable DDR4 kits are far cheaper new, and DDR4 locks you to a dead platform. Skip.
- **#3 7800X3D @ $300** — good price for what it is, but it's an 8-core gaming-first chip. Wrong tool for CPU-AI and parallel compiles.
- **#7 Skytech @ $2,899** — the only turnkey machine, but priced at or above a comparable new prebuilt. Also 8-core. Only interesting if negotiated toward ~$2,200. AM5/X670 is the one genuinely upgradable platform in the set.
- **#8 Custom PC @ $800** — parts total is well under the ask, and an RX 6650 XT is a downgrade from his laptop's 3080. Only compelling as an AM4 donor base at ~$550 or less (X570 + 32GB + 1TB), with a used Ryzen 9 5950X (16C/32T) dropped in later.

**Ask before judging**
- **#5 Corsair 680X @ $160** — dual-chamber, excellent radiator support, genuinely good for a serious cooling build. Fair but not a steal; try $110–130.
- **#6 parts lot** — no model numbers given. Ask which Ryzen and which RTX before anything else.

## Core strategic note
Josh's #1 stated priority (great **work** CPU) conflicts with the X3D chips in this set. X3D parts are gaming-optimized 8-core CPUs. For CPU-based AI and multiple concurrent Flutter builds, what matters is core count, memory bandwidth, and **RAM capacity (64–128GB)** — pointing at a 14700K-class Intel or a Ryzen 9 7950X/9950X on AM5, not an X3D.

*Prices are approximate market estimates and should be re-checked against current listings before offering.*
