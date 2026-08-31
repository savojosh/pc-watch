# "Now" build plan v2 — AM5 + SteamOS, staged Sept–Dec 2026

Target: works today, upgradable for five years.
Budget: aiming $1,000–1,500, stretch to $2,500. Buying incrementally over 2–4 months.
Host OS: **SteamOS**, with a Windows VM for Windows-target app testing.

**All prices are estimates needing same-day verification.** RAM and GPUs are both badly distorted markets right now.

---

## What the OS choice changes

SteamOS 3.8 (June 2026) officially supports **any AMD desktop PC**. Valve has confirmed NVIDIA support is being worked on but it has **not shipped**. Two hard consequences:

### 1. The GPU must be AMD. Non-negotiable.
This removes the RTX 4070 from v1 of this plan. It is not a downgrade — AMD cards have better open-source Linux drivers, better Wayland behaviour, and are generally cheaper on the used market.

### 2. Your RAM problem just got significantly worse.
A Windows 11 VM wants 8–16 GB to itself. Add the trading program's neural network threads, 2–4 Claude Code instances, the Dart analysis servers, and the SteamOS host. **32 GB is no longer a compromise — it's a bottleneck you'll hit weekly.**

This is the central budget tension in the whole build, and it is worth confronting directly rather than discovering in December.

---

## Target parts list

| Part | Pick | Est. | Notes |
|---|---|---|---|
| **CPU** | Ryzen 9 **7900X** (12C/24T) | ~$320 | 12 cores now serves three masters: trading NNs (80% cap ≈ 19 threads), concurrent Claude Code instances, and the Windows VM. Enable **SVM/AMD-V** in BIOS. Integrated graphics let you run headless before the GPU arrives. |
| **Motherboard** | B650 / B850, 4 DIMM, 2× M.2, 2.5GbE | ~$160 | Zen 6 support via BIOS. Confirm IOMMU support if you ever want GPU passthrough to the VM. |
| **RAM** | 32 GB (2×16) DDR5-6000 CL30 EXPO — **64 GB if at all possible** | ~$430 / ~$950 | See the RAM section below. This is the decision that matters most. |
| **GPU** | **Used AMD** — RX 7900 GRE 16 GB (ideal), RX 7800 XT 16 GB, or RX 9060 XT 16 GB | ~$350–450 | 16 GB, strong at ~6 MP ultrawide. Deadlock is native Linux. Handles 90–120 fps with settings. |
| **Boot SSD** | 1 TB Gen4 **with DRAM** — SN850X / 990 Pro | ~$100 | Not Gen5, not DRAM-less. |
| **Data SSD** | 2 TB Gen4 with DRAM | ~$190 | Dev, games, **and the Windows VM disk image**. Give the VM its own image here, not on the boot drive. |
| **Cooler** | **Arctic Liquid Freezer III 360** | ~$115 | Water, as requested. This is the right one — best sustained performance per dollar, and it's what your original list already had. |
| **PSU** | 750 W Gold, ATX 3.1 | ~$115 | 7900X + 7900 GRE ≈ 550 W peak. Headroom for a future GPU. |
| **Case** | High-airflow mesh ATX **with 360 mm radiator support** — Lancool 216, Montech Air 903 Max, Phanteks G400A | ~$95 | Confirm 360 front or top clearance before buying. |
| **UPS** | CyberPower CP1500PFCLCD | ~$180 | Unattended overnight trading. Buy last. |

**Estimated subtotal: ~$1,925** (~$2,105 with UPS)
**With 64 GB instead of 32 GB: ~$2,450–2,600**

Honest read: this lands **$1,900–2,100** at 32 GB, or **~$2,600** with the memory your workload actually wants. Above the $1,500 target, inside the stretch range.

---

## The RAM decision

Your workload is genuinely memory-bound, and SteamOS + a Windows VM pushed it over the line. Options, least to most expensive:

