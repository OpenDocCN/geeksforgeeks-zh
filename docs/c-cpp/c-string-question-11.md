# C |字符串|问题 11

> 原文:[https://www.geeksforgeeks.org/c-string-question-11/](https://www.geeksforgeeks.org/c-string-question-11/)

预测以下程序的输出:

```cpp
#include <stdio.h>
int main()
{
    char str[] = "%d %c", arr[] = "GeeksQuiz";
    printf(str, 0[arr], 2[arr + 3]);
    return 0;
}
```

**(A)**G Q
**(B)**71 81
**(C)**71 Q
**(D)**编译时错误

**答案:****(C)**

**解释:**

```cpp
The statement *printf(str, 0[arr], 2[arr + 3]);* boils down to:
*printf("%d %c, 0["GeeksQUiz"], 2["GeeksQUiz" + 3]);*
Which is further interpreted as:
*printf("%d %c, *(0 + "GeeksQUiz"), *(2 + "GeeksQUiz" + 3));*
Which prints the ascii value of *'G'* and character *'Q'*.

```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)