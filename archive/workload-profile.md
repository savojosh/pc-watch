# Workload profile — what Josh's work actually stresses

Established 2026-08-31. Supersedes the "core count is everything" framing used earlier in the session.

## Confirmed workload
- Runs `flutter run` locally on his machines — **app-level builds, not Flutter engine builds**
- Frequently has Claude Code drive `flutter` compile and analyze cycles agentically
- Multiple Flutter apps compiled (original stated requirement)
- Android emulators (4 AVDs on the example machine)
- Large CPU-based AI projects — aspirational, not yet in flight
- Gaming at high settings

## What each part actually bottlenecks on

| Task | Bound by | Scales with cores? |
|---|---|---|
| Dart Analysis Server (`flutter analyze`, IDE, Claude Code analysis) | **Single-thread speed + RAM.** Largely single-threaded per instance, 2–6 GB resident per project | No |
| Hot reload / `flutter run` debug iteration | **Single-thread + warm RAM state** (JIT) | No |
| Gradle build of one app (Kotlin/Java, D8/R8, AAPT2) | Moderately parallel | Somewhat — real gains taper well below 24 cores |
| **Several apps building concurrently** | Parallel, separate Gradle daemons, 2–4 GB each | **Yes — this is the genuine core-count case** |
| Android emulators (QEMU VMs) | Cores + RAM per instance | Yes |
| CPU inference (future) | Cores + memory bandwidth + **RAM capacity** | Yes |

## The correction

Earlier in this session I argued against the X3D chips on core count. That was too blunt. An agentic `flutter analyze` / hot-reload loop is a **latency** workload, not a throughput one — it is dominated by single-thread performance and warm in-memory state, and a 24-core CPU does not make it meaningfully faster. The X3D parts are stronger for that specific loop than I implied.

The core-count case is still real, but it rests on the *concurrent* work: several apps building at once, emulators running alongside, and the future CPU-inference ambition. Not on the analyzer.

## Where this leaves the 285K

Still a good fit, but for a different reason than originally given:
- **P-cores** (high clock) serve analyzer latency and hot-reload turnaround
- **E-cores** absorb parallel Gradle tasks and background emulators without stealing from the foreground
- 24 cores covers the concurrent-projects and future-inference cases

The Ryzen 9 9950X remains the alternative worth pricing: 16 uniformly strong cores, comparable single-thread, plus the AM5 upgrade path that LGA1851 lacks.

## Two things this reinforces

**1. RAM, again.** Dart analysis servers at 2–6 GB per project, Gradle daemons at 2–4 GB each, emulators at 2–4 GB each, plus Claude Code and a browser. Concurrent multi-project work is a memory-capacity problem before it is a core-count problem. 64 GB is correct and is worth protecting in the budget.

**2. Storage — the Gen5 case is now very weak.** Once the analysis server and Gradle daemon are warm, they are RAM-resident and touch disk rarely. What disk work remains is many small writes into `build/` and `.dart_tool/` on every agentic rebuild cycle. That pattern rewards a DRAM-equipped Gen4 drive and punishes a DRAM-less Gen5 one. It also raises write volume over time, so endurance (TBW) favours the DRAM drives, which are typically rated higher than DRAM-less HMB designs like the P510.

## Open question
How many Flutter projects are typically open and building at the same time? That number is what decides whether 24 cores is right-sized or generous.
