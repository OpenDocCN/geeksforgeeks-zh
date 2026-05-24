# C |宏&预处理器|问题 12

> 原文:[https://www . geesforgeks . org/c-宏-预处理器-问题-12/](https://www.geeksforgeeks.org/c-macro-preprocessor-question-12/)

预测后续程序的输出？

```cpp
#include <stdio.h>
#define MAX 1000
int main()
{
   int MAX = 100;
   printf("%d ", MAX);
   return 0;
}
```

**(A)**1000
**(B)**100
**(C)**编译器错误
**(D)** 垃圾值

**答案:****(C)**

**说明:**编译预处理阶段后，函数 main()更改为如下

```cpp
int main()
{
   int 1000 = 100;  // COMPILER ERROR: expected unqualified-id before numeric constant
   printf("%d ", 1000);
   return 0;
}
```

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/macro-preprocessor-gq/)