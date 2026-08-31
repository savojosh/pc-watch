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
| Target part | **Ryzen 9 9900X** (12C/24T, Zen 5) |
| Fallback | Ryzen 9 7900X (12C/24T, Zen 4) |
| Stretch | Ryzen 9 9950X (16C/32T) |
| Integrated graphics | **Required** — lets the machine boot and work before the GPU arrives |
| Budget | $275–330 standalone, or inside a Micro Center 3-in-1 bundle |

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
