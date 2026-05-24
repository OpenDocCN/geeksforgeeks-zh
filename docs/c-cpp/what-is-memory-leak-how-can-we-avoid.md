# 什么是内存泄漏？如何才能避免？

> 原文:[https://www . geesforgeks . org/什么是内存泄漏-我们如何避免/](https://www.geeksforgeeks.org/what-is-memory-leak-how-can-we-avoid/)

当程序员在堆中创建一个内存而忘记删除它时，就会发生内存泄漏。

内存泄漏的后果是通过减少可用内存的数量来降低计算机的性能。最终，在最坏的情况下，太多的可用内存可能被分配，系统或设备的全部或部分停止正常工作，应用程序失败，或者系统速度大大降低。

对于守护程序和服务器这样的程序来说，内存泄漏是一个特别严重的问题，顾名思义，它们永远不会终止。

## c

```cpp
/* Function with memory leak */
#include <stdlib.h>

void f()
{
   int *ptr = (int *) malloc(sizeof(int));

   /* Do some work */

   return; /* Return without freeing ptr*/
}
```

为了避免内存泄漏，堆上分配的内存应该总是在不再需要时释放。

## c

```cpp
/* Function without memory leak */
#include <stdlib.h>;

void f()
{
   int *ptr = (int *) malloc(sizeof(int));

   /* Do some work */

   free(ptr);
   return;
}
```