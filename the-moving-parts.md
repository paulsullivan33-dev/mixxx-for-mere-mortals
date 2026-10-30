# The Moving Parts

Mixxx looks like one busy window, but
it is five parts doing five different
jobs. Knowing which part holds what
turns later confusion into a named
problem.

## The decks

A **deck** is a player: it holds one
track, plays it from a position, at a
speed you can nudge. Mixxx starts
with two decks and can show four.
Each deck has a play button, a **CUE**
button (jump back to the marked
starting point), eight **hotcue**
buttons (jump to other marked points,
chapter 9), a tempo slider, and a
small spinning disc — the *spinny* —
that turns as the track plays and can
be grabbed with the mouse to scratch
or nudge.

The deck is also where a track's
waveform is drawn: the whole song
compressed into a strip, loud parts
tall, quiet parts flat, so you can
see a chorus or a breakdown coming.

## The mixer

Between the decks sits the **mixer**.
Each deck feeds a **channel strip**:
a gain knob (how loud this track
enters), three EQ knobs (high, mid,
low — turn the bass of the outgoing
song down as the incoming one rises,
and the join stops sounding like a
fight), a filter knob, and a channel
fader. At the bottom, the
**crossfader** slides the audience's
ears from one channel to the other.
What reaches the speakers is the
*main* output; a second output, the
*headphone* output, lets the DJ
listen to the next track privately
while the current one plays — the
single most important trick in the
craft, and the reason DJs want a
sound device with at least four
channels.

## The library

The **library** is the collection:
a table of every track Mixxx knows,
with columns for artist, title,
album, genre, duration, tempo, key,
rating, and when it last played.
Underneath the table is a real
database — a single file,
`mixxxdb.sqlite`, in Mixxx's settings
folder. That fact is this guide's
best friend: anything the library
claims, the database can prove. The
lab read its evidence straight out of
that file, and chapter 5 shows you
the shape of it.

Around the table sit the organising
tools: **crates** (folders you file
tracks into by hand), **playlists**
(ordered lists, for a planned set),
a **history** (a dated playlist for
every session, written automatically),
and the **Auto DJ** queue (chapter
10).

## The analyser

The **analyser** is the part that
listens once so you don't have to
guess forever. For each track it
computes three things: the
**waveform** (that strip the deck
draws), the **beat grid** — the
tempo in BPM (beats per minute) and
the position of the first beat, from
which every later beat is counted —
and the **musical key**. In the
2.4.0 the lab ran, the tempo work is
done by the Queen Mary tempo tracker
(the database records
`qm-tempotracker` as the tool, under
the version label `BeatGrid-2.0`),
and the key by Mixxx's own key
detector (`KeyMap-1.0`). It also
measures each track's loudness and
stores a **ReplayGain** value, so a
quiet recording and a loud one can be
levelled automatically. Chapter 6
puts its numbers on trial.

## The engine and the clock

Underneath everything, the **engine**
mixes the decks in real time. It
needs a steady clock, normally
provided by the sound device. The
lab's machine had no sound device at
all, and this is where this guide got
lucky: Mixxx complained, in a dialog
titled *No Output Devices*, and its
log recorded why it kept going
anyway:

```
warning [Main] Output sound device clock reference not set!
Using "Network stream"
```

With no hardware clock, Mixxx fell
back to an internal network-stream
clock — and kept perfect bookkeeping
time. Tracks played, play counts
rose, the history filled in. Nothing
was audible, and nothing pretended
to be. That fallback is why chapters
5, 6 and 10 can be verified at all.
