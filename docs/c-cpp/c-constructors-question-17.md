# C++ |构造函数|第 17 题

> 原文:[https://www.geeksforgeeks.org/c-constructors-question-17/](https://www.geeksforgeeks.org/c-constructors-question-17/)

```cpp
#include<iostream>
using namespace std;

class Test
{
public:
   Test(Test &t) { }
   Test()        { }
};

Test fun()
{
    cout << "fun() Called\n";
    Test t;
    return t;
}

int main()
{
    Test t1;
    Test t2 = fun();
    return 0;
}
```

**(A)** fun()调用
**(B)** 空输出
**(C)** 编译器错误:因为复制构造函数参数是非常量

**答案:****(C)**

**解释:**详见如下:

[为什么 C++ 中复制构造函数参数应该是 const？](https://www.geeksforgeeks.org/copy-constructor-argument-const/)

[本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)