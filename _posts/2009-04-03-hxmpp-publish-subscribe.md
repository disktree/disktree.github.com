---
layout: post
title: HXMPP Publish Subscribe
---
Today i’ve added PubSub support to our HXMPP library.
Pubsub is a notification system like web syndication (RSS, Atom, ..) for the XMPP protocol with some great advantages:

* Realtime. Unlike regular web syndication, pubsub is a pushing system.
As soon as a new item is published at a node, the service notifies all registered subscribers. This is the last hurdle (in terms of time) evolution of global information technology is overcoming by delivering information for human unrecognizeable delays (millisecondes). Unlike rss, email,.. more like global smoke signals. )

* Bandwith. New information is pushed only once.
Assume you have 50 feeds on your watchlist and every feed is about 10k in size and gets polled every 30 mins (the default configuration time in my RSS-reader), .. you end up having 1mb polled in 1h (720mb/month) mostly for /dev/null space since a lot of feeds just update in day intervals. This produces unecassery cost$ if you don’t have a flatrate connection (keyword mobile). Not to mention the extra costs for network transfer at servers (and power consumption)!

* Configuration is built into the service itself, not in the software you use for.
Publishers are able to config their service to their needs (like: manage subscription requests, cache items, not routing events to offline storage, block users,..).
Subscribers can config their subscriptions, for example: to get just the title of the published data (bandwith again!) or to set the presence types which are allowed to receive notifications.

Overall the current system (RSS stuff) is doing it completely wrong and hopefully gets dropped and replaced by pubsub like systems very soon!
