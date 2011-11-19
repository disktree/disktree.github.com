---
layout: post
title: Array sort performance
---
Some performance comparisons on sorting arrays( 100 x random float array with length of 1000 ).

nekoVM
haXe Array.sort: 5.4
Quicksort:  0.3
Insertionsort: 7.5

firefox 3.0.3 js
haXe Array.sort: 6.4
Quicksort:  0.2
Insertionsort: 4.2

flashplayer10
haXe Array.sort: 0.2
Quicksort: 0.1
Insertionsort: 7.5

php 5.2.4
Fatal error: Maximum execution time of 30 seconds exceeded on all tests so i tried with just 10 arrays instead of 100:
haXe Array.sort: 15.3
Quicksort: 4.6
Insertionsort: exceeded

Edit:
Test for flashplay10, with flash.Vector instead of Array:
(i’ve increased the arrays(vectors) to test to 1000 instead of 100 to get a more precise result, so dont compare with the results above )
haxeArray.sort: 1.75
Quicksort: 0.6

Resume:
Use quicksort if you dont need a custom comparison function!