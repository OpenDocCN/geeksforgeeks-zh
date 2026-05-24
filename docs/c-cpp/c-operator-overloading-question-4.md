# C++ |运算符重载|问题 4

> 原文:[https://www . geesforgeks . org/c-operator-overload-question-4/](https://www.geeksforgeeks.org/c-operator-overloading-question-4/)

下列哪个运算符更适合作为全局函数而不是成员方法重载？
**(A)** 后缀++
**(B)** 比较运算符
**(C)** 插入运算符< <
**(D)** 前缀++

**答案:****(C)**

**解释:** cout 是 ostream 类的对象，是编译器定义的类。

当我们执行“cout << obj" where obj is an object of our class, the compiler first looks for an operator function in ostream, then it looks for a global function.
时，重载插入运算符的一种方法是修改 ostream 类，这可能不是一个好主意。所以我们做了一个全局方法。下面是一个例子。

```cpp
#include <iostream>
using namespace std;

class Complex
{
private:
    int real;
    int imag;
public:
    Complex(int r = 0, int i =0)
    {
        real = r;
        imag = i;
    }
    friend ostream & operator << (ostream &out, const Complex &c);
};

ostream & operator << (ostream &out, const Complex &c)
{
    out << c.real;
    out << "+i" << c.imag;
    return out;
}

int main()
{
    Complex c1(10, 15);
    cout << c1;
    return 0;
}

```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)