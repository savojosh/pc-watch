# Priorities — Storage

## What I actually want from this part

Organization, primarily. Two drives with a clean split — OS on one, development and games
on the other — so that reinstalling the operating system is a boring afternoon instead of a
week of rebuilding toolchains.

## Ranked priorities

1. **The two-drive split actually holding.** This is the stated reason for two drives.
2. **Enough space on drive two** for games plus repos plus emulator images.
3. **Responsiveness under many small writes** — the agentic rebuild loop, not big file copies.
4. Sequential speed. Last, and by a wide margin.

## Realistic expectations

- **I will not feel Gen5 and I should stop paying for it.** The original dream build had two
  DRAM-less Gen5 drives at $550. My actual disk pattern is emulator images growing by random
  write and Gradle churning thousands of small files — latency and cache bound. A Gen4 drive
  with onboard DRAM is *better* here and saves ~$200–250.
- **My footprint is much smaller than I think.** Everything measured on the current machine
  comes to ~35–45 GB. 1 TB for the OS drive is generous, not tight.
- **Games are what will actually fill drive two**, not development. 2–4 resident games is
  300–500 GB.
- **The split will fail silently if I install things normally.** Toolchain caches default to
  the home directory. Without deliberately redirecting them, the OS drive quietly
  accumulates the emulators, the Gradle cache and the pub cache while drive two holds only
  source — and the organizational benefit evaporates without any error message.
- **NAND is in the same shortage as RAM.** A 1 TB 990 Pro that bottomed at $59 is $239.
  Black Friday will not undo a shortage.

## The honest cut

If the budget needs to give somewhere, **this is where it should give.** Running one 1 TB
drive partitioned as a stopgap, and buying drive two when NAND normalizes, is the least
damaging deferral in the build. $299 for a drive that cost $93 at its floor is the worst
dollar here.

It does temporarily break the two-drive plan, which is the thing I actually wanted. That's
the trade — and it's still better than cutting RAM.

## What I'd trade away

Gen5. Sequential benchmark numbers. Brand prestige. Capacity on the boot drive.

## What I would not trade

Onboard DRAM. That's the spec that actually matters for how this machine feels day to day.

## Future goal

Rewrite the cache-redirection plan for Linux — the existing one is written for Windows drive
letters. Then get to a real two-drive layout where wiping the OS costs nothing. Longer term,
if CPU inference becomes real, a handful of 70B-class models is 150–250 GB and drive two
needs to be 4 TB.
