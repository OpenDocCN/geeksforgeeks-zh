# C |指针基础|问题 3

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-3/](https://www.geeksforgeeks.org/c-pointers-question-3/)

以下程序的输出？

```cpp
#include <stdio.h>

int main()
{
    int *ptr;
    int x;

    ptr = &x;
    *ptr = 0;

    printf(" x = %d\n", x);
    printf(" *ptr = %d\n", *ptr);

    *ptr += 5;
    printf(" x  = %d\n", x);
    printf(" *ptr = %d\n", *ptr);

    (*ptr)++ ;
    printf(" x = %d\n", x);
    printf(" *ptr = %d\n", *ptr);

    return 0;
}
```

**(A)**x = 0
* ptr = 0
x = 5
* ptr = 5
x = 6
* ptr = 6
T8】(B)x =垃圾值
*ptr = 0
x =垃圾值
*ptr = 5
x =垃圾值
*ptr = 6
**(C)** x = 0
* ptr = 0
x = 5
* ptr = 5
x =垃圾值
*ptr =垃圾值
**(D)**x = 0
* ptr = 0
x = 0
* ptr = 0
x = 0
* ptr = 0

**答案:**

```cpp
  int *ptr;  /* Note: the use of * here is not for dereferencing, 
               it is for data type int */
  int x;

  ptr = &x;   /* ptr now points to x (or ptr is equal to address of x) */
  *ptr = 0;   /* set value ate ptr to 0 or set x to zero */

  printf(" x = %d\n", x);   /* prints x =  0 */
  printf(" *ptr = %d\n", *ptr);  /* prints *ptr =  0 */

  *ptr += 5;        /* increment the value at ptr by 5 */
  printf(" x  = %d\n", x);  /* prints x = 5 */
  printf(" *ptr = %d\n", *ptr); /* prints *ptr =  5 */

  (*ptr)++ ;         /* increment the value at ptr by 1 */
  printf(" x  = %d\n", x);  /* prints x = 6 */
  printf(" *ptr = %d\n", *ptr);  /* prints *ptr =  6 */

```