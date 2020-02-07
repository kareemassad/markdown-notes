---
tags: [C Course /Data Types]
title: Basic Data Types
created: '2019-12-03T03:16:09.489Z'
modified: '2019-12-03T04:20:58.848Z'
---

# Basic Data Types
```C
int x
float a
double b
char c
_Bool d
```

### int: Integers
* Is a signed integer
  * Can be positive, negative, or zero
* Can be used to store hexadecimal numbers such as 
```c
int rgbColor = 0xFFEF0D;
```

### float: floating point numbers
* Decimal number
* Can be expressed in scientific such as 1.7e^4 

### double: Similar to float
* Similar to float but can store more data.
* Can store 2x as many significant digits
* Most computers represent double values using 64bits

### _Bool: boolean expression
* can be used to store just the values 0 or 1.
* used to indicate on/off, yes/no, or true/false
* 0 is false, 1 is true

```c
#include <stdio.h>

int main()
{
  float jason = 23.333;
  double kareem = 55.5555555555e+11;
  _Bool boolVariable = 1; //true

  return 0;
}
```

