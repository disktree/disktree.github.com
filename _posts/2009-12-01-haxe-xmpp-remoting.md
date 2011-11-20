---
layout: post
title: HaXe/XMPP remoting
tags: [xmpp,haxe,remoting]
---
I have added a (async) haXe remoting remix to the HXMPP library where very XMPP entitiy (client) can act as remote host.
Which means i can call methods on a client from any other entity (a server or another client).
Pretty cool for round based games maybe.  

One important thing missing is a access model for the remote host.
Currently every entity is allowed to call methods.
(Workaround would be be to add a IQ/HXR filter to block remaing packet collectors)
