# C |循环&控制结构|问题 11

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-11/](https://www.geeksforgeeks.org/c-loops-control-structure-question-11/)

以下 C 程序的输出？

```cpp
#include<stdio.h>
int main()
{
    int i = 0;
    for (printf("1st\n"); i < 2 && printf("2nd\n"); ++ i && printf("3rd\n"))
    {
        printf("*\n");
    }
    return 0;
}
```

**(A)** 第一
第二
*
第三
第二
*

**(B)** 第一
第二
*
第三
第二
*
第三

**(C)** 第一
第二
第三
*
第二
第三

**(D)** 第一
第二
第三
*
第一
第二
第三

**回答:** **(B)**

**说明:**只是在 for 循环中一个个执行语句。
a)初始语句只执行一次。
b)在打印“*”之前打印第二个条件。第二条语句也有短路逻辑& &运算符，仅当“I”小于 2 时才打印第二部分
b)第三条语句在打印“*”后打印。这也有短路逻辑& &运算符，仅当“++ i”不为零时才打印第二部分。