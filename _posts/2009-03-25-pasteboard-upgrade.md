---
layout: post
title: Pasteboard upgrade
---
I’ve upgraded our pasteboard application. Beside a rewrite of the web front and server code i’ve added functionality to paste via jabber ( built with HXMPP targeting nekoVM ):

How to normal type message paste:
Type your language name into the subject.
Type your code into the body.

How to chat type message paste (in case your client does not support ‘normal’ type messages, like pidgin or the gtalk web widget ):
Send: language$$$code

Mind: The account has to be in your roster (accepts all presence subscriptions automaticly). On success the bot responds with message including the URL to your fresh, syntax highlighted paste. If the language is unkown your input gets filed under plaintext.

The used codehighlighter script by Joakim Ahnfelt also got an update and now supports: html, xml, javascript, php, css, perl, ruby, c, c++, c#, java, scala, haxe, python, haskell, latex, plus a few obscure languages.

[ paste.disktree.net ]
