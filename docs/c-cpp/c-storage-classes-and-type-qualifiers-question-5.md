# C |存储类和类型限定符|问题 19

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-5/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-5/)

```cpp
#include <stdio.h>
int main()
{
    int x = 5;
    int const * ptr = &x;
    ++(*ptr);
    printf("%d", x);

    return 0;
}
```

**(A)** 编译器错误
**(B)** 运行时错误
**(C)**6
**(D)**5

**答案:****(A)**

**解释:**看下面的声明就知道常量指针和指向常量的指针的区别了。
**int * const ptr**—>ptr 是常量指针。您可以更改指针 p 指向的位置的值，但不能将 p 更改为指向其他位置。
**int const * ptr**—>ptr 是指向一个常量的指针。您可以将 ptr 更改为指向其他变量。但是你不能改变 ptr 所指向的值。

在上面的程序中，ptr 是一个指向常数的指针。所以指向的值不能改变。

[本题竞猜](https://www.geeksforgeeks.org/c-language-2-gq/storage-classes-gq/)