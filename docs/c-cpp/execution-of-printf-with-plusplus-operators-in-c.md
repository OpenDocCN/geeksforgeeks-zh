# 用 c++ 运算符执行 printf

> 原文:[https://www . geesforgeks . org/execution-of-printf-with-plus plus-operator-in-c/](https://www.geeksforgeeks.org/execution-of-printf-with-plusplus-operators-in-c/)

考虑 C 语言中的以下语句，并预测其输出。

```cpp
printf("%d %d %d", i, ++ i, i++);
```

该语句通过引用参数列表中的“I”和“i++”来调用[未定义的行为](https://www.geeksforgeeks.org/undefined-behavior-c-cpp/)。没有定义参数的计算顺序。不同的编译器可能会选择不同的顺序。单个编译器也可以在不同的时间选择不同的顺序。

例如，下面三个 printf()语句也可能导致未定义的行为:

## C

```cpp
// C Program to demonstrate the three printf() statements
// that cause undefined behavior
#include <stdio.h>

// Driver Code
int main()
{
    volatile int a = 10;
    printf("%d %d\n", a, a++);

    a = 10;
    printf("%d %d\n", a++, a);

    a = 10;
    printf("%d %d %d\n", a, a++, ++ a);
    return 0;
}
```

**输出**

```cpp
11 10
10 10
12 11 11
```