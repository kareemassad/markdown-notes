---
tags: [SYSC2006 /Midterm_Prep]
title: Summary Up till Pointers and Arrays
created: '2019-11-09T02:46:01.938Z'
modified: '2019-11-09T03:24:28.276Z'
---

# Summary Up till Pointers and Arrays
###### DATE: 11/8/2019

## Pointers are variable that store address of another variable

Let's say that in the memory, variable `int a;` is stored at address 204 and `int *p` is stored in address 64

```c
int a; //initialize integer
int *P; //initialize pointer P

P = &a;  //set P equal to the address of a
a = 5;  
```

If we want to print P, &a, &P, and *P what are the outputs?
```c
print P   // = 204
print &a  // = 204
print &P  // = 64
print *P  // = 5 (This is called dereferencing)
```

We stored an address at P and now we can get the value stored at that address

We can modify the value at that reference and change the output such that:
```c
*P = 8; //we say that the address of a (&a) at P
print a //equal to 8
```
### RECAP:
Pointers - variables that store address of other variables

```c
int a;  //integer
int *p; //pointer to integer

char c; //character
char *P0; //pointer to character

double d; //double
double *P1; //pointer to double

//to get the address at a variable
P = &a; //P stores the address of a
a = 8;  //let's say a is 8

// then *P = a
```

## Working with pointers

What is the output?

1)  

```c
#include <stdio.h>
int main()
{
  int a;
  int *p;
  printf("%d\n",p);
}
```
The output is a **RUN-TIME ERROR** as the variable P is being used without being initialized.

2) 

```c
#include <stdio.h>
int main()
{
  int a;
  int *p;
  p = &a; // &a = address of a
  printf("%d\n",p); //print p
  printf("%d\n",*p); //print value at address pointer by p
}
```
This outputs 3800000 (memory address where a is located) and -858993460.
The second value is a garbage value as `a` isn't initialized.

3)

```c
#include <stdio.h>
int main()
{
  int a;
  int *p;
  a = 10;
  p = &a; // &a = address of a
  printf("%d\n",p); //print p
  printf("%d\n",*p); //print value at address pointer by p
}
```
This outputs 5504548 (memory address where a is located) and 10.

4)

```c
#include <stdio.h>
int main()
{
  int a;
  int *p;
  a = 10;
  p = &a;   // &a = address of a
  printf("a = %d\n",a); //print before

  *p = 12;  // dereferencing
  printf("a = %d\n",a;) //print after
}
```
This outputs a = 10 then a = 12.


## Pointer Arithmatic

Is it possible to increment a pointer variable? YES! But, it will increment by 1 cell, which is *4 bytes*
```c
#include <stdio.h>
int main()
{
  int a = 10;
  int *p;
  p = &a;
  
  //Pointer Arithmetic
  printf("%d\n",p);   //p is 2002
  printf("%d\n",p+1); //p is 2006
}
```






