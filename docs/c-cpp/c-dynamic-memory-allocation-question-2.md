# C |动态内存分配|问题 2

> 原文:[https://www . geesforgeks . org/c-dynamic-memory-allocation-question-2/](https://www.geeksforgeeks.org/c-dynamic-memory-allocation-question-2/)

考虑以下三个 C 函数:

```cpp
[PI] int * g (void) 
{ 
  int x= 10; 
  return (&x); 
}  

[P2] int * g (void) 
{ 
  int * px; 
  *px= 10; 
  return px; 
} 

[P3] int *g (void) 
{ 
  int *px; 
  px = (int *) malloc (sizeof(int)); 
  *px= 10; 
  return px; 
}
```

以上三个函数中，哪一个可能导致指针出现问题？(GATE 2001)
**(A)** 只有 P3
**(B)** 只有 P1 和 P3
**(C)** 只有 P1 和 P2

**(D)** P1、P2、P3

**回答:** **(C)**

**说明:**在 P1，指针变量 x 是 g()的局部变量，g()返回指向该变量的指针。g()返回后，x 可能会消失，因为 x 存在于堆栈中。所以，& x 可能会失效。
在 P2，指针变量 px 被赋予一个值，但没有给它分配内存。
P3 工作得非常好。使用 malloc()将内存分配给指针变量 px。所以，px 存在于堆上，它的存在将保留在内存中，即使在返回 g()之后，它仍然存在于堆上。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)