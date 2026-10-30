# Mixxx for Mere Mortals

A DJ setup used to mean two
turntables, a mixer, and a crate of
records heavy enough to count as
furniture. **Mixxx** is that setup as
a computer program: two or more
**decks** that play music files, a
**mixer** that blends them, and a
**library** underneath that keeps
every track organised — and, once it
has *analysed* them, knows each
track's tempo and musical key, so two
songs can be lined up beat for beat.
It is free software, for Windows,
macOS and Linux, maintained by
volunteers, and used everywhere from
bedrooms to clubs that would rather
not pay the commercial programs'
hardware toll.

This guide explains how Mixxx is put
together, how to install it, and how
to build a library it can measure
honestly. Then it does the thing
this series exists for: it checks the
program's famous numbers against
reality. The lab that wrote this
guide had no speakers, no sound card
and no DJ hardware — it could not
hear a single track it played. So
every claim here rests on evidence
that doesn't need ears: the library
database Mixxx keeps, read directly;
its analyser fed tracks whose true
tempos were known in advance; and
its Auto DJ switched on and left to
play a queue into the silence, with
its play counts, history and one
reluctant dialog ("A deck is
currently playing. Exit Mixxx?")
offered as the receipts.

What the lab could not do, it did
not fake. It never heard the music,
so it never grades it. Controllers,
timecode vinyl, live broadcasting
and the sound of a good blend are
taught from the Mixxx manual and
labelled as such wherever they
appear; `criteria.md` keeps the full
ledger of what was run and what was
only read.

## What this guide covers

- [**What Mixxx is**](what-mixxx-is.md) —
  the mental model: decks, a mixer and
  a measured library, and what a DJ
  program is for
- [**The moving parts**](the-moving-parts.md) —
  decks, mixer, library and its
  database, the analyser, and the
  engine clock that kept this lab
  honest
- [**Installing Mixxx**](installing-mixxx.md) —
  the package route, the version check
  that needs a display, and the two
  first-run ceremonies
- [**Your first library**](your-first-library.md) —
  scanning, what the scanner actually
  reads, and rescanning for new music
- [**The library**](the-library.md) —
  the tracks table, crates, playlists,
  the automatic history, and why the
  database is the truth
- [**Analysis: BPM and key**](analysis-bpm-and-key.md) —
  the analyser on trial: exact tempos,
  a believed tag, a correct key, and
  a beat invented for a beatless tone
- [**Decks and the mixer**](decks-and-the-mixer.md) —
  transport, tempo, channel strips,
  crossfader — the controls in the
  order your hands meet them
- [**Sync and beatmatching**](sync-and-beatmatching.md) —
  what the Sync button really does,
  and why DJs trust it only so far
- [**Hotcues, loops and effects**](hotcues-loops-and-effects.md) —
  bookmarks that play, stretches that
  repeat, and decoration with a knob
- [**Auto DJ**](autodj.md) — handing
  the decks to the machine, and
  proving from its own records that
  it played
- [**Broadcasting and recording**](broadcasting-and-recording.md) —
  feeding an internet radio server,
  and keeping the set as a file
- [**Controllers and vinyl control**](controllers-and-vinyl.md) —
  the hardware door: 294 mappings in
  the box, and turntables that drive
  files
- [**Recipes**](recipes.md) — prepare
  new music, queue an unattended
  evening, prove what played, fix a
  doubled tempo, blend by hand
- [**The neighbours**](the-neighbours.md) —
  Serato, Rekordbox, Traktor,
  VirtualDJ, and the non-DJ tools
  your collection also meets
- [**Limits**](limits.md) — the
  detector's blind spots, the missing
  stems, the booth it cannot be
- [**Troubleshooting**](troubleshooting.md) —
  the "No Output Devices" dialog,
  BPM 0.0, halved and doubled tempos,
  and the silent recording
- [**Glossary**](glossary.md) — the
  terms, collected in one place

## What it doesn't cover

Being a DJ — taste, timing, and
reading a room are crafts this guide
cannot hand you; it teaches the
instrument. Sound quality is not
graded anywhere, because the lab
could not listen. Music production
and audio editing are neighbours'
work (chapter 14 points), and
training your ear is a practice, not
a chapter.

## How to use this guide

Read chapters 1 and 2 for the model.
Chapters 3 to 5 get you a program
and a library; chapter 6 is the one
to read slowly, because every later
chapter spends the numbers it puts
on trial. Chapters 7 to 9 are the
hands; 10 is the machine playing
alone; 11 and 12 are the doors to
audiences and hardware. The lab's
transcripts and screenshots live in
`mixxx-lab/`; its fixture tracks
were generated tones and pulse
trains, and the truth tables in the
chapters came from the database
those runs left behind.

---

## Part of the series

This guide is one of the [For Mere Mortals](https://paulsullivan33-dev.github.io/mere-mortals/) guides: plain-language guides to the tools programmers and makers use.

Related guides:

- [ffmpeg for Mere Mortals](https://paulsullivan33-dev.github.io/ffmpeg-for-mere-mortals/)
- [Audacity for Mere Mortals](https://paulsullivan33-dev.github.io/audacity-for-mere-mortals/)
- [Navidrome for Mere Mortals](https://paulsullivan33-dev.github.io/navidrome-for-mere-mortals/)

## License

The writing in this guide is licensed under [CC BY 4.0](https://github.com/paulsullivan33-dev/mixxx-for-mere-mortals/blob/main/LICENSE). Code examples and lab scripts are licensed under the [MIT License](https://github.com/paulsullivan33-dev/mixxx-for-mere-mortals/blob/main/LICENSE-CODE).
