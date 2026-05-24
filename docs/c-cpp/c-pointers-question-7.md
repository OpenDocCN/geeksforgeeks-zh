# C |指针基础|问题 7

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-7/](https://www.geeksforgeeks.org/c-pointers-question-7/)

```cpp
#include<stdio.h> 
int main() 
{ 
   int a; 
   char *x; 
   x = (char *) &a; 
   a = 512; 
   x[0] = 1; 
   x[1] = 2; 
   printf("%d\n",a);   
   return 0; 
}
```

以上程序的输出是什么？
**(A)** 机器依赖
**(B)**513
**(C)**258
**(D)**编译器错误

**答案:****(A)**

T21】解释:输出是 513 在一个小端机。为了理解这个输出，让整数用 16 位存储。在小端序机器中，当我们做 x[0] = 1 和 x[1] = 2 时，数字 a 变为 00000001 0000010，这是小端序机器中 513 的表示。