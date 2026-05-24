# C++ |构造函数|问题 6

> 原文:[https://www.geeksforgeeks.org/c-constructors-question-6/](https://www.geeksforgeeks.org/c-constructors-question-6/)

```cpp
#include<iostream>
using namespace std;

class X 
{
public:
    int x;
};

int main()
{
    X a = {10};
    X b = a;
    cout << a.x << " " << b.x;
    return 0;
}
```

**(A)** 编译器错误
**(B)** 10 后跟垃圾值
**(C)**10 10
**(D)**10 0

**回答:****(C)**

**解释:**以下可能看起来像是错误，但它工作正常。

x a = { 10 }；

像结构一样，类对象可以被初始化。

线“X b = a；”调用复制构造函数，与“X b(a)；”相同。请注意，如果我们不编写自己的复制构造函数，编译器会创建一个默认的复制构造函数，将一个对象的数据成员分配给另一个对象。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)