1. **2×16 GB now, add 2×16 later (~$430 + ~$430).** I advised against adding sticks earlier because AM5 runs 4 DIMMs at reduced speed (~4800–5200 vs 6000). I'd revise that here: for VM and compile work you are **capacity-bound, not bandwidth-bound**, and the speed loss costs you little outside gaming. This is the pragmatic path on a staged budget.
2. **2×32 GB now (~$950).** Cleaner, faster, keeps two slots free for a future 128 GB. Nearly half the build budget.
3. **2×16 GB and live with it.** Workable if you don't run the Windows VM and Claude Code instances at the same time. Plan around it rather than hitting it by surprise.

Watch the used market for DDR5 the same way you're watching for a GPU.

---

## SteamOS: honest assessment

Your reasoning — strip Windows bloat, gaming-first, low overhead — is sound, and your **game library is unusually well suited to Linux**. CK3 and Stellaris have native Linux builds, Deadlock is a Valve title with native support, Palworld and Cities: Skylines II run under Proton. Gaming is genuinely not the risk here.

The friction is development, and it's real:

- SteamOS has an **immutable, read-only root** with atomic updates. Installing Android Studio, the Android SDK, Gradle, and the Flutter toolchain means working through **distrobox** containers or Flatpak rather than a normal package install. Very doable, but it is a different mental model and it will cost you a weekend up front.
- **Tailscale** as a system service on an immutable root needs a workaround (static binary or container) rather than a package install.
- Android emulators run on **KVM** and are typically *faster* on Linux than on Windows — a genuine win.
- Flutter targeting Linux and Android works fully. iOS still requires macOS; nothing changes that.

**Two alternatives worth considering before you commit**, both giving you the same anti-bloat gaming-first result with far less dev friction:

- **Bazzite** — explicitly built to be "SteamOS for your own PC." Includes the Steam gaming-mode experience, supports **both AMD and NVIDIA**, and has distrobox integrated. Removes the GPU lock-in entirely.
- **CachyOS** — Arch-based, performance-tuned kernel, fully mutable filesystem. The most dev-friendly of the three while still being gaming-optimised.

I'd nudge toward Bazzite or CachyOS given how much development this machine does, but SteamOS is a legitimate choice and the list above works for it either way. **If you pick Bazzite or CachyOS, the AMD-only GPU constraint disappears** and an RTX 4070 comes back on the table.

### One five-year flag
AMD GPU + SteamOS means **no CUDA**. Your AI work is CPU-based today so this costs you nothing now. But if that work ever moves to GPU acceleration, ROCm is meaningfully weaker than CUDA and you'd be re-buying a GPU. Worth knowing you're making that trade.

---

## Purchase sequence

### Phase 1 — Sept/Oct: bootable core
CPU, motherboard, RAM, PSU, cooler, case, boot SSD.

Buy close together and **POST-test on the bench immediately**. A board bought in September is out of return window by December; don't find a dead one at assembly time.

The 7900X's integrated graphics mean this set alone is a working dev machine — install SteamOS (or Bazzite), get the toolchain and Windows VM running, before you own a GPU.

### Phase 2 — continuously: hunt used
Watch Marketplace daily for a used **AMD RX 7900 GRE / 7800 XT** and for **DDR5**. Test any GPU in person.

### Phase 3 — Black Friday: SSDs discount hardest; CPU+mobo bundles are standard promos.

### Phase 4 — December: assemble. UPS last.

---

## Five-year path

| When | Move |
|---|---|
| Now | 7900X, 32 GB, used AMD 16 GB GPU, SteamOS + Windows VM |
| Soon | Second RAM kit to 64 GB — highest-value upgrade available to you |
| 2027–28 | **Zen 6 X3D** drop-in. Same board, RAM, cooler, case. This is what finally serves CK3 and Stellaris properly — they're cache-bound simulation games and 3D V-Cache targets exactly that. |
| 2028–29 | GPU upgrade |

**The loop this closes:** when the Zen 6 chip goes in, the 7900X and B650 become the dedicated 24/7 trading box you said you eventually want — a 12-core always-on machine for the price of a case and PSU.

---

## Open item
Monitor is confirmed **21:9, not 32:9** from the photo, so 3840×1080 is ruled out. Still need to know whether it's 3440×1440 (34") or 3840×1600 (38"). Check the model number on the back, or the display settings. Either sits near 6 MP and the GPU picks above cover both.
