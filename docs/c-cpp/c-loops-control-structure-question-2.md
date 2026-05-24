# C |循环&控制结构|问题 2

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-2/](https://www.geeksforgeeks.org/c-loops-control-structure-question-2/)

```cpp
#include <stdio.h>
#define PRINT(i, limit) do \
                        { \
                            if (i++ < limit) \
                            { \
                                printf("GeeksQuiz\n"); \
                                continue; \
                            } \
                        }while(0)

int main()
{
    int i = 0;
    PRINT(i, 3);
    return 0;
}
```

以上程序中**极客 sQuiz** 打印了多少次？
**(A)**1
**(B)**3
**(C)**4
**(D)**编译时错误

**回答:****(A)**

**说明:**如果一个宏需要多行展开，最好把那些行写在**里面做**极客 sQuiz** 打印一次后，控制到达 while 语句检查情况。因为条件为假，所以循环终止。**