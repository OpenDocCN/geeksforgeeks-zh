# C++ |构造函数|问题 8

> 原文:[https://www.geeksforgeeks.org/c-constructors-question-8/](https://www.geeksforgeeks.org/c-constructors-question-8/)

```cpp
#include <iostream>
using namespace std;

class Point
{
    int x, y;
public:
   Point(int i = 0, int j = 0) { x = i; y = j; }
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

**(A)** 编译器错误
**(B)**x = 0y = 0
**(C)**x =垃圾值 y =垃圾值

**答案:****(B)**

**解释:**如果我们自己不写，编译器会创建一个复制构造函数。即使我们已经在类中编写了其他构造函数，编译器也会编写它。所以上面的程序运行良好。因为我们有默认参数，所以分配给 x 和 y 的值是 0 和 0。

[本题小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)