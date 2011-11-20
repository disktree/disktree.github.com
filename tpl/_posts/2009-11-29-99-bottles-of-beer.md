---
layout: post
title: 99 bottles of beer
---

[Here](http://www.99-bottles-of-beer.net/language-haxe-2248.html) is my haXe submission to the 99 bottles of beer song collection 
(the website holds a collection of the song ‘99 bottles of beer’ in 1311! programming languages).   
It builds the complete song/string before output, so i was able to do some performance measurements.  
<br>
1000 iterations:  
* flash-standalone(10.0.32.18): 0m0.277s  
* flash-plugin(10.0.32.18,firefox3.5.5): 0m0.294s  
* php: 0m0.291s
* javascript (rhino): 0m0.474s
* neko: 0m0.529s
* cpp: 0m8.793s

