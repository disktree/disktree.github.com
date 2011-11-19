---
layout: post
title: HaXe/XMPP remoting
---

I have added a (async) haXe remoting remix to the HXMPP library using XMPP as transport, and created following example to test it:
[ HXR flash example ]

The app:
* embeds the same SWF twice in a HTML site
* the SWF logs into the jabber server with passed account information using SASL-MD5 authentication (password is hidden)
* creates an instance of the application
* create a haXe remoting host in context of the instance to listen for incoming calls.
* create a haXe remoting proxy in context of the instance for outgoing calls.
* on button click:
** creates random values for the next circle to add to the other entities canvas
** adds a circle to the remote entities canvas by calling a function on the proxy

A great benefit of HXR (haXe-remoting) over XMPP is that EVERY entitiy/target, also clients, can act as remote host. Which means i can call methods on a client from any other entity (a server or another client). Pretty cool for round based games and stuff.

Important thing missing is a access model for the remote host.
Currently every entity is allowed to call methods.
(Workaround would be be to add a IQ/HXR filter to block remaing packet collectors)
