# Installing Mixxx

Mixxx is free software, published by
the Mixxx project at mixxx.org, with
installers for Windows and macOS and
packages for Linux. On Linux the
easiest honest route is your
distribution's own package archive:
it is the same program, it arrives
with the libraries it needs, and
updates come with the rest of your
system. That is the route this lab
took, on Ubuntu 24.04:

```
$ sudo apt-get install mixxx
```

which installed Mixxx **2.4.0**
(package `2.4.0+dfsg-2build4`) and
its data package. The `dfsg` in the
version is Debian's mark that the
archive repacked the source to its
own free-software rules; the program
itself is the project's 2.4.0.

## The version check that isn't

Every guide in this series likes to
prove an install with `--version`.
Mixxx teaches humility here: it is a
graphical program, and even asking
its version starts the whole
application. With no display at all
it refuses, in Qt's own words:

```
qt.qpa.plugin: Could not load the Qt platform plugin "xcb"
```

Give it a display — even a virtual
one, as this lab did with Xvfb — and
`mixxx --version` answers properly:

```
Mixxx 2.4.0
```

The useful options it accepts are
listed by `mixxx --help`; the one
this lab relied on is
`--settings-path <path>`, which tells
Mixxx to keep its settings, database
and logs in a folder you choose
instead of the default `~/.mixxx`.
Point it somewhere of your own and
every experiment stays in one place.

## The first run

First runs have two ceremonies.

**Choosing the library.** Before the
main window, Mixxx opens a file
dialog titled *Choose music library
directory*, suggesting your `Music`
folder. This is the folder it will
scan for music (chapter 4). Pick
where your collection actually
lives; you can add more folders
later in the preferences, under
Library.

**The sound question.** Mixxx then
looks for something to play sound
through. On a normal computer it
finds your speakers or headphones
and says nothing. On the lab's
machine it found nothing — no card,
no devices — and said so, in a modal
dialog:

```
No Output Devices
```

Dismissing it let startup finish.
Mixxx wrote a sound configuration
anyway (`soundconfig.xml`: the ALSA
API, 48,000 Hz, no device), and ran
on its fallback clock, as chapter 2
described. On your machine the same
dialog is the sign that Mixxx cannot
see your audio interface: check the
cable, check that the operating
system can see the device, then open
Mixxx's preferences under Sound
Hardware and choose it there.

By the end of the first run, the
settings folder holds the pieces the
rest of this guide uses: `mixxx.cfg`
(written when Mixxx exits cleanly),
`mixxxdb.sqlite` (the library
database — it upgrades its own
schema on first sight; the lab's log
walked it up to schema version 28),
`mixxx.log`, and folders for
analysis data, controllers, effects
and broadcast profiles.
