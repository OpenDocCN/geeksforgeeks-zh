# C++ |静态关键词|问题 5

> 原文:[https://www.geeksforgeeks.org/c-static-keyword-question-5/](https://www.geeksforgeeks.org/c-static-keyword-question-5/)

```cpp
#include<iostream>
using namespace std;

class Test
{
private:
    static int count;
public:
    Test& fun(); 
};

int Test::count = 0;

Test& Test::fun()
{
    Test::count++ ;
    cout << Test::count << " ";
    return *this;
}

int main()
{
    Test t;
    t.fun().fun().fun().fun();
    return 0;
}
```

**(A)** 编译器错误
**(B)**4 4 4 4
**(C)**1 1 1 1 1
**(D)**1 2 3 4

**回答:****(D)**

**说明:**静态成员在非静态函数中是可以访问的，所以访问 count in fun()没有问题。

另外，请注意 fun()通过引用返回相同的对象。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)