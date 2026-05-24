# C |宏&预处理器|问题 5

> 原文:[https://www . geesforgeks . org/c-宏-预处理器-问题-5/](https://www.geeksforgeeks.org/c-macro-preprocessor-question-5/)

```cpp
#include <stdio.h>
#define ISEQUAL(X, Y) X == Y
int main()
{
    #if ISEQUAL(X, 0)
        printf("Geeks");
    #else
        printf("Quiz");
    #endif
    return 0;
}
```

以上程序的输出？
**(A)** 极客
**(B)** 测验
**(C)** 极客或测验
**中的任何一个(D)** 编译时错误

**答案:****(A)**

**解释:**条件宏*#如果 ISEQUAL(X，0)* 被展开预处理结束后，所有未定义的宏都用默认值 0 初始化。由于宏 X 尚未定义，因此用 0 初始化。于是，**极客**就打印出来了。