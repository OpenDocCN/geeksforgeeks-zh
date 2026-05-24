# C++ |异常处理|问题 11

> 原文:[https://www . geesforgeks . org/c-异常处理-问题-11/](https://www.geeksforgeeks.org/c-exception-handling-question-11/)

在 C++ 中，当异常被抛出而没有像下面的程序一样被捕获时会发生什么。

```cpp
#include <iostream>
using namespace std;

int fun() throw (int)
{
    throw 10;
}

int main() {

  fun();

  return 0;
}

```

**(A)** 编译器错误
**(B)** 程序异常终止
**(C)** 程序不打印任何内容，正常终止
**(D)** 以上

**均不存在答案:****(B)**

**解释:**当抛出异常而未被捕获时，程序异常终止。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)