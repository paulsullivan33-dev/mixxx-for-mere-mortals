# The Library

The library is where a DJ set is
really decided — long before the
first track plays, in the choosing.
This chapter walks the parts of it,
each grounded in what the lab's
database actually contained.

## The Tracks view

The main table is the whole
collection, sortable by any column,
searchable from the box above it:
type `artist:poets` or just a word
and the table filters as you go.
Columns worth a beginner's attention:

- **BPM and Key** — the analyser's
  measurements (chapter 6), the two
  numbers that say whether two tracks
  *can* be blended gracefully.
- **Rating** — your own stars, set by
  clicking in the column. The
  software never rates; taste is
  yours.
- **Last Played / Times Played** —
  Mixxx's memory. Play a track and
  both update; the lab watched them
  change in chapter 10.
- **Preview** — the headphone icon at
  each row's left plays the track in
  the preview deck, for auditioning
  without touching the main decks —
  on a machine with a headphone
  output, which the lab's was not.

## Crates

A **crate** is a hand-filed folder:
"wedding definites", "new this
month", "91 BPM openers" — any idea
you DJ by. A track can live in many
crates at once; crates don't move
files, they hold references. Make
one with **Library → Create New
Crate** (Ctrl+Shift+N), then drag
tracks onto it, or right-click
selected tracks and use the Crates
submenu. Deleting a crate deletes
the list, never the music.

## Playlists

A **playlist** is a crate with an
order: the planned shape of a set.
**Library → Create New Playlist**
(Ctrl+N) makes one; right-clicking
tracks offers *Add to Playlist*.
Playlists export, too — the Library
menu carries *Export Library to
Engine Prime*, a bridge to Denon's
ecosystem, which sits in the menu
whether or not you will ever use it.

One playlist in the database is
neither crate nor plan: the hidden
one named **Auto DJ**, which is the
queue of chapter 10, stored as an
ordinary playlist (the lab found it
as `playlist_id 1`, `hidden 1`).

## History

Mixxx keeps a diary. Every session
gets a playlist named by its date —
the lab's was `2026-10-30` — and
every track that plays is appended,
in order, with its position. Nobody
asked it to; it is simply what a
careful tool does. After a set, the
history is your setlist: what you
played, in the order you played it,
recoverable when someone asks "what
was that track after the slow one?"
Play counts and *Last Played* are
fed by the same machinery, and they
only move when a track genuinely
plays — loading a track into a deck
to look at it does not count.

## The database is the truth

Everything in this chapter is rows
in one SQLite file, which means you
can check this guide's claims — and
back up your own library — with
ordinary tools. The lab's whole
library, six tracks with analysis,
came to 200 KB. Copy
`mixxxdb.sqlite` somewhere safe
before any big reorganisation; the
crates, playlists, hotcues and play
counts of years live in it, and no
rescan can rebuild the parts that
were your judgement.
