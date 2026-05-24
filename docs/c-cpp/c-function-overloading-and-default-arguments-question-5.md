# C++ |函数重载和默认参数|问题 5

> 原文:[https://www . geesforgeks . org/c-function-overload-and-default-arguments-question-5/](https://www.geeksforgeeks.org/c-function-overloading-and-default-arguments-question-5/)

以下程序的输出？

```cpp
#include <iostream>
using namespace std;

int fun(int=0, int = 0);

int main()
{
  cout << fun(5);
  return 0;
}

int fun(int x, int y) { return (x+y); }
```

**(A)** 编译器错误
**(B)**5
**(C)**0
**(D)**10

**答案:****(B)**

**解释:**语句“int fun(int=0，int=0)”是一个函数的声明，该函数采用默认值为 0 和 0 的两个参数。

最后一个说法是乐趣的定义()。

当我们打一个有趣的电话(5)时，x 得到值 5，y 得到 0。所以返回值是 5。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)