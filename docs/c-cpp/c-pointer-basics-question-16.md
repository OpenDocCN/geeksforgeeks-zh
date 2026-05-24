# C |指针基础|第 16 题

> 原文:[https://www.geeksforgeeks.org/c-pointer-basics-question-16/](https://www.geeksforgeeks.org/c-pointer-basics-question-16/)

```cpp
#include <stdio.h>
int main()
{
    int arr[] = {1, 2, 3, 4, 5};
    int *p = arr;
    ++*p;
    p += 2;
    printf("%d", *p);
    return 0;
}
```

**(A)**2
**(B)**3
**(C)**4
**(D)**编译器错误

**答案:****(B)**

**解释:**表达式++*p 的求值方式为“++(*p)”。所以它增加数组第一个元素的值(不改变指针 p)。

当 p += 2 完成时，p 变为指向数组的第三个元素。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)