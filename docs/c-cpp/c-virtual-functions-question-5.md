# C++ |虚函数|问题 5

> 原文:[https://www . geesforgeks . org/c-virtual-functions-question-5/](https://www.geeksforgeeks.org/c-virtual-functions-question-5/)

```cpp
#include<iostream>
using namespace std;

class Base
{
public:
    virtual void show() = 0;
};

int main(void)
{
    Base b;
    Base *bp;
    return 0;
}
```

**(A)** 行“Base b”有编译器错误和“基础血压”
**(B)** 第“Base b”行有编译器错误
**(C)** 第“Base bp”行有编译器错误
**(D)** 无编译器错误

**答案:****(B)**

**解释:**由于 Base 有一个纯虚函数，所以它变成了一个抽象类，无法创建它的实例。

所以“Base b”行有一个错误。

请注意，行“Base *bp”中没有错误。我们可以有抽象类的指针或引用。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)