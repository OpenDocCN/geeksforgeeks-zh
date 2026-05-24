# C++ | const 关键字|问题 3

> 原文:[https://www.geeksforgeeks.org/c-const-keyword-question-3/](https://www.geeksforgeeks.org/c-const-keyword-question-3/)

预测后续程序的输出。

```cpp
#include <iostream>
using namespace std;
class Point
{
    int x, y;
public:
 Point(int i = 0, int j =0)
   { x = i; y = j;  }
   int getX() const { return x; }
   int getY() {return y;}
};

int main()
{
    const Point t;
    cout << t.getX() << " ";
    cout << t.getY();
    return 0;
}
```

**(A)** 垃圾值
**(B)** 0 0
**(C)** 第 cout < <行编译器错误 t . getx()<<”；
**(D)** 第 cout 行< < t.getY()编译器错误；

**回答:****(D)**

**说明:**第 cout 行< < t.getY()有编译器错误；

const 对象只能调用 const 函数。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)