# C++ |构造函数|问题 5

> 原文:[https://www.geeksforgeeks.org/c-constructors-question-5/](https://www.geeksforgeeks.org/c-constructors-question-5/)

以下程序的输出？

```cpp
#include<iostream>
using namespace std;

class Point {
public:
    Point() { cout << "Normal Constructor called\n"; }
    Point(const Point &t) { cout << "Copy constructor called\n"; }
};

int main()
{
   Point *t1, *t2;
   t1 = new Point();
   t2 = new Point(*t1);
   Point t3 = *t1;
   Point t4;
   t4 = t3;
   return 0;
}
```

**(A)** 普通构造函数调用
普通构造函数调用

普通构造函数调用

复制构造函数调用

复制构造函数调用

普通构造函数调用

复制构造函数调用

正常构造函数调用
复制构造函数调用

复制构造函数调用

正常构造函数调用

**答案:****(C)**

**解释:**解释见以下注释:

```cpp
Point *t1, *t2;   // No constructor call
t1 = new Point(10, 15);  // Normal constructor call
t2 = new Point(*t1);   // Copy constructor call 
Point t3 = *t1;  // Copy Constructor call
Point t4;   // Normal Constructor call
t4 = t3;   // Assignment operator call 
```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)