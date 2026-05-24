# c++ 中的转换运算符

> 原文:[https://www.geeksforgeeks.org/conversion-operators-in-cpp/](https://www.geeksforgeeks.org/conversion-operators-in-cpp/)

在 C++ 中，程序员使用类作为具体类型来抽象现实世界的对象。有时，需要隐式地将一个具体类型转换为另一个具体类型或基本类型。转换运算符在这种情况下起着重要作用。它类似于类中的运算符重载函数。

例如，考虑下面的类，这里，我们正在为复数创建一个类。它有两个数据成员:实数和虚数。

## c++

```cpp
// CPP Program to demonstarte Conversion Operators
#include <cmath>
#include <iostream>
using namespace std;

class Complex {
private:
    double real;
    double imag;

public:
    // Default constructor
    Complex(double r = 0.0, double i = 0.0)
        : real(r)
        , imag(i)
    {
    }

    // magnitude : usual function style
    double mag() { return getMag(); }

    // magnitude : conversion operator
    operator double() { return getMag(); }

private:
    // class helper to get magnitude
    double getMag()
    {
        return sqrt(real * real + imag * imag);
    }
};

int main()
{
    // a Complex object
    Complex com(3.0, 4.0);

    // print magnitude
    cout << com.mag() << endl;
    // same can be done like this
    cout << com << endl;
}
```

**输出**

```cpp
5
5
```

我们以两种不同的方式打印复杂物体的大小。

**注意**编译器在基于类型调用合适的函数时会有更多的控制权，而不是程序员所期望的。使用其他技术，如类/对象特定的成员函数(或利用 C++ Variant 类)来执行这样的转换，将是一个很好的实践。在某些地方，例如在与现有的 C 库进行兼容调用时，这些是不可避免的。