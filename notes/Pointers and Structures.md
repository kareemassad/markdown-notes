---
attachments: [8_SYSC_2006_F19_C_Pointers_and_Structures.pdf, ptr-point1.png]
tags: [SYSC2006 /Lecture 8]
title: Pointers and Structures
created: '2019-10-18T17:34:34.559Z'
modified: '2019-11-07T03:16:36.451Z'
---

# Pointers and Structures

###### Date: 09/10/2019
[](@attachment/8_SYSC_2006_F19_C_Pointers_and_Structures.pdf)

**NOTE:**
`p = &x;` Reads: Assign to p (a pointer) the address of x.

### The & Operator and Structures
The <mark><span style="color:red">& operator</mark> </span>can be applied to structures
  ```C
  point_t* ptr;
  point_t point1 = {320, 200};
  ...
  ptr = &point1;
  ```
ptr now points to point1:
<span style="color:blue">**contains the address of the first byte in the memory allocated to point1**</span>
 ![point to x to 5](@attachment/ptr-point1.png)

### Pointer Defreferencing

<span style="color:red">*ptr</span> is the entire structure
<span style="color:blue">(*ptr).x</span> and <span style="color:blue">(*ptr).y</span> are the members
* Read as: " (*ptr).x is the x member of the structure pointed to by ptr "
* <span style="color:blue">parentheses are required</span>, because the dot operator has higher precedence than *

### The -> Operator
If ptr is a pointer to a structure, **ptr->member** is a shorthand for (*ptr).member

```C
point_t* ptr;
point_t point1;
...
ptr = &point1;
ptr->x = 320; // (*ptr).x = 320;
ptr->y = 200; // (*ptr).y = 200;
```
### Function Arguments
* Don't pass large structures as function arguments
  * pass-by-value semantics
  * **copying an entire structure requires time and memory** (the function parameter)

**INSTEAD,** <mark>pass pointers to structures</mark> as function arguments

## Examples: addpoints (Version 1)

```c
void addpoints (point_t* ptr1, const point_t* ptr2)
{
    ptr1->x = ptr1->x + ptr2->x;
    ptr1->y = ptr1->y + ptr2->y;
}
// NOTE: Pointer to a constant:
// you cannot change the value it is pointing to.

point_t point1, point2; //init

point1 = makepoint(320, 200);
point2 = makepoint(30, 40);

addpoints(&point1, &point2);

//notice syntax on addpoints call 
//When addpoints returns, point1 contains the sum of the two points, i.e., point1 gets changed.
```

## Examples: addpoints (Version 2)

**What if we don't want the function to modify point1?**
<mark>rewrite addpoints so it is passed as a pointer to the structure where the **sum** will be stored.</mark>
```c
void addpoints (const point_t* ptr1, const point_t* ptr2, point_t* sum)
{
    sum->x = ptr1->x + ptr2->x;
    sum->y = ptr1->y + ptr2->y;
}

point_t point1, point2, result; //init

point1 = makepoint(320, 200);
point2 = makepoint(30, 40);

addpoints(&point1, &point2, &result);

//when addpoints returns, result contains the sum of the two points.
```

### Returning a Pointer

Rewrite `addpoints` so that it returns a pointer to a `point_t` structure containing the sum of the two points:
```c
point_t* addpoints(const point_t* ptr1, const point_t* ptr2);
```

## Examples: addpoints (Version 3)


```c
void addpoints (const point_t* ptr1, const point_t* ptr2, point_t* sum)
{
    sum->x = ptr1->x + ptr2->x;
    sum->y = ptr1->y + ptr2->y;
}

point_t point1, point2, result; //init

point1 = makepoint(320, 200);
point2 = makepoint(30, 40);

addpoints(&point1, &point2, &result);

//when addpoints returns, result contains the sum of the two points.
```














