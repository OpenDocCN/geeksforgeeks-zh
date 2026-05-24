# C |输入输出|问题 13

> 原文:[https://www . geesforgeks . org/c-输入输出-问题-10/](https://www.geeksforgeeks.org/c-input-and-output-question-10/)

```cpp
#include<stdio.h>

int main()
{
    char *s = "Geeks Quiz";
    int n = 7;
    printf("%.*s", n, s);
    return 0;
}
```

**(A)** 极客竞猜
**(B)** 什么都没印
**(C)** 极客 Q
**(D)** 极客 Qu

**答案:****(C)**

**解说:**。*表示精度未在格式字符串中指定，而是作为必须格式化的参数之前的附加整数值参数。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/input-and-output-gq/)