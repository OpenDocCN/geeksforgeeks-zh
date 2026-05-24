# C |宏&预处理器|问题 4

> 原文:[https://www . geesforgeks . org/c-宏-预处理器-问题-4/](https://www.geeksforgeeks.org/c-macro-preprocessor-question-4/)

```cpp
#include <stdio.h>
#define X 3
#if !X
    printf("Geeks");
#else
    printf("Quiz");

#endif
int main()
{
        return 0;
}
```

**(A)** 极客
**(B)** 小测验
**(C)** 编译器错误
**(D)** 运行时错误

**答案:****(C)**

**解释:**一个程序通过以下步骤转换为可执行程序

1)预处理

2) C 代码到目标代码的转换

3)链接

第一步处理宏。因此，在预处理步骤之后，代码被转换为以下代码。

```cpp
printf("Quiz");
int main()
{
        return 0;
}

```

上面的代码产生错误，因为 printf()是在 main 之外调用的。以下程序运行良好，并打印了“测验”

```cpp
#include 
#define X 3

int main()
{
#if !X
    printf("Geeks");
#else
    printf("Quiz");

#endif
    return 0;
}

```