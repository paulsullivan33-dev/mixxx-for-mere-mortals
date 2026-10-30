# Your First Library

A DJ program with an empty library is
a mixer connected to nothing. This
chapter fills the library once, on
purpose, and proves what happened.

## The lab's fixture shelf

The lab's music was manufactured, so
its truth would be known in advance.
Six short MP3 files were generated
with ffmpeg — pulse trains (a low
thump and a click, repeating) at
exactly 120, 128, 100 and 90 beats
per minute, one melodic arpeggio
stepping at 110 BPM, and one pure
440 Hz test tone with no beat at
all — each tagged with title, artist,
album, genre and track number. The
artists are invented; the tempos are
not. Chapter 6 spends them.

Your shelf is simpler: the music
files you already own, in the folder
you chose at first run.

## The scan

When Mixxx knows a music folder, it
**scans** it: walks the folder and
its subfolders, opens every audio
file, and writes one database row
per track with what the file's tags
say. Here is the lab's evidence,
read from `mixxxdb.sqlite` after the
first scan (transcript
`t01-scan-and-tags.txt` in
`mixxx-lab/`):

```
-- directories
/home/hatch/workspace/mixxx-labwork/music

id  artist            title                  album
--  ----------------  ---------------------  -------------------
1   Harbour Lights    Arpeggio Study No. 1   Quiet Harbour
2   Studio Reference  Concert A (Test Tone)  Test Tones
3   The Tone Poets    Night Drive Loop       Lab Fixtures Vol. 1
4   The Tone Poets    Pulse Train in C       Lab Fixtures Vol. 1
5   Harbour Lights    Slow Morning Groove    Quiet Harbour
```

Alongside each title, Mixxx recorded
the album, genre, track number,
duration (30.04 s for a 30-second
file — the extra fraction is MP3
frame padding, and Mixxx reports the
file's real length, not the tag's
claim), sample rate and bitrate.
What the scan does **not** do is
listen: every BPM column still read
0.0 at this point, except one — and
that exception is chapter 6's first
lesson. Tags are claims; analysis is
measurement.

A file whose tags are missing or
wrong scans in anyway, filed under
whatever the tags do say — often
nothing. Mixxx edits tags from its
Properties dialog (right-click a
track), and serious tidying is
better done with a dedicated tag
editor before scanning. The library
only ever shows what it was told.

## Adding music later: rescan

You will buy, rip or record new
tracks. Put the files in a folder
Mixxx watches and tell it to look
again: **Library → Rescan Library**,
or its shortcut, **Ctrl+Shift+L**.
The lab proved the path by adding a
sixth file, *Second Cup Waltz*, to
the folder after the first scan and
rescanning: within seconds the
library count went from five to six,
the new row carrying its tags and —
again — a BPM of 0.0, because
rescanning reads files; it does not
analyse them.

The mirror image also holds: delete
a file from the folder and rescan,
and Mixxx marks the track deleted
rather than forgetting it outright,
so a playlist that mentioned it
doesn't silently change shape.
Right-clicking a track offers *Hide
from Library* for the gentler
version: the file stays on disk,
the row leaves your sight.

## Where the folders live

The list of watched folders is in
the database's `directories` table —
the lab's held exactly the one path
it had chosen — and in the
preferences under Library, where you
can add and remove them. Mixxx also
rescans on startup, which is why
music added while Mixxx was closed
simply appears next time.
