# C |字符串|问题 15

> 原文:[https://www.geeksforgeeks.org/c-string-question-15/](https://www.geeksforgeeks.org/c-string-question-15/)

预测下面程序的输出，假设一个字符取 1 字节，指针取 4 字节。

```cpp
#include <stdio.h>
int main()
{
    char *str1 = "GeeksQuiz";
    char str2[] = "GeeksQuiz";

    printf("sizeof(str1) = %d, sizeof(str2) = %d",
           sizeof(str1), sizeof(str2));

    return 0;
}
```

**(A)** sizeof(str1) = 10，sizeof(str2) = 10

**(B)** sizeof(str1) = 4，sizeof(str 2)= 10
**(C)**sizeof(str 1)= 4，sizeof(str 2)= 4
**(D)**sizeof(str 1)= 10，sizeof(str 2)= 4

**回答:****(B)**

**说明:

[本题小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)**