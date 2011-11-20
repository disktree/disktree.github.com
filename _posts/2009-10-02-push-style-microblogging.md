---
layout: post
title: Push style microblogging
---
A small project i am lately working on is a microblogging service,
utilizing havver to push new messages (sent from a jabber client) to the users browser in realtime without the need of page reloading.
It uses anonymous authentication, which allows logging in without a own jabber account.

haXe really unfolds its power for this project since i target 4 different platforms from one language and use the same jabber library clientside and for the commandline bot. Flash for the jabber client, JS for printing html, PHP for delivering HTML and nekoVM for the jabber bot.
<br>
Go test it:
[**http://roar.disktree.net**](http://roar.disktree.net)
