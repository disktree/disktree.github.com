---
layout: post
title: Flash policy nekoVM server
---
The changed security settings in flash player >= 9,0,124,0 does not allow you to make a socket connection directly to a server without first obtaining explicit permission from that server in form of a policy-file-request. Follow this article for more information and the flash-policy servers written in perl and python adobe is providing.

I thought it would be nice to have a neko one, so it shall be developed ( using haXe of course ). Thanks to the neko.net.ThreadServer class writing a multi threaded socket server is an easy task.

[flash-policy-server-source.zip]

This could easy be extended with db-logging, .., whatever.
Follow this link for a neko.net.ThreadServer tutorial.

