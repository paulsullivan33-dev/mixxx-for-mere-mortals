# What Mixxx Is

**Mixxx** is DJ software: a program
that plays two or more songs at once,
lets you blend one into the next, and
keeps the library of tracks underneath
organised and measured. It does the
job of the classic two-turntables-and-
a-mixer setup, except the turntables
are files on your disk and the mixer
is a window full of knobs. It is free
software — free to download, free to
run, its code open for anyone to read
and change — and it runs on Windows,
macOS and Linux.

A DJ set is mostly three skills done
at once: choosing the next track,
starting it at the right moment, and
making the join invisible. Mixxx has
machinery for all three. The **library**
holds your music and remembers facts
about every track. **Analysis** listens
to each file once and writes down its
tempo and musical key, so the software
can line two songs up beat for beat.
The **decks** play the tracks, and the
**mixer** between them decides what
the audience hears.

This guide's lab ran the real thing:
Mixxx 2.4.0, installed from the Ubuntu
package archive, on a machine with no
speakers, no sound card and no DJ
hardware at all. That sounds like a
crippling limit, and for judging sound
it is — this guide never tells you how
anything *sounds*. But almost
everything a DJ program does besides
making noise is bookkeeping, and
bookkeeping can be measured exactly:
what the scanner read from each file,
what the analyser decided the tempo
was, what the automatic DJ actually
played and when. Chapter by chapter,
the claims here rest on that evidence,
kept in `mixxx-lab/` in this
repository. What could not be run —
real speakers, real controllers, a
real broadcast — is labelled
documented-only wherever it appears,
and `criteria.md` keeps the full
ledger.

One honest line belongs here, before
any procedure: Mixxx is a tool for
playing music, and music has owners.
Playing your own collection to
yourself and your friends is what it
is for. Recording a mix and handing
it out, or broadcasting one to the
internet, distributes other people's
work, and the rights for that are
yours to sort out — chapter 11
describes the machinery, not the
permission.

## What this guide covers

- The moving parts: decks, the mixer,
  the library and its database, the
  analyser — and which part holds what
- Installing Mixxx and surviving the
  first run, including the "no output
  devices" moment this lab met head-on
- The library: scanning, rescanning,
  crates, playlists, and the history
  Mixxx quietly keeps of everything
  that played
- Analysis: how Mixxx finds a track's
  tempo and key, measured against
  tracks whose true tempo the lab
  already knew — including the beatless
  test tone it confidently got wrong
- Decks, the mixer, hotcues, loops
  and effects, in plain terms
- Sync: what it does, and why working
  DJs trust it only so far
- Auto DJ: handing the decks to the
  machine, which this lab did, and
  proving from its own records that
  it played
- Broadcasting to internet radio and
  recording your mix
- Controllers and timecode vinyl —
  the hardware chapter, documented
  only, because the lab has none

## What it doesn't cover

How to *be* a DJ: taste, timing,
reading a room. This guide teaches
the instrument, not the art. It also
does not grade sound quality, because
the lab could not listen; chapters
say what the software does, and your
ears must judge the rest. Scratching
technique, turntablism and music
production are other crafts with
other tools.
