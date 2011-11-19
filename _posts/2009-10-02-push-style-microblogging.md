---
layout: post
title: Push style microblogging
---
A small project i am lately working on is a microblogging service, utilizing jabber/XMPP to push new messages (sent from a jabber client) to the users browser in realtime without need of page reloading.
It uses anonymous authentication, which allows to consume it without logging into a jabber account.

haXe really unfolds its power for this project since i target 4 different platforms from one language and use the same jabber library clientside and for the commandline bot. Flash for the jabber client, JS for printing html, PHP for delivering HTML and nekoVM for the jabber bot.

Go test it:
http://roar.disktree.net

The site uses the css3 font-face feature, .. a compatible browser is needed to view the site correctly!
(displays nice in firefox3.5 and safari, shitty in opera)

