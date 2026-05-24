# C++ |运算符重载|问题 10

> 原文:[https://www . geesforgeks . org/c-operator-overload-question-1/](https://www.geeksforgeeks.org/c-operator-overloading-question-1/)

如何使用 new 限制类对象的动态分配？
**(A)** 通过重载新操作符
**(B)** 通过做一个空的私有新操作符。
**(C)** 通过使一个空的私有新的和新的[]运算符
**(D)** 通过重载新的运算符和新的[]运算符

**答案:****(C)**

**解释:**如果我们声明*新的*和*【新的】*运算符，那么就不能在任何地方(类内和类外)创建对象我们不能使用新的来分配测试类型的对象。

```cpp
#include <stdlib.h>
#include <stdio.h>
#include <iostream>

using namespace std;

class Test {
private:
    void* operator new(size_t size) {}
    void* operator new[](size_t size) {}
};

int main()
{
    Test *obj = new Test;
    Test *arr = new Test[10];
    return 0;
}

```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)