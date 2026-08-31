# Design spec — Storage layout (Bazzite)

**Written 2026-08-31**, after the OS was locked to Bazzite. This replaces the Windows-era
plan in `../archive/two-drive-layout-plan.md`, which remains valid **only** for the Windows
VM's own internal disk.

## The goal, restated

Reinstalling or rebuilding the OS should cost nothing. Every repo, toolchain cache, emulator
image, container and game library should survive it untouched.

## The good news: Linux makes this almost trivial

The Windows plan needed eight environment variables and a half-dozen per-tool overrides
because Windows toolchains hardcode caches to `%USERPROFILE%` on `C:`. On Linux, **every one
of those caches already lives under `$HOME`**:

| Cache | Location |
|---|---|
| Gradle | `~/.gradle` |
| Android SDK + AVDs | `~/.android`, `~/Android/Sdk` |
| Dart / Flutter packages | `~/.pub-cache` |
| HuggingFace models | `~/.cache/huggingface` |
| pip / uv | `~/.cache/pip`, `~/.cache/uv` |
| npm | `~/.npm` |
| Steam library | `~/.local/share/Steam` |
| Podman / distrobox containers | `~/.local/share/containers` |

**So: put `/home` on drive two and the entire problem is solved in one line of fstab.** No
`GRADLE_USER_HOME`, no `ANDROID_AVD_HOME`, no `PUB_CACHE`, no per-tool redirects. The
Windows plan's complexity was a Windows problem.

## The layout

| Drive | Slot | Size | Mounts |
|---|---|---|---|
| **Drive 1 — OS** | M2_1 (Gen5 x4, CPU) | 1 TB | `/boot/efi`, `/boot`, `/` (ostree), `/var` |
| **Drive 2 — data** | M2_2 (Gen5 x4, CPU) | 2 TB | **`/home`**, plus `~/vms` for the Windows VM image |

Use M2_1 and M2_2. **Avoid M2_3** — populating it drops the PCI_E3 expansion slot from x4 to
x2, and that slot is reserved for an Intel NIC if the Realtek 5GbE proves troublesome on Linux.

Filesystem: **Btrfs** on both. Bazzite defaults to it, and subvolumes plus cheap snapshots
are genuinely useful for a machine doing risky toolchain work.

## What stays on drive 1, and why that's fine

- The ostree deployments (Bazzite keeps two, plus up to 90 days of prior images)
- `/var`, which holds Flatpak apps and system Podman storage
- Total realistic usage: well under 200 GB. **1 TB is generous, as intended.**

## The one thing that needs moving explicitly

**The Windows VM disk image.** libvirt defaults to `/var/lib/libvirt/images`, which is on
drive 1. A Win11 guest image is 60–100 GB and belongs on drive two.

After running `ujust setup-virtualization`, define a storage pool pointing at
`~/vms` (on drive two) and create the guest's disk there. This is the Linux equivalent of
the Windows plan's "give the VM its own image on D:" rule, and it matters for the same
reason — VM images are large, they churn, and they are not OS state.

## Bazzite-specific rules that follow

1. **Systemd services do not run inside distrobox.** Tailscale, `libvirtd`, and anything
   supporting the overnight trading program are **host** services. This is the single most
   important operational rule of the whole setup.
2. **Host gets:** Tailscale (`ujust enable-tailscale` — it's in the base image),
   virtualization (`ujust setup-virtualization`), adb udev rules in `/etc/udev/rules.d/`,
   and your user in the `kvm` group.
3. **One distrobox** holds Flutter, Android SDK, JDK/Gradle, Node and Python. Create it with
   `--device /dev/kvm` so the Android emulator gets hardware acceleration.
4. **VS Code as a host Flatpak**, attaching into the container — do *not* export it out of
   the distrobox, which has caused GitHub auth problems.
5. **Layer packages onto the base image only as a last resort.** Bazzite's own documented
   priority is: ujust/Portal → Flatpak → Homebrew for CLI tools → distrobox → AppImage →
   rpm-ostree layering last. A layered package whose dependencies can't resolve against a new
   base image will **stall an update**.

## Practical gotcha to pre-empt

**inotify watch limits.** Several concurrent Gradle daemons plus Dart analysis servers can
exhaust `fs.inotify.max_user_watches`. This is a host sysctl and containers inherit it. Fix
before it bites, with a file in `/etc/sysctl.d/`:

```
fs.inotify.max_user_watches = 524288
fs.inotify.max_user_instances = 1024
```

`/etc` is real and writable on Bazzite and persists across updates, so this survives.

## Rollback, honestly

`rpm-ostree rollback` is one command — but it is **one deployment deep**. Running it twice
returns you to where you started rather than going back two versions. Before any risky
change, `ostree admin pin` a known-good deployment to get a durable escape hatch.

Rollback reverts the **OS only**. It does not revert `/home`, your containers, or `/etc`.
That is exactly why drive two holds everything you care about.

## Capacity check

Measured footprint on the current machine is **~35–45 GB** — emulators ~30 GB, Flutter cache
1.8 GB, Gradle a few GB, coursework 717 MB. Drive two's 2 TB will be consumed mostly by games
(300–500 GB with 2–4 resident) and the VM image.

**Open question, unchanged:** the Steam library size is unmeasured and is the biggest driver
of drive-two capacity. If it is large, drive two should be 4 TB rather than 2 TB. Measure
before buying.
