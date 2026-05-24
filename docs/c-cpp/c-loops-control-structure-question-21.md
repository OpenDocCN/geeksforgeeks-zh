# C |循环&控制结构|问题 21

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-21/](https://www.geeksforgeeks.org/c-loops-control-structure-question-21/)

```cpp
#include<stdio.h>
int main()
{
    int a = 5;
    switch(a)
    {
    default:
        a = 4;
    case 6:
        a--;
    case 5:
        a = a+1;
    case 1:
        a = a-1;
    }
    printf("%d \n", a);
    return 0;
}
```

**(A)**3
**(B)**4
**(C)**5
**(D)**这些

**都没有答案:****(C)**

**说明:**没有 break 语句，所以先执行 a = a + 1，再执行 a = a-1。

本题小考