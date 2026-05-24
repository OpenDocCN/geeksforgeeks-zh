# C |循环&控制结构|问题 6

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-6/](https://www.geeksforgeeks.org/c-loops-control-structure-question-6/)

```cpp
#include <stdio.h>
int main()
{
    int i;
    if (printf("0"))
        i = 3;
    else
        i = 5;
    printf("%d", i);
    return 0;
} 
```

预测上述程序的输出？
**(A)**3
**(B)**5
**(C)**03
**(D)**05

**答案:****(C)**

**解释:**控制首先转到打印 **0** 的 if 语句。**printf(“0”)**返回正在打印的字符数，即 1。if 语句下的块被执行，I 用 3 初始化。