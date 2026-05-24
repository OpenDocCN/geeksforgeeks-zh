# C |数据类型|问题 6

> 原文:[https://www.geeksforgeeks.org/c-data-types-question-6/](https://www.geeksforgeeks.org/c-data-types-question-6/)

输出？

```cpp
int main()
{
    void *vptr, v;
    v = 0;
    vptr = &v;
    printf("%v", *vptr);
    getchar();
    return 0;
}
```

**(A)** 0
**(B)** 编译器错误
**(C)** 垃圾值

**回答:****(B)**

**说明:** void 不是声明变量的有效类型。但是 void *是有效的。

[本题小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)