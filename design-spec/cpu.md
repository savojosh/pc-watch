# Design spec — CPU

## What this part is

The processor. On this build it is the part that actually determines whether concurrent
Flutter builds, the overnight trading neural nets, and a Windows VM can run at the same
time without fighting each other.

## Hard compatibility constraint

**Socket AM5 only.** Anything else does not physically fit the locked motherboard.

This rules out several parts previously under consideration:
- Intel i7-14700KF (LGA1700) — also a dead-end socket with the Raptor Lake Vt degradation issue
- Intel Core Ultra 9 285K (LGA1851) — the old dream-build chip
- Any Ryzen 5000-series (AM4)

## Currently aimed-for spec

| Field | Target |
|---|---|
| Socket | AM5 |
| Generation | Zen 5 (Ryzen 9000) preferred; Zen 4 (7000) acceptable |
| Cores | **12C/24T minimum** |
| **PLAN A (primary)** | **Ryzen 9 9950X — 16C/32T, 170 W**, via the Micro Center bundle |
| **PLAN B (backup)** | **Ryzen 9 9900X — 12C/24T, 120 W**, bought standalone at ≤ $360 |
| Plan B alternate | Ryzen 9 7900X (12C/24T, Zen 4) at ≤ $300 |
| Integrated graphics | **Required** — lets the machine boot and work before the GPU arrives |
| Budget | Inside the $999.99 bundle, or $300–360 standalone |

### Plan A — the bundle, and why it changed the target

[Micro Center product 5007458](https://www.microcenter.com/product/5007458/amd-ryzen-9-9950x,-asus-b850-creator-proart-wifi-am5,-gskill-flare-x5-series-32gb-ddr5-6000-kit,-computer-build-bundle):
**9950X + ASUS ProArt B850-Creator + 32 GB DDR5-6000 CL36 = $999.99** (reg $1,264.97).
**In-store only, limit 1 per household.** Westmont IL, ~$66 round trip all-in.

Micro Center offers **no 9900X bundle at all** — their Ryzen 9 tier starts at the 9950X. The
comparison that decided it:

| | Plan B, bought separately | Plan A bundle |
|---|---|---|
| CPU | 9900X ~$360 (12C/24T) | **9950X ~$490 (16C/32T)** |
| Board | Tomahawk $230 | ProArt $295 |
| RAM | 32 GB CL30 ~$404 | 32 GB CL36 |
| **Total** | **~$994** | **$999.99** |

**Six dollars for four more cores**, plus a better board. Even adding the $66 trip it is
~$72 for a 33% core-count increase on the workload that justifies the whole build.

**The cost of 16 cores: 170 W vs 120 W.** On a machine that runs 11 hours nightly and
throttles on temperature, that raises the stakes on the 360 mm AIO — it does not change the
answer, but it makes the cooler non-negotiable.

**Before driving:** phone store #081 and confirm the bundle is in stock. Bundles rotate
weekly and the website defaults to a different store.

**BIOS setting to remember: enable SVM / AMD-V** for the Windows VM and Android emulators.

## Why 12 cores, and why not X3D

The workload splits in two, and they want different things:

- **Latency work** — Dart analysis server, hot reload, agentic `flutter analyze` loops.
  Largely single-threaded, dominated by clock speed and warm RAM state. **More cores does
  not help this.**
- **Throughput work** — several apps building at once, Android emulators, the trading
  program's CPU-bound neural nets (capped at 80% of cores), future CPU inference.
  **This is the real core-count case.**

12 cores serves the throughput case while keeping strong per-core clocks for the latency
case. 24 cores would be generous rather than right-sized.

**On the X3D parts** (7800X3D, 9800X3D): these are 8-core gaming-first chips. The extra
L3 cache is excellent for CK3 and Stellaris specifically — both are cache-bound simulation
games — but 8 cores is thin for concurrent builds plus a VM plus the trading process. The
correct resolution is **not to buy one now**: buy 12 uniform cores today, and take a **Zen 6
X3D as the 2027–28 drop-in upgrade**, when it will serve the games properly on the same board.

## Five-year path

Year 0: Zen 5 12-core → Year 2–3: Zen 6 X3D drop-in on the same B850 board → the displaced
chip becomes the always-on trading box you've wanted.

## Sourcing note

This is the one healthy market in the build. **Micro Center 3-in-1 AM5 bundles**
(CPU + board + 32 GB RAM) have historically saved ~$400–460 versus buying separately — the
single biggest lever available. See `../market-prices/cpu.md`.
