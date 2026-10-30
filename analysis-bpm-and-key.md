# Analysis: BPM and Key

Analysis is Mixxx listening on your
behalf: once per track, in advance,
so that during a set the answers are
already on screen. This chapter puts
its two famous numbers — tempo and
key — on trial, against tracks whose
truth the lab knew before Mixxx did.

## Running it

Scanning reads tags. Analysis is
separate, and slower, because it
decodes the audio. Select tracks in
the library, right-click, and open
the **Analyze** submenu:

- **Analyze** — fill in whatever is
  missing: waveform, beat grid, key,
  loudness.
- **Reanalyze** — do it again from
  scratch (after an upgrade, or when
  you distrust an old result).
- **Reanalyze (constant BPM)** — for
  tracks recorded from a steady
  source; it forbids the tracker from
  wandering.

Loading a track into a deck also
queues its analysis if it has none,
which is why tracks analyse
themselves, one by one, during a
first set. The batch route is
kinder: select the whole library the
night before.

Results land in the database.
Waveform passes are recorded in a
`track_analysis` table (versions
`Waveform-5.0` and
`WaveformSummary-5.0`), the waveform
pictures themselves in files under
the settings folder's `analysis/`
directory, and the numbers — as rows
in the library itself, with their
provenance: `BeatGrid-2.0` by
`qm-tempotracker:0`, keys by
`KeyMap-1.0`.

## The trial

The fixtures, again: pulse trains
generated at exactly 120, 128 and
100 BPM, an arpeggio stepping at
110, and a pure 440 Hz tone. One
file, *Night Drive Loop*, also
carried a tag claiming BPM 128. The
results (transcript `t02-analysis.txt`):

```
title                  true BPM   Mixxx BPM   key
---------------------  --------   ---------   ---
Pulse Train in C       120        120.0       Cm
Night Drive Loop       128        128.0       Cm
Slow Morning Groove    100        100.0       Cm
Arpeggio Study No. 1   110        110.0       C
Concert A (Test Tone)  none       86.25       Am
```

Four lessons, in order of comfort:

**Steady tempos are exact.** Every
pulse train came back at its true
tempo to the tenth of a beat. Real
music made to a click — most
electronic dance music, most modern
pop — is this regular, and the
tracker is this good at it.

**A tag is believed until analysis
disagrees.** Before analysis ran,
*Night Drive Loop* already showed
128.0 — imported straight from its
TBPM tag. Analysis agreed, so the
number never visibly changed. A
*wrong* tag would have survived
until a reanalyze replaced it: the
column does not say which numbers
were measured and which were merely
repeated, so treat suspiciously round
perfection in a downloaded library
with suspicion.

**Keys are real, but the input must
have some.** The arpeggio — the only
fixture with actual notes, C E G C —
came back **C**, the right key. The
pulse trains came back **Cm**, which
is the analyser doing its best with
a thump: a kick drum has pitch
content but no key, and the honest
reading of "Cm" on a drum loop is
"it had to print something". Key
detection is a musical judgement by
algorithm; on real songs it is
useful, and it is still a judgement.

**A beatless sound gets a beat
anyway.** The 440 Hz tone — twenty
seconds of *aaaa*, no rhythm in it
at all — came back at **86.25 BPM**,
key Am. The number is meaningless;
the tracker found the faint frame
boundaries of the MP3 and built a
tempo out of them. This is the
single most useful thing in this
chapter: **analysis always answers**.
It is your job to know when the
question made no sense — a live
recording that drifts, a classical
piece, a spoken intro — and the fix
is the tap-tempo and beat-grid
editing under right-click's *Adjust
BPM*, or analysing as constant BPM.

## Loudness, quietly

Analysis also stored a **ReplayGain**
value per track — the lab's fixtures
ranged from 0.46 to 1.12 — which
Mixxx uses to level playback so one
track doesn't arrive noticeably
hotter than the last. You never see
it work; you only notice its absence
in software that lacks it.

## Half time and double time

The classic honest error: a track at
70 BPM analysed as 140 (or 140 as
70), because beats are beats at
either counting. It is not wrong
exactly — but it breaks sync
arithmetic and set planning. *Adjust
BPM* offers ×2 and ÷2 for precisely
this, and checking new purchases
against your own foot-tap is the
thirty-second habit that catches it.
