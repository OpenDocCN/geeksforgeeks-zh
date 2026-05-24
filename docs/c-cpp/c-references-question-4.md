# C++ |参考文献|问题 4

> 原文:[https://www.geeksforgeeks.org/c-references-question-4/](https://www.geeksforgeeks.org/c-references-question-4/)

预测后续 C++ 程序的输出。

```cpp
#include<iostream>
using namespace std;

int &fun()
{
    static int x = 10;
    return x;
}
int main()
{
    fun() = 30;
    cout << fun();
    return 0;
}
```

**(A)** 编译器错误:函数不能用作左值
**(B)**10
**(C)**30

**回答:****(C)**

**说明:**当函数通过引用返回时，可以用作左值。由于 x 是一个静态变量，它在函数调用和初始化行“static int x = 10 只执行一次。
函数调用 fun() = 30，将 x 修改为 30。下一次调用“cout < < fun()”返回修改后的值。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)