# C++ |运算符重载|问题 3

> 原文:[https://www . geesforgeks . org/c-operator-overload-question-3/](https://www.geeksforgeeks.org/c-operator-overloading-question-3/)

即使用户没有编写，编译器在每个用户定义的类中默认重载以下哪些运算符？

```cpp
1) Comparison Operator ( == )
2) Assignment Operator ( = ) 
```

**(A)**1 和 2 都是
**(B)** 只有 1
**(C)** 只有 2
**(D)** 两者都不是

**答案:****(C)**
**说明:** Assign 运算符在所有用户定义的类中默认可用，即使用户尚未实现。默认分配进行浅层复制。

但是比较运算符“==”没有重载。

```cpp
#include<iostream>
using namespace std;

class Complex {
private:
    int real, imag;
public:
    Complex(int r = 0, int i =0)  {real = r;   imag = i;}
};

int main()
{
    Complex c1(10, 5), c2(2, 4);

    // For example, below code works fine
    c1 = c2;

    // But this code throws compiler error
    if (c1 == c2)
       cout << "Same";

    return 0;
}
```

[本题小考](https://www.geeksforgeeks.org/c-plus-plus-gq/operator-overloading-gq/)