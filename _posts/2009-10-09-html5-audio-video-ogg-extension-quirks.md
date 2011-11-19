---
layout: post
title: HTML5 audio/video .ogg extension quirks
---

While adding support for wrapping media files into the according html5 tag (audio or video) to my realtime microblogging application at roar.disktree.net i discovered a nasty situation as follows:
How to know if a file with the ‘.ogg’ extension is video rather than audio from within javascript ?

Possible workarounds to distinguish (in case of my application):

    Read the file header serverside and save the result somewhere.
    Ok, but requires extra work.
    Try to discover filetype from the ID3 tag.
    Not save.
    Read the file header in flash (which is able to read data at byte level).
    Ok for files served from same domain only.

Anyhow, no solution for javascript, so it would be good to agree on:
Name audio files ‘ogg’, video files ‘.ogv’ and tell everybody to do so!

Or am i overlooking something ?