# C |宏&预处理器|问题 1

> 原文:[https://www . geesforgeks . org/c-宏-预处理器-问题-1/](https://www.geeksforgeeks.org/c-macro-preprocessor-question-1/)

```cpp
#include <stdio.h>
#define PRINT(i, limit) do \
                        { \
                            if (i++ < limit) \
                            { \
                                printf("GeeksQuiz\n"); \
                                continue; \
                            } \
                        }while(1)

int main()
{
    PRINT(0, 3);
    return 0;
}
```

以上程序中**极客 sQuiz** 打印了多少次？
**(A)**1
**(B)**3
**(C)**4
**(D)**编译时错误

**答案:****(D)**

**解释:****PRINT**宏在预处理器时间即编译前展开宏展开后，if 表达式变为: **if (0++ < 3)** 。由于 **0** 是一个常数，只代表 r 值，应用增量运算符会产生编译时错误:需要左值。lvalue 表示具有某个地址的内存位置。