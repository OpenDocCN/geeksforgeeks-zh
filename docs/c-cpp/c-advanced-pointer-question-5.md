# C |高级指针|问题 5

> 原文:[https://www . geesforgeks . org/c-advanced-pointer-question-5/](https://www.geeksforgeeks.org/c-advanced-pointer-question-5/)

预测产量

```cpp
#include <string.h>
#include <stdio.h>
#include <stdlib.h>

void fun(char** str_ref)
{
    str_ref++ ;
}

int main()
{
    char *str = (void *)malloc(100*sizeof(char));
    strcpy(str, "GeeksQuiz");
    fun(&str);
    puts(str);
    free(str);
    return 0;
}
```

**(A)**GeeksQuiz
**(B)**eeksquick
**(C)**垃圾值
**(D)** 编译器错误

**答案:****(A)**

**解释:**注意 str_ref 是一个局部变量来取乐()。当我们做 str_ref++ 时，它只改变局部变量 str_ref。

我们可以使用取消引用操作符*来更改字符串指针。例如，下面的程序打印“电子测验”

```cpp
#include <string.h>
#include <stdio.h>
#include <stdlib.h>

void fun(char** str_ref)
{
    (*str_ref)++ ;
}

int main()
{
    char *str = (void *)malloc(100*sizeof(char));
    strcpy(str, "GeeksQuiz");
    fun(&str);
    puts(str);
    free(str);
    return 0;
}

```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)