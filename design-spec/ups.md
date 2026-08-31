# Design spec — UPS

## What this part is

Battery backup. Not strictly part of the tower, but a deliberate inclusion — and one most
builds skip.

## Why it is on the list

The trading program runs **unattended, 23:00–10:00, every night**, and needs Tailscale up.
A brief outage at 03:00 with nobody awake means a hard power loss mid-run: lost work, and
a filesystem in an unclean state on a machine nobody is at.

That is the actual justification. Protecting the hardware is a secondary benefit; protecting
an eleven-hour unattended job is the reason.

## Currently aimed-for spec

| Field | Target |
|---|---|
| Model | **CyberPower CP1500PFCLCD** |
| Topology | Line-interactive, **pure sine wave** |
| Capacity | 1500 VA / 1000 W |
| Budget | **~$180** |

**Pure sine wave is required, not optional.** Modern active-PFC power supplies — including
every candidate in `psu.md` — can behave badly on the simulated/stepped sine wave that
cheaper UPS units produce, sometimes refusing to switch to battery at all. This is the
single spec not to compromise on.

## Sizing

A ~550 W peak system on a 1000 W unit gives several minutes of runtime — enough for a clean
automated shutdown, which is all that is needed. This is not meant to ride out a long
outage.

## Configuration to remember

Buying the UPS is not the whole job. **Configure automatic graceful shutdown** on the host
via `nut` or CyberPower's Linux daemon, triggered on battery. An unconfigured UPS just
delays the same hard power loss by four minutes.

Also: put only the tower and the network gear on the battery outlets. Monitors go on the
surge-only side — they are useless during an unattended overnight run and they drain the
battery fast.

## Purchase timing

**Buy this last.** It is the most deferrable item in the build, its market is stable at
~$180, and it does nothing until the machine is assembled and the trading program is
actually running on it.

## Note on batteries

UPS batteries are consumable — expect a replacement around year 3–4 of the five-year window.
Budget roughly $50 for it rather than being surprised into buying a whole new unit.
