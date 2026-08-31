# Priorities — CPU

## What I actually want from this part

A great **work** CPU. This is the stated #1 priority of the whole build. The laptop it
replaces is thermally buckling under exactly this load, and I want the desktop to stop
being the thing that limits how much I can run at once.

## Ranked priorities

1. **Concurrent throughput.** Several Flutter apps building at once, Android emulators
   alongside, the trading program's neural nets underneath. This is the real core-count case.
2. **Single-thread speed.** The agentic `flutter analyze` / hot-reload loop is a *latency*
   workload. More cores does nothing for it. Both halves matter and they pull differently.
3. **Upgrade path.** A drop-in Zen 6 in 2027–28 on the same board.
4. **Integrated graphics**, so the machine is useful before the GPU arrives.
5. Gaming. Genuinely fifth — the games I play most are simulation titles I cap at 60 FPS.

## Realistic expectations

- **12 cores is right-sized, 24 would be generous.** The earlier "core count is everything"
  framing was too blunt; the analyzer doesn't scale and Gradle's gains taper well below 24.
- **I will not feel this upgrade in CK3 or Stellaris.** Those are cache-bound. The chip that
  fixes them is a Zen 6 X3D in 2027–28, not anything I buy now. Expecting otherwise leads to
  buying an 8-core X3D today and regretting it on build days.
- **The CPU market is the healthy one.** No shortage pressure. I should not feel rushed here
  the way I do on RAM and storage.
- **The Micro Center bundle is the single biggest lever in the build** — historically
  ~$400–460 versus buying separately. It's worth planning a trip around.

## What I'd trade away

Peak gaming frame rates. Overclocking headroom. The last 10% of single-thread performance
if it costs 4 cores.

## What I would not trade

Core count below 12, or the AM5 socket. An 8-core chip — however fast — is thin for
"multiple Flutter apps, an emulator, a Windows VM, and the trading process, at the same
time," which is the actual daily reality.

## Future goal

Year 2–3: Zen 6 X3D drop-in. That single upgrade closes both open loops at once — it finally
serves the simulation games properly, **and** it frees the current chip to become the
dedicated 24/7 trading machine I've wanted, for the price of a case and PSU.
