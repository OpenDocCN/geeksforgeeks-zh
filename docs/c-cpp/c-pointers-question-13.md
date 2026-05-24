# C |指针基础|第 11 题

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-13/](https://www.geeksforgeeks.org/c-pointers-question-13/)

```cpp
#include<stdio.h> 
void f(int *p, int *q) 
{ 
  p = q; 
  *p = 2; 
} 
int i = 0, j = 1; 
int main() 
{ 
  f(&i, &j); 
  printf("%d %d \n", i, j); 
  getchar(); 
  return 0; 
}
```

**(A)**2 2
**(B)**2 1
**(C)**0 1
**(D)**0 2

**回答:****(D)**

**解释:**见下图 f()附注释说明。

```cpp
/* p points to i and q points to j */
void f(int *p, int *q) 
{ 
  p = q;    /* p also points to j now */
 *p = 2;   /* Value of j is changed to 2 now */
}
```