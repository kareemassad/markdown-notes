---
tags: [C Course /Data Types]
title: Enums and Chars
created: '2019-12-03T04:27:16.828Z'
modified: '2019-12-03T04:40:51.082Z'
---

# Enums and Chars

### Enums

* a data type that allows a programmer to define a variable and specify the valid values that could be stored into that variable
  * can create a variable name "myColor" and it can only contain of the primary colors

```c
enum identifier {id1,id2,id3}; //syntax definition

enum primaryColor {red, yellow, blue};  //define

```
* This defines the two variable myColor and gregsColor to be type of primaryColor
```C
enum primaryColor myColor, gregsColor
```
`myColor = red;` works but `myColor = green;` doesn't.

* Could also assign by numbers. The first name in the list is 0

```c
enum direction { up, down, left = 10, right}
```
* an enumerated data type direction is defined with the values up, down, left, and right
* up = 0 because it appears first in the list
* down = 1 because it appears next
* left = 10 because it is explicitly assigned this value
* right = 11 because it appears immediately after left in this list

### Char
* Chars represent a single character such as the letter 'a', the digit character '6', or a semicolon (';')
* Character literals use single quotes such as 'A' or 'Z'
* You can also declare char variable to be unsigned: `unsigned char = 'z'`
* Char =/= string
```C
char broiled // declare a char variable
broiled = 'T';  //OK
broiled = T;  //No! Thinks T is a variable
broiled = "T"; //No! Thinks it is a string
```

* You can use the numerical code to assign values from ASCII: `char grade = 65`

### Escape Characters


