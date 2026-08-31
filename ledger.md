# PC Deal Watch — Ledger

Append-only running record. The nightly run reads this before searching so it does not
re-flag things Josh has already seen, and appends what it found. Do not rewrite history;
add new entries at the bottom of each section.

## How to use this file

- **Seen listings**: every Marketplace / Reddit / forum listing already surfaced, with the
  date first seen. A listing already here is only re-flagged if its price dropped
  meaningfully or its status changed.
- **Price history**: one row per retail part per run where a price was successfully read.
  This is what makes "meaningful drop" measurable instead of a guess.
- **Dismissed**: things Josh said no to. Never flag these again.

---

## Seen listings

| First seen | Source | Item | Price | Location | Link | Notes |
|---|---|---|---|---|---|---|
| 2026-08-31 | Marketplace | **Gaming PC + 27" 1440p 180Hz monitor** — RX 9060 XT 16GB, Ryzen 5 9600X, 32GB DDR5-6000, 2TB 990 EVO Plus, B850M Pro-A WiFi, RM750e 750W | **$1,299 firm** | Eagle, WI | [link](https://www.facebook.com/marketplace/item/1615949413652605/) | **STRONGEST FIND SO FAR.** ~$600 under parts value. Seller 73 ratings, highly rated. Under consideration — see notable-listings/whole-systems.md. CPU is 6-core, below the 12-core floor |
| 2026-08-31 | Marketplace | Corsair Crystal 680X + 3× LL140 | $160 (was $170) | East Troy | [link](https://www.facebook.com/marketplace/item/982467421351537/) | Still live, price cut once. Offer $120 |
| 2026-08-31 | Marketplace | **ASUS TUF Gaming B850-E WiFi — NEW sealed** | **$120** (retail $239) | Crystal Lake, IL | [link](https://www.facebook.com/marketplace/item/1539897134108491/) | Considered as a Tomahawk replacement; **rejected** — 3 M.2, x1-only secondary slot. Kept as fallback. Seller 33 ratings, highly rated |
| 2026-08-31 | Marketplace | Lian Li Lancool 205 Mesh + CM Elite 240 AIO + fans/hub | $100 | Janesville | [link](https://www.facebook.com/marketplace/item/985527567824017/) | **Still live** (6 weeks up) — earlier "expired" call was wrong. ATX support. Verify 360 mm clearance |
| 2026-08-31 | Marketplace | XFX Speedster SWFT 319 RX 6800 16GB | $350 | Deforest, WI | — | Clears the $450 GPU trigger, but RDNA 2, ~250 W, no warranty. Fallback only |
| 2026-08-31 | Marketplace | Gigabyte B850 EAGLE WIFI6E, used | $100 | Fitchburg, WI | — | Rejected — gigabit-only NIC, x2 third M.2, x1 secondary slots |
| 2026-08-31 | Marketplace | TeamGroup T-Force Delta 32GB DDR5-5200 | $425 | Waukesha, WI | — | Rejected — **above** the $404 new price for faster DDR5-6000 |
| 2026-08-31 | Marketplace | i9-14900K + ASUS Z790 Prime bundle | $400 | Elgin, IL | — | Rejected — LGA1700 |
| 2026-08-31 | Marketplace | ASUS TUF RTX 3080 Ti OC / EVGA 3080 Ti FTW | $360 / $400 | Germantown / Rockford | — | Rejected — 12 GB, under the VRAM floor |
| 2026-08-31 | Marketplace | NVIDIA RTX 5070 Gaming PC, i9-14900KF | $2,100 | Delavan | — | Rejected — LGA1700 dead socket |
| 2026-08-31 | Marketplace | Gaming PC, RTX 5060 | $1,100 | Janesville | — | Rejected — 5060 is 8GB, below VRAM floor |
| 2026-08-31 | Marketplace | G.SKILL RipjawsV 32GB (2×16) | $180 | Fort Atkinson | — | Rejected — DDR4 |
| 2026-08-31 | Marketplace | Samsung DDR5-5600 laptop memory | $150 | Janesville | — | Rejected — SODIMM, laptop form factor |

---

## Price history

| Date | Part | Retailer | Price | Notes |
|---|---|---|---|---|
| _(none yet — seeded 2026-08-31)_ | | | | |

---

## Dismissed — do not flag again

| Date | Item | Reason |
|---|---|---|
| 2026-08-31 | RTX 4060 8 GB, $325 NIB, Janesville (from the "PC Parts" lot) | 8 GB fails the 16 GB VRAM floor; would bottleneck at ultrawide; over market for a 4060 |
| 2026-08-31 | Corsair DDR4 32 GB (2×16), $140, Whitewater | DDR4 — does not fit AM5. Also overpriced for DDR4 |
| 2026-08-31 | Intel i7-14700KF, $250 (cut from $270), Whitewater — **still live**, [listing](https://www.facebook.com/marketplace/item/1065221752982873/) | LGA1700 dead socket; ~250 W vs ~150 W sustained, which costs completed work on a temperature-throttled overnight run; Raptor Lake Vt degradation risk; seller has no ratings. Rejection is architectural — do not re-flag at any price |
| 2026-08-31 | Custom PC, Ryzen 5 3600XT / RX 6650 XT, $800, Edgerton | AM4 dead socket; GPU is a downgrade from the current laptop's 3080; parts total well under ask |

---

## Run log

| Date | Marketplace reachable? | Sources checked | Notified? |
|---|---|---|---|
| 2026-08-31 | — | seeded, no run yet | no |
| 2026-08-31 | **Yes — live sweep with Claude via Chrome** | Facebook Marketplace, Whitewater 20 mi: "ryzen" (0 results), "ddr5", "gaming pc", "rtx", "9060 xt" | 1 strong find (Eagle $1,299), 1 still-live (680X $160), 4 rejected, 5 believed expired |
| 2026-08-31 | **40 mi sweep with Claude via Chrome** | Marketplace, Whitewater **40 mi**: "ryzen", "am5", "ddr5", "b850 motherboard", "radeon", "aio liquid cooler", "nvme ssd" | Opened up a real AM5 market that does not exist at 20 mi: 4 AM5 boards, a 16GB AMD GPU, a CPU+board bundle. Radius made standing at 40 mi |
| 2026-08-31 | correction | Josh supplied a direct link | **The i7-14700KF was NOT expired** — those search terms could not match an Intel-titled listing. Lesson: search by explicit model number before declaring anything expired. Expiry claims from that sweep are unreliable for non-AMD items |
