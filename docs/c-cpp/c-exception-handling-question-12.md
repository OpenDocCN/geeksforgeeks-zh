# C++ |异常处理|问题 12

> 原文:[https://www . geesforgeks . org/c-异常处理-问题-12/](https://www.geeksforgeeks.org/c-exception-handling-question-12/)

当一个函数抛出一个错误，但没有在它可以抛出的异常列表中指定它时，会发生什么。

例如，以下程序的输出是什么？

```cpp
#include <iostream>
using namespace std;

// Ideally it should have been "int fun() (int)"
int fun()
{
    throw 10;
}

int main()
{
    try
    {
        fun();
    }
    catch (int )
    {
        cout << "Caught";
    }
    return 0;
}
```

**(A)** 编译错误
**(B)** 无编译错误。输出为“cated”

**答案:** **(B)**

**解释:** C++ 编译器不检查强制执行函数来列出它可以抛出的异常。在 Java 中，它是强制执行的。

由程序员来指定。作为一个文明的程序员，程序员应该指定清单。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)