# C |结构&联盟|问题 1

> 原文:[https://www.geeksforgeeks.org/c-structure-union-question-1/](https://www.geeksforgeeks.org/c-structure-union-question-1/)

```cpp
#include‹stdio.h›
int main()
{
    struct site
    {
        char name[] = "GeeksQuiz";
        int no_of_pages = 200;
    };
    struct site *ptr;
    printf("%d ", ptr->no_of_pages);
    printf("%s", ptr->name);
    getchar();
    return 0;
}
```

**(A)**200 GeeksQuiz
**(B)**200
**(C)**运行时错误
**(D)** 编译器错误

**答案:****(D)**

**解释:**当我们声明一个结构或联合时，我们实际上声明了一个适合我们目的的新数据类型。因此，我们不能初始化值，因为它不是变量声明，而是数据类型声明。