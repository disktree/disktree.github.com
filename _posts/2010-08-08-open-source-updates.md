---
layout: post
title: Open source updates
---

HXMPP updates
* Full adobe air2 support (including native, secure air2 socket connections).
* Added support for websocket connections (javascript only)
* Minor fixes

HXMPP.lop test implementation
The LOP stuff is in the HXMPP repo since months, this is just an example usage.
The application consists of a javascript villein (a anonymous XMPP client) living in the browser and a farm running on the nekoVM. The villein spawns hscript virtual machines on the farm, sends some script .. the farm computes it and sends back the result. Variables live as long until the VM gets killed by the villein.

OWL
A XMPP server running on nodejs.
The project is in a very early state but already doing basic internal instant messaging (no S2S). I am f* enjoying the development process, since i got a good overview on the XMPP protocol over the last couple of years (time goes by in ludicrous speed) while developing the client library and don’t have to read XMPP specs that much .. straight forward coding .. this will change when i get to the S2S stuff. brrr.
Of course written in haXe using the nodejs type signatures from blackdog and (currently) a redis backend.
This project accepts and encourages contributions!
Ping me: xmpp://tong@jabber.spektral.at

Tsunami
A small framework for navigating on websites without reloading using #s (hashes). This is forked from the serverside mtwin templo library.
Here is an example (src).
What sux is that webkit based browser destroy pending XHR requests on hash tag URL changes therefore it breaks BOSH connections -> fail! Firefox does it right.

