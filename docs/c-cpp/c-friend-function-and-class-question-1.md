# C++ |朋友关键词|问题 1

> 原文:[https://www . geesforgeks . org/c-friend-function-and-class-question-1/](https://www.geeksforgeeks.org/c-friend-function-and-class-question-1/)

预测后续程序的输出。

```cpp
#include <iostream>
using namespace std;
class A
{
protected:
    int x;
public:
    A() {x = 0;}
    friend void show();
};

class B: public A
{
public:
    B() : y (0) {}
private:
    int y;
};

void show()
{
    A a;
    B b;
    cout << "The default value of A::x = " << a.x << " ";
    cout << "The default value of B::y = " << b.y;
}
```

**(A)**show 中的编译器错误()因为 x 在 A 类中受到保护
**(B)**show 中的编译器错误()因为 y 在 B 类中是私有的
**(C)** 默认值 A::x = 0 B::y = 0
**(D)**编译器依赖

**答案:****(B)**

T20

B 类是从 A 继承而来的，这里需要注意的重要一点是友情是不能继承的。所以 show()没有成为 B 的朋友，因此无法访问 B 的私人成员。

[本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)