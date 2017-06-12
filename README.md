# Garry's Mod MIDI Player

[![Steam Workshop](https://img.shields.io/badge/Steam-Workshop-417a9b.svg?style=flat-square&colorA=555555&maxAge=60)](https://steamcommunity.com/sharedfiles/filedetails/?id=935799359) [![Travis Build Status](https://img.shields.io/travis/garrysmodlua/gmod-midiplayer/master.svg?style=flat-square&maxAge=30)](https://travis-ci.org/garrysmodlua/gmod-midiplayer)

This is a MIDI player for Garry's Mod.

This MIDI player is far from perfect. Several issues with sound playback in the Source engine prevent any improvements. The only likely path to improving this MIDI player is for Garry's Mod to ditch its outdated Chrome 18 based embedded browser (Awesomium) with one based on modern versions of Chrome (Chromium Embedded Framework). Then, an HTML5 implementation of a more accurate MIDI player can be used. Until then, here's whats wrong:

* Notes that require a sound to be pitch-shifted by a factor higher than 2.55 will be ignored. While an upper limit makes sense, Source made it way too low.
* If too many notes are played at once using the same sound file, some of them will be ignored. This is due to limitations in Source.
* The pitch of a note will not always be accurate. This is due to Source forcing what should be a floating point number into an 8-bit integer.
* Volume of notes may be wrong. The cause of this is unknown, but is probably the fault of Source. An HTML5 version of the MIDI player using the same methods produces correct output.
* The implementation of the SoundFont 2 spec is not complete. This is due to limitations in Source engine.
