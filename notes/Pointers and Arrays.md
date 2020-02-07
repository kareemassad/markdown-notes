---
tags: [SYSC2006 /Lecture 9]
title: Pointers and Arrays
created: '2019-11-01T17:45:23.404Z'
modified: '2019-11-27T19:55:22.619Z'
---

# Pointers and Arrays

### Syntax
* The declaration for an int array defines an array that can store 10 integers:
  ```c
  int a[10];
  int *pa;
  pa = &a[0];
  ```
* **pa** now points to <mark>element 0</mark> in the array (pa contains the address of a[0])

### Array Access via Pointers

* This copies the contents of x into <mark>a[0]</mark>
```c
int x = 3; 
*pa = x;
```

### Pointer Arithmetic
* Suppose <mark>pa</mark> points to any array element

  * <mark>pa+1</mark> is the address of the **next element**
  * <mark>pa+i</mark> is the address of the **i-th element** after the one pa points to

### Array Access via Pointers
After executing `pa = &a[0];`
* pa+1 is the address of a[1]
* *(pa+1) is the contents of a[1]
* pa+i is the address of a[i]
* *(pa+i) is the contents of a[i]

### Array Names and Addresses

* The name of an array is a synonym for the address of its zero'th element (beginning)
* This means that this:
  `pa = &a[0];`  == `pa = a;`

### Array Access: [] and * Operators

* Because the value of <mark>name a is &a[0]</mark> (the address of element 0), the value of experssion a+i is the address of the i-th element after a[0]
* Apply the dereferencing operator: <mark>*(a+i)</mark> is the <mark>contents</mark> of the i-th element after a[0].

This means that the expression `*(a+i)` == `a[i]`

<br>

* We can use a subscript with a pointer variable
* if **pa** points to an array, 
<mark>pa[i] == *(pa+i)</mark>

NOTE: An array name is  <mark>**NOT**</mark> a variable, so this is **NOT PERMITTED**: `a = pa;`
### Arrays as Function Arguments
A function that returns the average of an array of integers (uses **subscripts** to access array elements)

```c
double average(int data[], int n)
{
  double sum = 0; 
  int i;

  for(i = 0; i < n; i++){
    sum = sum + data[i];
  }
  return sum / n;
}
```

* When an array name is used as a function argument, C passes the **address** of the zero'th element.

EX:
```c
double average(int data[], int n);
int samples[100];
```
* C converts this call: 
  `average(samples, 50);`
to 
  `average(&samples[0],50);`

<br>

* Parameter data is actually <mark>a pointer to the first element of an array</mark> of integers

```c
double average(int data[], int n)
{
  ...
}
```
* We can rewrite the function use pointer expressions to access the array

### Average - Pointer-plus-offset *(data + i)

```c
double average(int *data, int n)
{
  double sume = 0;
  int i;

  for(i = 0; i < n; i++){
    sum = sum + *(data + i)
  }
  return sum / n;
}
```
### Pointer Arithmetic
* Pointers are variables, so we can add an subtract values from them; e.g., if pa points to an array element,
`pa = pa + 1;` updates pa to point to the next array

* Common idioms:
  pa += 1; or ++pa; or pa++;

### Average - "Walking Pointer" (data +=1)
```c
double average(int *data, int n) 
{
  double sum = 0;
  int i;

  for(i = 0; i < n; i++){
    sum = sum + *data;
    data += 1;
  }
  return sum / n;
}
```
Learn memory diagrams!

