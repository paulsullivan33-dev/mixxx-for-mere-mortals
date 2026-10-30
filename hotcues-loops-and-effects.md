# Hotcues, Loops and Effects

Three sets of tools turn a player
into an instrument. The lab could
see every one of these controls in
the running program (they are in the
screenshots in `mixxx-lab/`), set
none of them by hand — its fixtures
were thirty-second test patterns —
and so this chapter describes them
from the Mixxx manual, plainly
labelled documented-only in
`criteria.md`. The one thing the lab
*can* prove is where their results
live: in the database.

## Hotcues

A **hotcue** is a bookmark that
plays. Each deck shows eight buttons,
numbered 1–8 under the waveform.
While a track plays, press an empty
button and the current position is
stored; press it again, any time,
and the deck jumps to that position
and keeps playing. DJs mark the
first beat, the vocal's start, the
drop, the clean exit — the places a
set is steered by.

Hotcues are per-track, not per-deck:
they are stored in the library
database's `cues` table, against the
track, and they survive restarts,
crates and playlists. (The lab's own
cues table held twenty rows it never
set by hand — four per fixture,
written by analysis itself: markers
for the first beat and its
neighbours, which Mixxx uses to
anchor the beat grid.) Set cues are
editable in the track Properties and
colourable, because at a glance,
mid-set, "the red one" beats "cue
number five".

## Loops

A **loop** repeats a stretch of the
track — four beats, eight, sixteen —
seamlessly, until you let it go. The
deck's loop controls set the size in
beats (the grid again), move the
loop, or halve and double it.
Uses: stretching an intro that ends
too soon, holding a groove while you
prepare the next blend, building a
climax out of a fragment. A loop
saved with the track — a *saved
loop* — lives in the same cues
machinery as hotcues and can be
recalled like one.

## Effects

Above each deck row sit the effect
units, **FX1** and **FX2** in the
default two-deck layout, assignable
to any channels. An effect unit
holds a chain of effects — the
library includes echoes, reverb,
flanger, filters and more — each
with a knob or three, and a *super
knob* that sweeps the chain's main
parameters together for one-handed
drama. Effects are decoration, not
structure: the set that works
without them works better with a
little of them, and the classic
beginner error is a set that is all
echo and no songs. The lab's
settings folder grew an
`effects.xml` on exit — chains are
configuration too, and they persist.

## Samplers, briefly

Below the decks sit the **samplers**:
small players for short sounds —
jingles, drops, a vocal stab — fired
from their own buttons, with their
own rows in the interface once you
enable more than the default view.
The skins Mixxx ships (Deere,
LateNight, Shade, Tango, several in
64-sampler variants) decide how much
of all this is on screen at once;
the lab ran LateNight, and chapter 3
met the rest by name in the package.
