# Storage sizing — measured from the current laptop ("iron")

Measured 2026-08-31 from granted folders on the Asus laptop. Windows, user `jmps2`.

## Measured footprint

| Location | Size | Notes |
|---|---|---|
| `.android/avd` | **~29.6 GB** | 4 emulators: Medium_Phone_2 13.9 GB, Pixel_9 8.0 GB, Small_Phone 4.3 GB, Medium_Phone 3.4 GB |
| `flutter/bin/cache` | **1.77 GB** | artifacts 1.02 GB, dart-sdk 544 MB, web sdk 110 MB, one stale `dart-sdk.old2` 45 MB |
| `.gradle` | **≥288 MB** | listing truncated at the 2000-entry cap; true size likely several GB |
| `UWW` (coursework) | **717 MB** | almost entirely COMPSCI-332-01 (696 MB) |
| `.cache/huggingface` | **346 MB** | a single model: `google/vit-base-patch16-224` |
| `Downloads` | **~176 MB** | |
| `Desktop` | empty | |
| `Videos` | empty | no captures, no screen recordings |

**Total measured: roughly 33 GB, plus the Flutter repo source/`.git` and the untruncated `.gradle` — call it 35–45 GB all in.**

Not measured: `Pictures`, `Music`, `Saved Games`, `.vscode-insiders`, `.local`, and anything outside the home directory (game libraries, Program Files).

## What this changes about the build

**1. The 1 TB / 2 TB split is backwards for this user.** The entire dev + documents footprint is under ~45 GB. A 1 TB boot drive is enormously oversized for "OS and general use," while the 2 TB drive will be consumed almost entirely by games, not development. The capacity belongs on drive two.

**2. Android emulators dominate, and they argue against PCIe 5.0.** Nearly 30 GB of the footprint is `.qcow2` sparse images that grow through small random writes, plus 2 GB `ram.img` snapshots per AVD. That access pattern is latency- and DRAM-cache-bound, not sequential-bandwidth-bound. A Gen4 drive with onboard DRAM (SN850X, 990 Pro) will handle it better than the DRAM-less Gen5 Crucial P510.

**3. The AI footprint today is 346 MB.** One vision transformer. No Ollama, no LM Studio, no GGUF cache anywhere in the home directory. The "large CPU-based AI" workload is aspirational rather than in-flight — which is fine, but it means storage doesn't need to be sized for it *yet*. When it arrives it will arrive fast: a handful of 70B-class quantised models is 150–250 GB.

**4. RAM is reinforced as the right priority.** Four AVDs at 2–4 GB each, plus Gradle daemons, plus a browser and IDE, is already a lot of concurrent memory pressure on a laptop. 64 GB is well justified independent of the AI ambition.

## Open questions
- How large is the Steam / game library? It's outside the home directory and unmeasured, and it is the single biggest driver of drive-two capacity. (`SteamSetup.exe` sits in Downloads, suggesting a recent or pending install.)
- The `flutter` folder is a full monorepo checkout — `engine/`, `buildtools/`, `third_party/`, `DEPS`. Is the Flutter **engine** ever built locally? If so, storage and CPU requirements both change substantially.

## Revised storage recommendation (pending those answers)
- **Boot / OS + general:** 1 TB is fine and leaves generous headroom. Gen5 acceptable here since this is the slot that will actually negotiate Gen5.
- **Dev + games:** go bigger and go Gen4-with-DRAM — 4 TB rather than 2 TB. Roughly the same money as the two P510s, with double the space where the pressure actually is.
