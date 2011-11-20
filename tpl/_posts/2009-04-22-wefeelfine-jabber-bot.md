---
layout: post
title: WeFeelFine jabber bot
---
I’ve created a jabber bot for the [WeFeelFine](http://www.wefeelfine.org/) API.  
We Feel Fine is an exploration of human emotion on a global scale.
Since August 2005, We Feel Fine has been harvesting human feelings from a large number of weblogs.
Every few minutes, the system searches the world’s newly posted blog entries for occurrences of the phrases “I feel” and “I am feeling”.
When it finds such a phrase, it records the full sentence, up to the period, and identifies the “feeling” expressed in that sentence (e.g. sad, happy, depressed, etc.)

You can add ﻿wefeelfine@jabber.spektral.at to your contact list and request the bot with chat (or normal type) messages like:  
returnfield, returnfield,… $ option=value+option=value+…  
..where the returnfields specifiy the data which should get loaded (sentence is default).  
<br>
Possible returnfields are:
    imageid
    feeling
    posttime
    postdate
    posturl
    gender
    born
    country
    state
    city
    lat
    lon
    conditions

Key-value pairs after ‘$’  specify optional settings, which are:

    limit=0-1500 (num feelings to return)
    feeling=a-z (specify feeling)
    gender=0/1 (0=female,1=male)
    conditions=1-4 (1=sunny, 2=rainy, 3=snowy, 4=cloudy)
    counry=a-z
    state=a-z
    city=a-z
    postdate=date (YYYY-MM-DD)
    postmonth=1-12
    postyear=0-2009

<br>

The bot will return 5 values if no ‘limit’ options is specified.
Type ‘help’, ‘fields’ or ‘options’ to display the possible request fields.
<br>
Reuqest examples:
<br>

* Give me the most recent 5 sentences from vienna:
<pre class="code">
$city=vienna
</pre>
<br>

* Give me the last two sentences from people in canada who feel loved:
<pre class="code">
$limit=2 + feeling=loved + state=canada
</pre>

* Give me the last 3 sentences plus city, gender, latitude and longitude from people in paris who feel angry:
<pre class="code">
city,gender,lat,lon $ limit=3 + city=paris + feeling = angry
</pre>

<br>

[![wefeelfine](/img/wefeelfine.gif)](http://www.wefeelfine.org/)  
