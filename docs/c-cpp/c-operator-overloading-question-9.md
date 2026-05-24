# C++ |运算符重载|问题 9

> 原文:[https://www . geesforgeks . org/c-operator-overload-question-9/](https://www.geeksforgeeks.org/c-operator-overloading-question-9/)

```cpp
#include<iostream>
using namespace std;

class Point {
private:
  int x, y;
public:
  Point() : x(0), y(0) { }
  Point& operator()(int dx, int dy);
  void show() {cout << "x = " << x << ", y = " << y; }
};

Point& Point::operator()(int dx, int dy)
{
    x = dx;
    y = dy;
    return *this;
}

int main()
{
  Point pt;
  pt(3, 2);
  pt.show();
  return 0;
}
```

**(A)** x = 3，y = 2
**(B)** 编译器错误
**(C)** x = 2，y = 3

**回答:****(A)**

**解释:**这是函数调用运算符重载的一个简单例子。

函数调用运算符在重载时不会修改函数的调用方式。相反，它修改了在应用于给定类型的对象时如何解释运算符。
如果为一个类重载一个函数调用运算符，它的声明将具有以下形式:

```cpp
    return_type operator()(parameter_list) 
```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)