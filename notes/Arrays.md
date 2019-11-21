---
tags: [SYSC2006 /Lecture 3]
title: Arrays
created: '2019-09-20T17:05:48.264Z'
modified: '2019-10-07T00:05:09.442Z'
---

# Arrays 
###### DATE: 9/20/2019

Arrays start at 0, so an array samples would have it's first entry start at 0 and end at 9.

* Syntax: 

``` C
element-type name[capacity];
```
1) Example: This declares an area with size 10.

``` C
double samples[10]; 
```
2) Example: Overwrite the 2nd element with the value stored in the 3rd element.

``` C
i = 1;
samples[i] = samples[i+1];
```
3) Example: Calculate the average of the first n elements in array samples.

``` C
double average;
double sum = 0.0;
for (int i =0; i < n; i += 1) {
  sum = sum + samples[i];
}
average = sum / n;
```
* Put the calculate-average code in a function

``` C
double average_samples (double x[], int n)
{
    double sum = 0;
    for (int i = 0; i < n; i++) {
        sum = sum + x[i];
    }
    return sum / n;
}
```
* The first parameter: double x[]
  - notice that *we don't specify the array's capacity
  - First the argument can be any array of doubles

* The second parameter: int n
  - number of array elements that the function should process; e.g., x[0], x[1], ..., x[n-1]

## Functions Changing Arrays

Function parameters are always (in C) passed by value **EXCEPT** for arrays, they are passed by reference. 

If a funtion modifies elements in an array parameter, it is actually modifying the array argument. 

1) **Pass by Value:** In this parameter passing method, values of actual parameters are copied to function’s formal parameters and the two types of parameters are stored in different memory locations. So any changes made inside functions are not reflected in actual parameters of caller.

2) **Pass by Reference:** Both actual and formal parameters refer to same locations, so any changes made inside the function are actually reflected in actual parameters of caller.

### Call the function this way:

``` C
double average;
...
average = average_samples(samples, 6);
```
* Array argument is samples, **not** samples[] or samples[6] or samples[10]

**passed by REFERENCE**
result1 = function1 (samples);
**passed by VALUE**
result2 = function2 (samples[i]);

``` C
void init_array(int arr[], int n, int initial)
{
    for (int i = 0; i < n ; i++) {
        arr[i] = initial;
    }
}

//Zero the first 5 elements and numbers[5] to numbers[9] are uninitialized

int numbers[10];
init_array(numbers,5,0);

```

### Calculating Array Capacity

``` C
int numbers[10];
int capacity;
capacity = sizeof(numbers)/sizeof(numbers[0]);

```
* sizeof(numbers) evaluates to the amount of memory allocated to the **entire array**.

* sizeof(numbers[0]) evaluates to the amount of memory used by **one array element**.

```C
int numbers[10];
int capacity;
capacity = sizeof(numbers)/sizeof(numbers[0]);
```











