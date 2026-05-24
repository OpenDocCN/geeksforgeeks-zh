# C |循环&控制结构|问题 5

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-5/](https://www.geeksforgeeks.org/c-loops-control-structure-question-5/)

预测以下程序的输出:

```cpp
#include <stdio.h>
#define EVEN 0
#define ODD 1
int main()
{
    int i = 3;
    switch (i & 1)
    {
        case EVEN: printf("Even");
                break;
        case ODD: printf("Odd");
                break;
        default: printf("Default");
    }
    return 0;
}
```

**(A)** 偶数
**(B)** 奇数
**(C)** 缺省
**(D)** 编译时错误

**答案:****(B)**

**解释:**表达式 **i & 1** 如果设置了最右位则返回 1，如果设置了最右位则返回 0 由于所有奇数都设置了最右边的位，控制转到标记为奇数的块。