# C |数组|问题 4

> 原文:[https://www.geeksforgeeks.org/c-arrays-question-4/](https://www.geeksforgeeks.org/c-arrays-question-4/)

以下程序的输出？

```cpp
#include<stdio.h> 

int main() 
{ 
  int a[] = {1, 2, 3, 4, 5, 6}; 
  int *ptr = (int*)(&a+1); 
  printf("%d ", *(ptr-1) ); 
  return 0; 
}
```

**(A)**1
**(B)**2
**(C)**6
**(D)**运行时错误

**回答:****(C)**

**解释:** & a 是整个数组的地址 a[]。如果我们在& a 上加 1，就得到“a[] + sizeof(a)的基址”。这个值被类型化为 int *。所以 ptr 指向存储 6 后的内存。ptr 被类型化为“int *”，并打印值*(ptr-1)。因为 ptr 在 6 点后指向记忆，所以 ptr–1 指向 6。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)