# Troubleshooting

Failures the lab met, and the ones
the manual meets most.

**Mixxx opens with a dialog: "No
Output Devices".** *(Lab.)*
It found no sound device. If your
machine truly has none, Mixxx still
runs — on the fallback "Network
stream" clock, per its log — and
everything except hearing works.
If your machine *has* one: check
the operating system sees it (the
lab's ALSA layer reported `cannot
find card '0'` — the machine really
was empty), then Preferences →
Sound Hardware and assign the
device explicitly. USB interfaces
that were plugged in after Mixxx
started need a restart of Mixxx to
appear.

**A track's BPM is 0.0.**
It was scanned but never analysed —
the two are different passes
(chapter 4). Select it, right-click
→ Analyze → Analyze. Loading it
into a deck also queues analysis.

**The BPM is double or half what it
should be.**
The counter counted every other
beat. Right-click → Adjust BPM →
÷2 or ×2, then check the grid
against the waveform. Common on
hip-hop (counted fast) and drum &
bass (counted slow), and nothing is
broken — beats are beats at both
countings.

**Sync makes the blend worse.**
The grid is wrong — position, not
just speed. Adjust BPM lets you drag
the first beat onto the waveform's
first real hit. If the track drifts
even with a correct start, it was
never a fixed tempo: analyse as
constant BPM won't save it; chapter
8's hands will.

**The key looks absurd.**
On drums, spoken word or a test
tone, it is absurd — the detector
must print something (Cm for a kick
drum, Am for a concert A). Ignore
the column for tracks with no notes
to detect.

**A track is in the folder but not
the library.**
Rescan (Ctrl+Shift+L). If it still
won't appear, the file is likely a
format Mixxx can't read or a tag
wreck it files oddly — check the
search box is empty, and look in
the log (`mixxx.log` in the settings
folder) for the file's name.

**You deleted a file and Mixxx
still lists it.**
By design: rescans mark missing
tracks deleted rather than dropping
rows that playlists reference.
Right-click → Hide from Library for
the row you can't stand seeing.

**Auto DJ stopped.**
The queue ended. Refill it, or set
Auto DJ's random refill to draw
from a large crate. Also check it
wasn't switched off by a deck
interaction — the enable button's
orange state is the truth.

**The library feels irreplaceable
and fragile.**
It is one file, `mixxxdb.sqlite`,
in the settings folder
(`~/.mixxx` by default, or wherever
`--settings-path` points). Back it
up like you'd back up photos: the
music can be re-bought; your cues
and crates cannot.

**Recording came out silent.**
You recorded the main output while
the crossfader or MAIN knob left
the audience hearing nothing — the
file is an honest copy of that.
Test recordings before real sets,
and check the level in the file,
not just its existence.
