# Broadcasting and Recording

Two buttons at the top of the window
share one idea: the main output is
worth keeping, or worth sending.
**REC** keeps it, as a file.
**ON AIR** sends it, live, to an
internet radio server. The lab had
no server and no audience, so this
chapter is documented-only in its
behaviour — but the machinery's
defaults are in the lab's own files,
and those are quoted exactly.

## Broadcasting: Mixxx as a radio source

Internet radio has two halves: a
**server** (Icecast or Shoutcast)
that listeners connect to, and a
**source** that feeds it the music.
Mixxx is a source. In Preferences →
Live Broadcasting you describe your
server in a **broadcast profile**;
Mixxx then connects, and everything
on the main output streams.

First run had already created the
lab a default profile — before any
broadcasting was configured, the
settings folder held
`broadcast_profiles/Connection 1.bcp.xml`,
and its contents are the shape of
every profile:

```
<ProfileName>Connection 1</ProfileName>
<Port>8000</Port>
<StreamName>Mixxx</StreamName>
<Bitrate>128</Bitrate>
<Channels>2</Channels>
<MetadataFormat>$artist - $title</MetadataFormat>
```

Per the manual: Mixxx speaks to
**Icecast 1 and 2** and **Shoutcast
1** directly, and to Shoutcast 2 via
the Shoutcast 1 protocol provided a
stream name is set. Streams to
Icecast can be MP3 or Ogg Vorbis;
to Shoutcast, MP3. The metadata
line — artist and title of what's
playing, sent to the server and on
to listeners' players — follows
that `$artist - $title` pattern,
customisable per profile. Profiles
hold the server's host, port,
mountpoint (required for Icecast),
login and password; treat the file
like any credential, because it is
one. Reconnect behaviour is part of
the profile too: the default retries
up to ten times, because live radio
that gives up at the first dropped
packet is not live for long.

The **ON AIR** button connects and
disconnects; while connected it
stays lit. And chapter 1's line
applies with force: a broadcast is a
publication. The licences that cover
playing records in a room do not
automatically cover streaming them
to the world, and sorting that out
belongs to whoever runs the station.

## Recording: the red button

**REC** writes the main output to a
file as it plays — your set, exactly
as the audience heard it, fades,
mistakes and all. Preferences →
Recording chooses the format:
lossless WAV or FLAC for an archive
copy, MP3 or Ogg Vorbis for a file
that travels. Recordings land in
the folder set there (Mixxx keeps a
**Recordings** view in the sidebar
listing what it has made), and a cue
file can be written alongside,
marking where each track started —
the difference between one long
audio file and a set you can
navigate. Recording costs a little
CPU and some disk; a two-hour set in
WAV is a gigabyte and a quarter,
give or take, which is why the
compressed formats exist.

The oldest advice in recording
applies unchanged: test the whole
chain before the set you care about.
A recording of silence is the
canonical failure, and it is only
ever discovered afterwards.
