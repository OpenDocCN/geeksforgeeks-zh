# C |循环&控制结构|问题 1

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-1/](https://www.geeksforgeeks.org/c-loops-control-structure-question-1/)

```cpp
#include <stdio.h>

int main()
{
    int i = 1024;
    for (; i; i >>= 1)
        printf("GeeksQuiz");
    return 0;
}
```

GeeksQuiz 在上面的程序中会被打印多少次？ ```cpp**(A)**10
**(B)**11
**(C)**无限
**(D)** 程序会显示编译时错误

**答案:****(B)**

**解释:**在 for 循环中，提提表达式是可选的。 **> > =** 是复合运算符。它将值的二进制表示向右移动 1，并将结果值赋给同一个变量。执行 for 循环，直到变量 **i** 的值没有降至 0。```