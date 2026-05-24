# C++ |构造函数|第 12 题

> 原文:[https://www.geeksforgeeks.org/c-constructors-question-12/](https://www.geeksforgeeks.org/c-constructors-question-12/)

预测后续程序的输出。

```cpp
#include<iostream>
using namespace std;
class Point {
    int x;
public:
    Point(int x) { this->x = x; }
    Point(const Point p) { x = p.x;}
    int getX() { return x; }
};

int main()
{
   Point p1(10);
   Point p2 = p1;
   cout << p2.getX();
   return 0;
}
```

**(A)** 10
**(B)** 编译器错误:p 必须通过引用传递
**(C)** 垃圾值
**(D)** 以上都不是

**答案:****(B)**

**解释:**对象必须在复制构造函数中通过引用传递。编译器会对此进行检查，如果不通过引用传递，则会产生编译器错误。

下面的程序编译良好，输出结果为 10。

```cpp
#include <iostream >
using namespace std;
class Point {
    int x;
public:
    Point(int x) { this->x = x; }
    Point(const Point &p) { x = p.x;}
    int getX() { return x; }
};

int main()
{
   Point p1(10);
   Point p2 = p1;
   cout << p2.getX();
   return 0;
}
```

原因很简单，如果我们不通过引用传递，那么参数 p1 会被复制到 p，所以会有一个复制构造函数调用来调用复制构造函数，这是不可能的。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)