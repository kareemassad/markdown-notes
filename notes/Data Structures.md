---
attachments: [5-SYSC_2006_F19_C_Structures.pdf]
tags: [SYSC2006 /Lecture 5]
title: Data Structures
created: '2019-09-25T18:14:19.627Z'
modified: '2019-10-07T00:06:11.711Z'
---

# Data Structures

## What is a structure?
* One or more variables grouped togetherunder a single name
    * variables can have different types
* Allows a group of related variables to be treated as a unit
    * Able to deal with a group at the same time
* **A structure declaration doesn't allocate memory**
    * point is a **tag**, **NOT** a variable name
    * The key word **struct** is needed.

Example: a 2-D point
```C
struct point {
    int x;
    int y;
 };
```
You should visualize this as such:
<a href="https://imgur.com/I5C4E0e"><img width="400" height="200" src="https://i.imgur.com/I5C4E0e.png" title="Visualize C structs" /></a>

```C
struct point point3 = {320, 200}; // OK
```

<a href="https://imgur.com/N3cp37x"><img width="300" height="200" src="https://i.imgur.com/N3cp37x.png" title="source: imgur.com" /></a>

## Initialization
* This doesn't work:
```C
struct point point4;
point4 = {320, 200}; // No
```
* Must **cast** the expression {320, 200} to type
struct point

```C
point4 = (struct point) {320, 200}; // OK
```

## typedef
This declares point_t as a **synonym** for struct point. This means that you can write point_t instead fo struct point. 

```C
typedef struct point point_t;
```
* Examples:
```C
point_t point1, point2;
point_t point3 = {320, 200};
point_t point4;
point4 = (point_t) {320, 200};
```
We can also declare a structure and point_t together:
```C
typedef struct point {
  int x;
  int y;
} point_t;
```
## Structure Operation

* Structure members can be accessed individually
* Structures can be copied and assigned
* Structures can be passed as arguments to functions (pass by value semantics)
* Structures can be returned from functions
* The address of a structure can be calculated (more about this when we cover pointers)

## Accessing Structures
```C
instance_name.member_name
```
**CANT** use [] to access a member
A structure declaration defines a **type**

---
---

INCOMPLETE NOTES




