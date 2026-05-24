# C++ |朋友关键词|问题 2

> 原文:[https://www.geeksforgeeks.org/c-friend-keyword-question-2/](https://www.geeksforgeeks.org/c-friend-keyword-question-2/)

预测以下程序的输出。

```cpp
#include <iostream>
using namespace std;

class B;
class A {
    int a;
public:
    A():a(0) { }
    void show(A& x, B& y);
};

class B {
private:
    int b;
public:
    B():b(0) { }
    friend void A::show(A& x, B& y);
};

void A::show(A& x, B& y) {
    x.a = 10;
    cout << "A::a=" << x.a << " B::b=" << y.b;
}

int main() {
    A a;
    B b;
    a.show(a,b);
    return 0;
}
```

**(A)** 编译器错误
**(B)**A::A = 10 B::B = 0
**(C)**A::A = 0 B::B = 0

**答案:****(B)**

**解释:**这是一个简单的程序，其中 A 类的一个函数被声明为 B 类的朋友。

由于 show()是好友，所以可以访问 B.

[成员的私人数据](https://www.geeksforgeeks.org/c-plus-plus-gq/friend-function-and-class-gq/)