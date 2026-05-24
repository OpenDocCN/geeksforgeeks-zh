# C |输入输出|问题 9

> 原文:[https://www . geesforgeks . org/c-输入输出-问题-9/](https://www.geeksforgeeks.org/c-input-and-output-question-9/)

下面的 C 语句是什么意思？

```cpp
scanf("%4s", str);
```

**(A)** 从控制台上准确读出 4 个字符。
**(B)** 从控制台读取最多 4 个字符。
**(C)** 以 4 的倍数读取字符串字符串
**(D)** 无

**答案:****(B)**

**解释:**尝试以下程序，输入 GeeksQuiz，输出会是“Geek”

```cpp
#include <stdio.h>

int main()
{
    char str[50] = {0};
    scanf("%4s", str);
    printf(str);
    getchar();
    return 0;
}

```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)