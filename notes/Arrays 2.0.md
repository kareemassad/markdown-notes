---
tags: [SYSC2006 /Lecture 3]
title: Arrays 2.0
created: '2019-09-25T17:10:01.676Z'
modified: '2019-10-07T00:05:16.391Z'
---

# Arrays 2.0
###### DATE: 9/25/2019

#### Const Qualifier 
If you declare a variable to be a **const**, you're telling the compiler that it's a read-only variable and that it won't be changed throughout its existance. 

```C
int main(void) {
const int NUM_ELEMENTS = 8; // Number of elements
int userVals(NUM_ELEMENTS); // User Numbers
int i = 0;                  // Loop Index
```

Use to prompt user to input values
```C
for (i=0; i< NUM_ELEMENTS; i++) {
    printf("Value: ");
    scanf("%d", & (userVals[i]));
}
```

Use to reverse array's elements
```C
for (i=0; i< NUM_ELEMENTS; i++) {
    userVals[i] = userVals[NUM_ELEMENTS - i]; // Swap
}
```
Use to print all numbers
```C
printf("\nNew Values: ");
for (i=0; i < NUM_ELEMENTS; i++) {
    printf("%d ", userVals[i]);
}

return 0;
}
```

Pass by reference is a pointer
```C
int addList (int array[], int i)
{
    array[i] = array[i] + 50;
    return 0;
}
```

