# Two-drive layout plan

Based on Josh's stated structure (modeled on the laptop "iron") and usage: 2–4 games resident at a time, many school programs installed, OS separate from dev/gaming for organization.

## Capacity verdict

| Drive | Role | Size | Interface |
|---|---|---|---|
| C: | Windows, school programs, documents | 1 TB | Gen5 fine here — this is the slot that actually negotiates Gen5 |
| D: | Development + games | 2 TB | **Gen4 with onboard DRAM** (SN850X, 990 Pro) |

Rough budget for D:, with 2–4 games resident: games 300–500 GB, dev repos and caches 100–200 GB. 2 TB is comfortable. The earlier 4 TB suggestion assumed a large permanent game library and does not apply.

C: at 1 TB is generous for Windows (~40 GB) plus a heavy school-software load (~100–150 GB) plus documents.

## The actual problem: Windows defaults fight this layout

Almost every toolchain cache in the observed structure is hardcoded to `%USERPROFILE%` — that is, C:. Install the tools normally and put projects on D:, and C: still silently accumulates the AVDs, the Gradle cache, the pub cache, and the model cache, while D: holds only source. The organizational split fails quietly.

Fixing it means redirecting each cache explicitly. Set these as **user** environment variables (System Properties → Environment Variables), before installing the tools where possible.

| Variable | Value | Redirects |
|---|---|---|
| `GRADLE_USER_HOME` | `D:\dev\.gradle` | Gradle caches + daemon + Kotlin profile |
| `ANDROID_USER_HOME` | `D:\dev\.android` | ADB keys, Android user config |
| `ANDROID_AVD_HOME` | `D:\dev\.android\avd` | **Emulator images — the big one** |
| `ANDROID_HOME` / `ANDROID_SDK_ROOT` | `D:\dev\Android\Sdk` | Android SDK, platforms, NDK |
| `PUB_CACHE` | `D:\dev\.pub-cache` | Dart/Flutter packages |
| `HF_HOME` | `D:\dev\.cache\huggingface` | Hugging Face model cache |
| `PIP_CACHE_DIR` / `UV_CACHE_DIR` | `D:\dev\.cache\pip` | Python packages |
| `CARGO_HOME` / `GOPATH` | `D:\dev\...` | If Rust/Go are in play |

Not environment variables, handle separately:

- **npm:** `npm config set cache D:\dev\.npm --global`
- **Flutter SDK:** clone to `D:\dev\flutter` rather than the home root
- **Android Studio caches:** `idea.system.path` and `idea.config.path` in `idea.properties`
- **Steam:** add `D:\SteamLibrary` as a library folder and set it as default for new installs
- **Docker Desktop:** relocate the WSL2 `.vhdx` if containers are used — it grows without bound on C: otherwise
- **Windows known folders:** Documents / Downloads / Pictures can be moved to D: via each folder's Properties → Location tab, if you want user data to survive a reinstall too

## Why this pays off

The stated reason for two drives was organization, but the stronger payoff is that a Windows reinstall then touches only C:. With the redirects above, wiping and reinstalling Windows leaves every repo, toolchain cache, emulator image, and game library intact on D: — reconnect by re-setting the same variables. Without the redirects, a reinstall takes the AVDs and every cache with it.

## Interface note, restated

The dev drive's real workload — Gradle's many small files, emulator `.qcow2` images growing by random write, incremental build output — is latency and DRAM-cache bound, not sequential-bandwidth bound. That is why Gen4-with-DRAM beats the DRAM-less Gen5 P510 here despite the slower bus. Additionally, Arrow Lake supplies only one CPU-attached Gen5 M.2 slot; the second M.2 runs off the chipset at Gen4, so a second Gen5 drive would likely be paying for a speed the slot cannot deliver. Confirm against the MSI Z890 Gaming Plus manual.
