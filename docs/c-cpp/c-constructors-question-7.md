# C++ |构造函数|问题 7

> 原文:[https://www.geeksforgeeks.org/c-constructors-question-7/](https://www.geeksforgeeks.org/c-constructors-question-7/)

以下程序的输出是什么？

```cpp
#include <iostream>
using namespace std;

class Point
{
    int x, y;
public:
   Point(const Point &p) { x = p.x; y = p.y; }
   int getX() { return x; }
   int getY() { return y; }
};

int main()
{
    Point p1;
    Point p2 = p1;
    cout << "x = " << p2.getX() << " y = " << p2.getY();
    return 0;
}
```

**(A)** x =垃圾值 y =垃圾值
**(B)**x = 0y = 0
**(C)**编译器错误

**回答:****(C)**

**说明:**第“点 p1”行有编译器错误。点类没有不带任何参数的构造函数。如果我们编写任何构造函数，那么编译器不会创建[默认构造函数](http://en.wikipedia.org/wiki/Default_constructor)。

换句话说，它不是真的，也就是说，如果我们编写一个默认的或参数化的构造函数，那么编译器会创建一个复制构造函数。见下一个问题。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)