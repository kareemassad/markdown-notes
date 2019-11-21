---
attachments: [6-SYSC-2006-intro-to-pointers.pdf, pointer_1.png, pointer_2.png, pointer_3.png, pointer_4.png]
tags: [SYSC2006 /Lecture 6]
title: Pointers in C
created: '2019-10-03T22:32:14.043Z'
modified: '2019-10-07T00:06:34.306Z'
---

# Pointers in C
###### Date: 03/10/2019 
[](@attachment/6-SYSC-2006-intro-to-pointers.pdf)
### Memory Oragnization

* Memory can be viewed as a collection of consecutively-numbered cells

  * usually, each cell hols an 8-bit **byte**

  * a _char_ is stored in one cell (byte)

  * a 32-bit _int_ is stored in 4 adjacent cells

    * on smaller machines, values of type _int_ are 16 bits wide are are stored in pairs of adjacent cells

* The cell numbers are known as **_addresses_**

### Variables & Pointers

* A variable:
a symbolic name for a group of cells
  * number of cells depends on the variable's type
  * It contains an actual **value**
* Pointer:
a variable that contains the **address** of a variable

### Pointer Variable Declarations
```c
int *p;
```
* Declares a variable named p, whose <span style="color:blue">type</span> is “<span style="color:blue">pointer to int”</span>

* _type_ * means “**pointer to _type_**”
 
<span style="color:red"> This does _**NOT**_ declare a variable named *p, whose type is _int_. </span>

### Address-of (&) Operator
* This assigns the address of x to variable p.
```c
int *p;
int x = 1, y = 2;
p = &x;
```
* p now _**“points to”**_ x.

![Visualize Pointers](@attachment/pointer_1.png)

### Dereferencing (*) Operator
```c
*p = 5;
```
- The variable pointed to by p is assigned by 5.
- x now contains 5
![point to x to 5](@attachment/pointer_2.png)

* If p points to x, then *p can be used anywhere x can be used
```c
*p = *p + 10;
// is equivalent to
x = x + 10;
``` 
* X now contains 15.
![using *p as x](@attachment/pointer_3.png)

### Precedence of Operators
* Unary <span style="color:red">**&**</span> and <span style="color:red">__*__</span> have higher precedence than the arithmetic, comparison and logical operators

```c
y = *p + 1;
```
* Dereferencing the pointer is performed before the addition
* Takes the value pointed to by p, adds 1, then assigns the result (16) to y.

### Pointer Assignment
A pointer can be assigned to another pointer:
```c
int *p2;
p2 = p;
```
* This copies the contents of p into p2
* So, p2 and p now point to the same variable
![p2 = p](@attachment/pointer_4.png)





















