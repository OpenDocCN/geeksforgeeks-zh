# C++ |静态关键词|问题 1

> 原文:[https://www.geeksforgeeks.org/c-static-keyword-question-1/](https://www.geeksforgeeks.org/c-static-keyword-question-1/)

预测后续 C++ 程序的输出。

```cpp
#include <iostream>
using namespace std;

class Test
{
    static int x;
public:
    Test() { x++ ; }
    static int getX() {return x;}
};

int Test::x = 0;

int main()
{
    cout << Test::getX() << " ";
    Test t[5];
    cout << Test::getX();
}
```

**(A)**0 0
**(B)**5 5
**(C)**0 5
**(D)**编译器错误

**答案:****(C)**

**解释:**静态函数可以在没有任何对象的情况下调用。所以调用“Test::getX()”就可以了。

由于 x 被初始化为 0，所以对 getX()的第一次调用返回 0。注意构造函数中的 x++ 语句。当创建 5 个对象的数组时，构造函数被调用 5 次。所以在下一次调用 getX()之前，x 会增加到 5。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)