---
tags: [SYSC2006 /Lecture 9]
title: Summary
created: '2019-11-27T19:45:47.395Z'
modified: '2019-11-27T19:54:53.920Z'
---

# Summary

* As **parameters** in a function definition:

<mark>int data[]</mark> == <mark>int *data</mark> 

Parameter data is a pointer, initialized as a local variable, with an **address** when the function is called

* The function can treat data as an array of integers, and access elements using subscripts; e.g., **data[i]**

* The function can treat data as a pointer to an integer(actually, a pointer to the first integer in a block of consecutive integers), and access integers in the block using pointer notation; 
e.g., <mark>*data, *(data+i)</mark>
