---
attachments: [7_SYSC_2006_pointers_and_functions_F19_C_temp.pdf, swap().png]
tags: [SYSC2006 /Lecture 7]
title: Pointers and Functions
created: '2019-10-04T17:42:42.439Z'
modified: '2019-11-09T04:41:51.285Z'
---

# Pointers and Functions
###### Date: 04/10/2019
[](@attachment/7_SYSC_2006_pointers_and_functions_F19_C_temp.pdf)

Here is a function that swaps it's arguments:

```c
void swap(int *px, int *py)
{
  int temp;
  temp = *px;
  *px = *py;
  *py = temp;
}

int main(void)
{
  int a = 5, b = 10;  // Point A & B
  swap(&a, &b);
  return 0;
}
```
![point to x to 5](@attachment/swap().png)
**NOTE:** This would not swap if they arent pointers. This is because pointers are passed by reference and otherwise it would be passed by value. When passing by value, the value from the function does not change the value in main. 


