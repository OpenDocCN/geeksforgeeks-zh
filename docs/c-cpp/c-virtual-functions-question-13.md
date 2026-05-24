# C++ |虚函数|第 13 题

> 原文:[https://www . geesforgeks . org/c-virtual-functions-question-13/](https://www.geeksforgeeks.org/c-virtual-functions-question-13/)

```cpp
#include <iostream>
using namespace std;

class A
{
public:
    virtual void fun() { cout << "A::fun() "; }
};

class B: public A
{
public:
   void fun() { cout << "B::fun() "; }
};

class C: public B
{
public:
   void fun() { cout << "C::fun() "; }
};

int main()
{
    B *bp = new C;
    bp->fun();
    return 0;
}
```

**(A)**A::fun()
**(B)**B::fun()
**(C)**C::fun()

**答案:****(C)**

**说明:**这里需要注意的重要一点是 B::fun()是虚的即使我们没有用虚关键字与之搭配。

当一个类有一个虚函数时，在所有子类中具有相同签名的函数会自动变成虚函数。在 B 和 c 中，我们不需要在有趣的声明中使用虚拟关键字()。不管怎样，它们都是虚拟的。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)