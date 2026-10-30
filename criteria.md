# Writing criteria for this guide

Every "for Mere Mortals" guide is written to the same nine-point
standard, so a reader who trusts one can trust the rest. Here it
is, with the verification notes for this particular guide below.

1. **Fix it first.** Reader outcomes lead, not action items: each
   chapter opens by naming the outcome it delivers, shows a check
   the reader can run to confirm they got it, and a reasonable
   reader finishes able to state what was done, what it means,
   and what to try next.
2. **Plain language.** Short sentences, everyday vocabulary,
   technical terms defined on first use. No slang, and no
   idioms that only make sense in one country — the reader may
   be translating as they go.
3. **No dead ends.** A guide never tells the reader to do
   something it cannot show them how to verify. Every claim a
   reader relies on — an install, a command, an output — is
   something this guide demonstrates or clearly labels
   documented-only below.
4. **Live-verified where it matters.** Procedures are run for
   real in the guide's lab wherever the build machine allows it,
   and the transcripts kept in the repository are the evidence.
   What could not be run is listed honestly below, never
   presented as if it had been.
5. **General audiences.** Nothing in this guide — examples,
   fixtures, names, addresses — is modelled on any particular
   reader or author's real life, network, or organisations.
   The lab's tracks are generated tones and pulse trains with
   invented artists.
6. **Standalone.** A reader needs this guide, its lab, and
   nothing else. Where another guide would genuinely help, it
   is pointed to once, by name, and the chapter still completes
   without it.
7. **Honest about limits.** Chapter 15 names what the tool
   cannot do: analysis that answers even when the question made
   no sense, no real-time stem separation, grids that drifting
   music breaks, keys that are a detector's opinion, no
   Rekordbox booth preparation, backups left to the reader.
8. **The ethics rule is in the text, early.** Chapter 1 and
   chapter 11 draw the line plainly: Mixxx plays music that has
   owners, and recording a mix to hand out or broadcasting one
   to the internet distributes their work. The machinery is
   taught; the permission is the reader's to hold.
9. **Builds clean.** The site builds with MkDocs in strict mode
   with no warnings, and a fresh reader following the chapters
   in order reaches the stated outcome of each.

## Verification notes for this guide

The build machine is a shared Ubuntu 24.04 sandbox (about
7.9 GB of memory, several builders working at once; timings
are therefore not quoted). Mixxx **2.4.0** (distribution
package `2.4.0+dfsg-2build4`) was installed with the package
manager in the ordinary way — the archive's lock was free, so
no extraction workaround was needed for this guide — and run
unmodified under Xvfb, a virtual display, with
`--settings-path` pointing into the lab folder so every file
it wrote stayed in one place. Three other builders' programs
shared the virtual display at times; the windows are separate
and the screenshots in `mixxx-lab/` are Mixxx's own.

The lab machine had **no sound card, no speakers and no way
to listen**, and no DJ hardware. Every claim about what
Mixxx *did* is therefore a record: rows in its SQLite
database (`mixxxdb.sqlite`), its log, its saved configuration
files, and screenshots of its window. Nothing in this guide
grades how anything sounds.

The fixtures are six MP3 files generated with ffmpeg, each
30–32 seconds: pulse trains (a low thump plus a click) at
exactly 120, 128, 100 and 90 BPM, one arpeggio stepping at
110 BPM through the notes C–E–G–C, and one pure 440 Hz sine
tone with no beat at all. All carry invented titles, artists
("The Tone Poets", "Harbour Lights", "Studio Reference") and
albums; one, and only one, carries a TBPM tag (128), so a
believed number could be told apart from a measured one.

Run for real, with transcripts or screenshots as evidence:

- Version and `--help`, including the discovery that even
  `--version` needs a display (Qt's "xcb" failure without
  one) and works with one (t00).
- First run: the *Choose music library directory* dialog,
  the schema upgrade of a fresh `mixxxdb.sqlite` to version
  28, and the modal **No Output Devices** dialog on a
  machine whose sound layer reported no card at all; the
  log's fallback line — "Output sound device clock
  reference not set! Using 'Network stream'" — is quoted in
  chapter 2 (t04).
- Library scan of the five first fixtures, proven from the
  database: the `directories` row, and per-track artist,
  title, album, genre, track number, duration (30.04 s for
  30-second files), sample rate and bitrate as Mixxx read
  them (t01).
- Analysis of all five (right-click → Analyze → Analyze),
  proven from the database: the TBPM-tagged track showing
  128.0 *before* analysis; measured BPMs of 120.0, 128.0,
  100.0 and 110.0 against true tempos of 120, 128, 100 and
  110; the beatless tone returned at 86.25 BPM; keys C
  (the arpeggio) and Cm/Am for content with no real key;
  BeatGrid provenance `qm-tempotracker:0`, key provenance
  `KeyMap-1.0`; ReplayGain values; waveform analysis rows
  and files (t02).
- Rescan: a sixth fixture added to the folder and picked up
  via Library → Rescan Library (Ctrl+Shift+L) within
  seconds, arriving with BPM 0.0 — scanned, not analysed
  (t01, chapter 4).
- Auto DJ, complete: the queue built with *Add to Auto DJ
  Queue (replace)* and read back from the hidden `Auto DJ`
  playlist (six rows, positions 1–6); Auto DJ enabled
  (button orange, "Full Intro + Outro", 10 second
  transitions); and after roughly two minutes, two tracks
  with `timesplayed = 1` and `last_played_at` timestamps,
  the dated History playlist holding the played tracks in
  order, the queue consumed from six to two — plus the
  exit dialog "A deck is currently playing. Exit Mixxx?"
  and lit mixer meters in its screenshot (t03,
  `mixxx-lab/*.png`).
- Configuration as written by the program itself:
  `soundconfig.xml` (ALSA, 48,000 Hz, no device), the
  default broadcast profile's XML (port 8000, bitrate 128,
  metadata format `$artist - $title`), and the package's
  294 shipped controller mapping files, counted on disk.

Documented only — described from the Mixxx manual
(manual.mixxx.org, version 2.4), not run, and the text does
not claim otherwise:

- Everything audible: blend quality, EQ and filter sound,
  scratching feel, latency, headphone cueing as heard.
- Deck craft performed by hand: setting hotcues and loops
  in anger (their controls were seen in the running program
  and their storage found in the database's `cues` table,
  including the four analyser-written markers per fixture),
  sync behaviour in a live blend, sampler use.
- Broadcasting to a real Icecast/Shoutcast server and
  recording a real set: the profiles, buttons and formats
  are as quoted; no server existed here to receive a stream
  and no set was recorded.
- Controllers, MIDI mapping in use, and timecode vinyl:
  no hardware exists in this lab. Manual claims (Serato
  CV02, Traktor MK1/MK2 timecode support) are the manual's.
- The Windows and macOS installers, and skins beyond the
  LateNight skin the lab ran.
- The neighbour programs of chapter 14 — characterised, not
  run or benchmarked.

Fixtures are this guide's own and deliberately generic:
generated tones and pulse trains, invented artists and
albums, no real songs, names, organisations or events.
Nothing commercial was played, recorded or broadcast.
