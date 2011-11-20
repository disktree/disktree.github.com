---
layout: post
title: Flash policy nekoVM server
---
The changed security settings in flash player >= 9,0,124,0 does not allow you to make a socket connection directly to a server without first obtaining explicit permission from that server in form of a policy-file-request.
Follow [this](http://www.adobe.com/devnet/flashplayer/articles/socket_policy_files.html) article for more information and the flash-policy servers written in perl and python adobe is providing.  
I thought it would be nice to have a neko one, so it shall be developed (haXe/neko).  
Thanks to the [neko.net.ThreadServer](http://haxe.org/api/neko/net/threadserver) ([tutorial](http://haxe.org/doc/neko/threadserver)) class writing a multi threaded socket server is an easy task.  
<br>
[flash-policy-server-source.zip](/files/fpserver.zip)
