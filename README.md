# pc-watch

Working folder for Josh's AM5 desktop build. Mirrored between
`C:\Users\jmps2\pc-watch` on "iron" and the cloud project.

**Locked architecture: Socket AM5 · MSI MAG B850 Tomahawk MAX WiFi · DDR5 · Bazzite.**
GPU vendor open (Bazzite runs AMD and NVIDIA); AMD is the current pick on price, not
compatibility. Target lifecycle 5 years. Start at `design-spec/00_architecture.md`.

## Folders

| Folder | Holds |
|---|---|
| `design-spec/` | The exact specification for each part type — what it is, port and slot requirements, desired specs, what we are currently aiming for. **The compatibility contract.** Start with `00_architecture.md`. |
| `priorities/` | What Josh actually wants from each part type — future goals, realistic expectations, what to trade away first. The *why* behind the spec. |
| `market-prices/` | Observed market pricing per part type, so the realistic build's cost doesn't drift and the dream build stays honest. `00_budget-ledger.md` is the index and the running total. |
| `notable-listings/` | Live listings worth pursuing, per part type, with links and a recommendation. **Expired listings get removed, not archived.** |
| `archive/` | The original project research documents, preserved as written. Superseded in places — `design-spec/` wins on any conflict. |

## Working files

- `watchlist.md` — what the nightly scheduled task searches for
- `ledger.md` — the nightly task's append-only record of seen listings and price history

## Rules

1. `design-spec/` is the contract. A listing that conflicts with it is not a deal.
2. Anything DDR4, AM4, LGA1700 or LGA1851 is automatically out.
3. Air coolers never satisfy the cooling requirement.
3b. NVIDIA is allowed as of 2026-08-31 (Bazzite). Evaluate it; don't filter it.
4. NAS is a separate box, later. This build needs no drive bays and no HBA.
5. Prices go stale fast — DDR5 and NAND especially. Re-verify before buying.
