# Recipes

Small complete jobs, start to
finish. Anything marked *(lab)* was
done, for real, in this guide's lab.

## Prepare a folder of new music *(lab)*

1. Put the files in a folder Mixxx
   already watches.
2. **Library → Rescan Library**
   (Ctrl+Shift+L). New rows appear
   with their tags read and BPM 0.0.
3. Select the new tracks (search the
   album name, Ctrl+A), right-click →
   **Analyze → Analyze**.
4. Read the BPM column with chapter
   6's scepticism: tap along to one
   track and check the machine agrees
   with your foot.

## Queue an unattended evening *(lab)*

1. Select the night's tracks in the
   library.
2. Right-click → **Add to Auto DJ
   Queue (replace)**.
3. Open **Auto DJ** in the sidebar,
   check the order, set the
   transition style and length.
4. Press the enable button; it turns
   orange. Test with ten minutes
   before you trust it with five
   hours — and check the queue is
   long enough, or point the random
   refill at a big crate.

## Prove what played last night *(lab)*

1. Open the sidebar's **History** and
   pick the date: the setlist, in
   order.
2. For the sceptical version, the
   same rows are in the database —
   the dated playlist in
   `PlaylistTracks`, and
   `timesplayed`/`last_played_at` in
   `library`. (Transcript
   `t03-autodj.txt` shows both.)

## Fix a track analysed at double tempo

1. Right-click the track → **Adjust
   BPM** → halve (÷2). The beat grid
   rescales.
2. Play the start and check the
   waveform's grid lines sit on the
   beats you hear.
3. The same dialog sets the first
   beat by hand when the grid is the
   right speed but the wrong phase.

## Blend two tracks by hand

1. Load A, play it out. Load B, set
   its cue on the first beat, route B
   to your headphones only.
2. Start B on A's downbeat. Drift?
   Nudge the spinny; drift again the
   same way? Move B's tempo slider a
   hair toward A's BPM.
3. When the beats hold together,
   bring B's channel fader up with
   its **Low** EQ down, crossfade,
   and trade the lows at the join.
4. Chapter 8 is this recipe with the
   training wheels discussed honestly.

## Stream a set to your own Icecast

*(Documented — the lab had no
server.)*

1. Run or rent an Icecast server;
   note its host, port, mountpoint
   and source password.
2. Preferences → Live Broadcasting:
   fill a profile with those, format
   MP3, a bitrate your uplink affords
   (128 kbps is the common floor).
3. Connect with **ON AIR**; check
   the stream from a second device
   before the audience does.
4. Rights, chapter 1: broadcasting
   is publishing.
