# C |指针基础|第 14 题

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-16/](https://www.geeksforgeeks.org/c-pointers-question-16/)

预测以下程序的输出

```cpp
#include<stdio.h>
int main()
{
    int a = 12;
    void *ptr = (int *)&a;
    printf("%d", *ptr);
    getchar();
    return 0;
}
```

**(A)** 12
**(B)** 编译器错误
**(C)** 运行时间错误
**(D)**0

**答案:****(B)**

**解释:**第“printf("%d "，* ptr)；"。

void *类型指针不能被取消引用。我们必须在取消引用之前对它们进行类型转换。

以下程序运行良好，打印 12 张。

```cpp
#include<stdio.h>

int main()
{
    int a = 12;
    void *ptr = (int *)&a;
    printf("%d", *(int *)ptr);
    getchar();
    return 0;
}
```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)