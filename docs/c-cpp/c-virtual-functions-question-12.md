# C++ |虚函数|第 12 题

> 原文:[https://www . geesforgeks . org/c-virtual-functions-question-12/](https://www.geeksforgeeks.org/c-virtual-functions-question-12/)

预测后续 C++ 程序的输出。假设没有对齐，虚拟函数的典型实现由编译器完成。

```cpp
#include <iostream>
using namespace std;

class A
{
public:
    virtual void fun();
};

class B
{
public:
   void fun();
};

int main()
{
    int a = sizeof(A), b = sizeof(B);
    if (a == b) cout << "a == b";
    else if (a > b) cout << "a > b";
    else cout << "a < b";
    return 0;
}
```

**(A)**A>B
**(B)**A = = B
**(C)**A<B
T9】(D)编译器错误

**答案:****(A)**

**解释:**A 类有一个 B 类没有的 VPTR。

在虚拟函数的典型实现中，编译器在每个对象中放置一个 VPTR。编译器会在每个构造函数中偷偷添加一些代码。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)