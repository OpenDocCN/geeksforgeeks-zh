# C++ |构造函数|问题 4

> 原文:[https://www.geeksforgeeks.org/c-constructors-question-4/](https://www.geeksforgeeks.org/c-constructors-question-4/)

```cpp
#include<iostream>
using namespace std;
class Point {
public:
    Point() { cout << "Constructor called"; }
};

int main()
{
   Point t1, *t2;
   return 0;
}
```

**(A)** 编译器错误
**(B)** 构造函数调用
构造函数调用

**(C)** 构造函数调用

**答案:****(C)**

**说明:**这里只构造了一个对象 T1。t2 只是指针变量，不是对象

[本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)