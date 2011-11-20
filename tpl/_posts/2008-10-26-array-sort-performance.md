---
layout: post
title: Array sort performance
---
Some performance comparisons on sorting arrays(100 random float arrays with size of 1000).

* **nekoVM**  
 haXe Array.sort: 5.4  
 Quicksort:  0.3  
 Insertionsort: 7.5  

* **javascript** (firefox 3.0.3)  
 haXe Array.sort: 6.4  
 Quicksort:  0.2  
 Insertionsort: 4.2  

* **flashplayer10**  
 haXe Array.sort: 0.2  
 Quicksort: 0.1  
 Insertionsort: 7.5  

Resume: Use [quicksort](http://haxe.org/doc/snip/quicksort) if you dont need a custom comparison function :)