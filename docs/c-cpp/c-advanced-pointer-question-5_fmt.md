# C 高级指针问题 5

> 原文: [https://www.geeksforgeeks.org/c-advanced-pointer-question-5/](https://www.geeksforgeeks.org/c-advanced-pointer-question-5/)

预测输出

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

**(A)** `GeeksQuiz`
**(B)** `eeksquick`
**(C)** 垃圾值
**(D)** 编译器错误

**答案:** **(A)**

**解释:** 注意 `str_ref` 是 `fun()` 中的一个局部变量。当我们执行 `str_ref++` 时，它只改变了局部变量 `str_ref`。

我们可以使用解引用操作符 `*` 来更改字符串指针。例如，下面的程序打印 “GeeksQuiz”

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