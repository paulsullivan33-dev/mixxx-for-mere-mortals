# Auto DJ

Auto DJ is Mixxx playing a queue by
itself: track after track, blended
with automatic fades, for as long as
the queue lasts — the pub before the
DJ arrives, the party playlist with
manners. This chapter is the lab's
favourite, because Auto DJ ran here,
on a machine with no sound at all,
and left fingerprints everywhere.

## Building the queue

The queue is a playlist — the hidden
one chapter 5 found in the database,
named **Auto DJ**. Fill it by
selecting tracks in the library and
right-clicking:

- **Add to Auto DJ Queue (top)** —
  these play next, ahead of whatever
  waits.
- **Add to Auto DJ Queue (replace)**
  — the queue becomes exactly this
  selection.

The lab used *replace* with all six
fixtures, then confirmed the state
without trusting the screen:

```
playlist  track                     position
--------  ------------------------  --------
1         Arpeggio Study No. 1      1
1         Slow Morning Groove       2
1         Second Cup Waltz          3
1         Concert A (Test Tone)     4
1         Night Drive Loop          5
1         Pulse Train in C          6
```

## Switching it on

Open **Auto DJ** in the sidebar: the
queue, and a toolbar — an enable
button (it turns **orange** when
live), the transition style
(**Full Intro + Outro** was the
lab's: the fade spans the outgoing
track's outro and the incoming
track's intro, as analysis marked
them), a transition length (**10
sec.** here), shuffle toggles, and
a button to refill the queue
randomly from a crate when it runs
dry.

The lab pressed the button and
waited. Outwardly, little happened —
no sound, remember. In the records,
everything happened:

```
track                   timesplayed   last_played_at
----------------------  -----------   -------------------
Arpeggio Study No. 1    1             2026-10-30 23:04:54
Slow Morning Groove     1             2026-10-30 23:05:22
```

The queue shrank as tracks were
consumed (six became two while the
lab watched), the **History**
playlist for the date gained the
played tracks in order — Arpeggio,
Slow Morning, then Second Cup Waltz
as it started — and quitting Mixxx
mid-queue produced the dialog that
says it best:

```
A deck is currently playing. Exit Mixxx?
```

Auto DJ had been playing, on the
fallback "Network stream" clock,
with the mixer meters moving and no
listener in the world. As a proof
of machinery, it is complete.

## What it is and isn't

Auto DJ blends by measurement, not
taste: fixed rules, fixed fades, the
queue you gave it, in the order you
gave it (or shuffled). It respects
intros and outros as analysed, which
chapter 6 warns is a measurement,
not a promise. It will not rescue a
bad queue, skip a track the room
hates, or notice anything at all.
For background music that should
sound *handled* — crossfaded,
levelled, unhurried — it is
genuinely good. For a set, it is the
thing the DJ replaces.

Practical notes from the manual:
keep the queue long or point the
random refill at a large crate, or
Auto DJ stops at the end of the
list; turn it off before using the
decks yourself, because it will
happily load over your plans; and
its fades are transitions, not
beatmatching — tempo-synced blends
are your department (chapter 8).
