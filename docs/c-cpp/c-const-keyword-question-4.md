# C++ | const 关键字|问题 5

> 原文:[https://www.geeksforgeeks.org/c-const-keyword-question-4/](https://www.geeksforgeeks.org/c-const-keyword-question-4/)

```cpp
#include <stdio.h>
int main()
{
   const int x;
   x = 10;
   printf("%d", x);
   return 0;
}
```

**(A)** 编译器错误
**(B)**10
**(C)**0
**(D)**运行时错误

**答案:****(A)**

**说明:**除初始化时外，不能更改“const”变量的值。编译器会检查这一点。

[本题小考](https://www.geeksforgeeks.org/c-plus-plus-gq/const-keyword-gq/)