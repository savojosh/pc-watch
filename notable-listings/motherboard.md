# Notable listings — Motherboard

Spec: `../design-spec/motherboard.md` · Prices: `../market-prices/motherboard.md`
**Last verified by live sweep: 2026-08-31, 40 mi radius.**

## Recommendation

**Buy the MSI MAG B850 Tomahawk MAX WiFi new at $229.99 from Newegg.** Confirmed 2026-08-31
after re-testing the decision against a sealed ASUS TUF B850-E at $120 — see below. The
premium buys a 4th M.2 and a real PCIe x4 slot, plus a warranty and no drive to Illinois.

Still worth phoning Micro Center Westmont first in case a bundle makes the board effectively
free — see `cpu.md`.

## Live local listings — 40 mi radius

| Item | Price | Location | Drive (round trip fuel) | Verdict |
|---|---|---|---|---|
| **ASUS TUF Gaming B850-E WiFi — NEW, sealed** | **$120** | Crystal Lake, IL (~50 mi) | ~$20, seller offers to meet halfway | **CONSIDERED, REJECTED.** Half its $239 retail and a genuine bargain — but 3 M.2 and an x1-only secondary slot. See below. Seller 33 ratings, Highly rated |
| Brand New Gigabyte B850 Gaming X | $150 (cut from $175) | ~40 mi | ~$16 | Pass — no advantage over the Tomahawk at $80 less, and unverified slot layout |
| Gigabyte B850 EAGLE WIFI6E, used | $100 | Fitchburg, WI (~50 mi) | ~$20 | **Pass.** Weakest of the three — **gigabit-only Realtek NIC**, third M.2 is x2, all secondary slots PCIe 3.0 **x1** |
| Ryzen 5 7500X3D + ASRock B850M-C bundle | $320 (cut from $340) | Madison, WI (~50 mi) | ~$20 | Pass — 6-core X3D, below the 12-core floor; micro-ATX board |
| ASUS TUF Gaming Z790-Plus WiFi | $145 | East Troy, WI | ~$6 | **Dead** — LGA1700 |
| MSI B450 AM4 Gaming Plus Max | $70 | ~40 mi | — | **Dead** — AM4 |

## Why the $120 TUF B850-E was rejected

Verified specs: ATX, **4 DIMM** (256 GB), **3 M.2** (Gen5 x4 CPU, Gen4 x4 CPU, Gen4 x4
chipset), 4 SATA, PCIe **5.0 x16** CPU-attached, secondary x16-length slot that is **x1
electrical**, Realtek **2.5GbE**, Wi-Fi 6E, 8+2+1 VRM. Retail $239–244.

**The case for it was real.** The Tomahawk's x4 slot was justified largely by an HBA for the
NAS, and the NAS is now a separate box. An Intel 2.5GbE NIC needs only x1, so the Linux
fallback survives. And RTL8125 2.5GbE is *more* mature on Linux than the Tomahawk's newer
RTL8126 5GbE.

**Rejected because** the $110 premium buys a 4th M.2 and a genuine x4 slot — options that
cost little now and cannot be added later, on a board intended to last five years. New retail
also carries a warranty.

**If the Tomahawk becomes unavailable or the budget tightens, this is the fallback**, and a
good one. Do not re-flag it otherwise.

## Filter rules

Ignore AM4, LGA1700, LGA1851 boards at any price. Ignore boards with fewer than 4 DIMM slots.
Ignore boards whose only secondary slots are x1 **unless** priced under ~$130 as a fallback.
Flag round-trip fuel on anything beyond ~25 mi at ~$0.40 per mile of one-way distance.
