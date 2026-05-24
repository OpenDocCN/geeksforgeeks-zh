# C++ |函数重载和默认参数|问题 4

> 原文:[https://www . geesforgeks . org/c-function-overload-and-default-arguments-question-4/](https://www.geeksforgeeks.org/c-function-overloading-and-default-arguments-question-4/)

预测后续 C++ 程序的输出。

```cpp
include<iostream>
using namespace std;

class Test
{
protected:
    int x;
public:
    Test (int i):x(i) { }
    void fun() const  { cout << "fun() const " << endl; }
    void fun()        {  cout << "fun() " << endl;     }
};

int main()
{
    Test t1 (10);
    const Test t2 (20);
    t1.fun();
    t2.fun();
    return 0;
}
```

**(A)** 编译器错误
**(B)**fun()
fun()const

**(C)**fun()const
fun()const

**(D)**fun()
fun()

**答案:****(B)**

**解释:**此外，如果我们仔细查看输出，我们会发现在 const 对象上调用了“const void fun()”，在非常规对象上调用了“void fun()”。
C++ 允许基于 const 类型重载成员方法。当函数返回引用或指针时，基于常量类型的重载会很有用。我们可以使一个函数常量，返回常量引用或常量指针，另一个非常量函数，返回非常量引用或指针。详情见下文。****

[函数重载和 const 关键字](https://www.geeksforgeeks.org/function-overloading-and-const-functions/)

[本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)