eyePatch
========

Enable viewing of MHEG obscured DVB-T channels.

There is no support in eyeTV for MHEG, so unencrypted channels that are obscured by an MHEG caption are unwatchable.

eyePatch makes those channels watchable.

How to install
==============
Copy eyePatch.bundle to /Library/Application Support/EyeTV/plugins . (You might need to make a new Plugins folder first). Then restart EyeTV.

What it does
============
DVB-T channels are sent as a series of streams, combined with a program map table that describes the content of the streams. In MHEG obscured channels, the program map table deliberately mis-describes the video and/or audio streams.

MHEG obscured channels are concealled as follows
*   Audio and video channels are labelled private streams
*   MHEG 'unlock' application is added
*   The MHEG application can route the private streams for viewing under software control.

eyePatch opens these channels
*   It detects if the channel master timebase is a private stream
*   This stream is likely also a video stream
*   Other private streams are likely to be audio
*   MHEG streams are removed from the channel map
*   If the program map table is changed, its version number is incremented to force eyeTV to refresh
*   No channel specific data is required. eyePatch is based only on data published in DVB and MPEG standards documents.

Note that all content is streamed in plaintext to the receiver. eyePatch alters only unencrypted program map tables.

This currently works for all MHEG obscured video content on Freeview UK, and is likely to work on other networks too.
