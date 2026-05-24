# C++ |析构函数|问题 2

> 原文:[https://www.geeksforgeeks.org/c-destructors-question-2/](https://www.geeksforgeeks.org/c-destructors-question-2/)

预测后续 C++ 程序的输出

```cpp
#include <iostream>
using namespace std;

int i;

class A
{
public:
    ~A()
    {
        i=10;
    }
};

int foo()
{
    i=3;
    A ob;
    return i;
}

int main()
{
    cout << foo() << endl;
    return 0;
}
```

**(A)**0
**(B)**3
**(C)**10
**(D)**以上都不是

**回答:****(B)**

**说明:**从函数返回时，析构函数是最后要执行的方法。对象“ob”的析构函数在 I 的值被复制到函数的返回值后被调用。因此，在析构函数将 I 的值更改为 10 之前，I 的当前值被复制&，因此输出为 i = 3。详见[本](https://www.geeksforgeeks.org/playing-with-destructors-in-c/)。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)