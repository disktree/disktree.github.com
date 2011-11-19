---
layout: post
title: 99 bottles of beer
---

Here is my haXe submission to the 99 bottles of beer song collection.
( The website holds a collection of the song ‘99 bottles of beer’ in 1311! programming languages. )
I got annoyed of a comment on the previous haXe version claiming that its twice as long as the COBOL version. So i thought it can be done better/shorter.

It builds the complete song/string before output, so i was able to do some performance measurements:

Run program 100 times:
neko: 0m0.618s
cpp: 0m1.106s
php: 0m2.292s
js (rhino): 0m41.954s

Run 1000 times in a loop (internal):
flash-standalone(10.0.32.18): 0m0.277s
flash-plugin(10.0.32.18,firefox3.5.5): 0m0.294s
php: 0m0.291s
js (rhino): 0m0.474s
neko: 0m0.529s
cpp: 0m8.793s

