# C |高级指针|问题 3

> 原文:[https://www . geesforgeks . org/c-advanced-pointer-question-3/](https://www.geeksforgeeks.org/c-advanced-pointer-question-3/)

```cpp
#include <stdio.h>
int main()
{
    int a[5] = {1,2,3,4,5};
    int *ptr = (int*)(&a+1);
    printf("%d %d", *(a+1), *(ptr-1));
    return 0;
}
```

**(A)** 2 5
**(B)** 垃圾值
**(C)** 编译器错误
**(D)** 分段错误

**答案:****(A)**

**解释:**程序打印“2 5”。

由于编译器在访问数组元素之前将数组操作转换为指针，因此(a+1)指向 2。

表达式(&a + 1)实际上是刚好在数组末尾之后的地址(在地址 5 之后)，因为&a 包含大小为 5*integer_size 的项的地址，当我们这样做时(&a + 1)，指针将增加 5*integer_size。

ptr 被类型化为 int *所以当我们做 ptr -1 时，我们得到这个问题的 5

[测验的地址](https://www.geeksforgeeks.org/quiz-corner-gq/)