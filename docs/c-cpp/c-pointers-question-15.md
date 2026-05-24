# C |指针基础|第 13 题

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-15/](https://www.geeksforgeeks.org/c-pointers-question-15/)

```cpp
int f(int x, int *py, int **ppz) 
{ 
  int y, z; 
  **ppz += 1; 
   z  = **ppz; 
  *py += 2; 
   y = *py; 
   x += 3; 
   return x + y + z; 
} 

void main() 
{ 
   int c, *b, **a; 
   c = 4; 
   b = &c; 
   a = &b; 
   printf("%d ", f(c, b, a)); 
   return 0;
}
```

**(A)**18
**(B)**19
**(C)**21
**(D)**22

**回答:****(B)**

**讲解:**让我们一行一行地了解这一点

```cpp
  /* below line changes value of c to 5\. Note that x remains unaffected by 
    this change as x is a copy of c and address of x is different from c*/
  **ppz += 1  

  /* z is changed to 5*/
  z  = **ppz; 

  /* changes c to 7, x is not changed */
  *py += 2; 

   /* y is changed to 7*/
  y = *py;    

  /* x is incremented by 3 */
   x += 3;    

  /* return 7 + 7 + 5*/
  return x + y + z;
```