# Controllers and Vinyl Control

Everything so far assumed a mouse.
Real DJing is done with hands on
hardware — knobs that turn, faders
that slide, platters that spin —
because two hands can do two things
at once and a mouse cannot. This
chapter is the hardware door.
The lab owns no DJ hardware, so
everything here is documented-only,
from the Mixxx manual and from one
countable fact in the installed
package itself.

## Controllers

A DJ **controller** is a box shaped
like the Mixxx window: two jog
wheels, a mixer section, pads and
knobs, connected by USB. Inside,
it's a MIDI device — every control
sends standard messages — plus, in
better models, a built-in sound
device with the four channels
chapter 7 wanted (main out,
headphones out).

Mixxx speaks to a controller through
a **mapping**: an XML file naming
which MIDI message drives which
Mixxx control, often with a
JavaScript companion for anything
clever (lights, displays, shift
layers). The countable fact: the
lab's ordinary Ubuntu package
installed **294 mapping files** in
`/usr/share/mixxx/controllers/` —
Akai, Allen & Heath, Denon, Hercules,
Native Instruments, Numark, Pioneer
and dozens more, alphabetically from
Akai's MPD24 onwards. If a controller
is at all mainstream, its mapping is
already on your disk; connecting is:
plug in USB, open Preferences →
Controllers, enable the device, pick
the mapping. Mappings you write or
download live in the settings
folder's `controllers/` directory —
the lab's existed, empty, from the
first run.

Honest limits: brand-new controllers
outrun the mapping library for a
while, and some manufacturers keep
their best tricks (screens, motor
platters) behind their own software.
The mapping being XML and script is
the Mixxx answer — anything the
hardware sends can, in principle, be
mapped — but "in principle" has
written many weekend projects.

## Vinyl control

The other door is backwards in time
on purpose. **Vinyl control** (also
called DVS, digital vinyl system)
lets real turntables drive Mixxx: a
special record — a **timecode
vinyl**, carrying not music but a
precise timing signal — plays on an
ordinary deck; Mixxx listens to the
signal through a sound device,
knows exactly where the needle is
and how fast the record moves, and
plays the digital track to match.
Scratch, and the file scratches.
Per the manual, Mixxx understands
the Serato CV02 and Traktor
MK1/MK2 timecode records, so the
vinyl from the two big ecosystems
works. You need a phono-capable
audio interface with enough inputs,
the records themselves, and
turntables — at which point the
setup costs more than most
controllers, which is exactly why
its users swear by it: nothing else
feels like vinyl, because it is.

## Sound hardware, the quiet prerequisite

Both doors lean on the thing the lab
didn't have: a proper audio
interface. The preferences page the
lab met as a *No Output Devices*
dialog is where interfaces are
assigned — main, headphones, booth,
microphone, vinyl inputs — per
channel, per device. The number on
the box that matters is independent
stereo outputs: one is a laptop,
two is a DJ setup.
