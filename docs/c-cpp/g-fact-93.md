# 在 C++ 中使用显式关键字

> 原文:[https://www.geeksforgeeks.org/g-fact-93/](https://www.geeksforgeeks.org/g-fact-93/)

预测后续 C++ 程序的输出。

```cpp
#include <iostream>

using namespace std;

class Complex
{
private:
    double real;
    double imag;

public:
    // Default constructor
    Complex(double r = 0.0, double i = 0.0) : real(r), imag(i) {}

    // A method to compare two Complex numbers
    bool operator == (Complex rhs) {
       return (real == rhs.real && imag == rhs.imag)? true : false;
    }
};

int main()
{
    // a Complex object
    Complex com1(3.0, 0.0);

    if (com1 == 3.0)
       cout << "Same";
    else
       cout << "Not Same";
     return 0;
}
```

输出:程序编译良好，并产生以下输出。

```cpp
Same 
```

正如在[这个 GFact](https://www.geeksforgeeks.org/advanced-c-conversion-operators/) 中讨论的，在 C++ 中，如果一个类有一个可以用单个参数调用的构造函数，那么这个构造函数就变成了转换构造函数，因为这样的构造函数允许将单个参数转换成正在构造的类。
*我们可以避免这种隐含的转换，因为这可能会导致意想不到的结果。我们可以借助[显式关键字](http://msdn.microsoft.com/en-us/library/h1y7x448%28v=vs.80%29.aspx)将构造函数显式化。*例如，如果我们尝试以下带有构造函数的使用显式关键字的程序，我们会得到编译错误。

```cpp
#include <iostream>

using namespace std;

class Complex
{
private:
    double real;
    double imag;

public:
    // Default constructor
    explicit Complex(double r = 0.0, double i = 0.0) : real(r), imag(i) {}

    // A method to compare two Complex numbers
    bool operator== (Complex rhs) {
       return (real == rhs.real && imag == rhs.imag)? true : false;
    }
};

int main()
{
    // a Complex object
    Complex com1(3.0, 0.0);

    if (com1 == 3.0)
       cout << "Same";
    else
       cout << "Not Same";
     return 0;
}
```

输出:编译器错误

```cpp
no match for 'operator==' in 'com1 == 3.0e+0'

```

我们仍然可以将双精度值类型转换为 Complex，但是现在我们必须显式类型转换它。例如，以下程序运行良好。

```cpp
#include <iostream>

using namespace std;

class Complex
{
private:
    double real;
    double imag;

public:
    // Default constructor
    explicit Complex(double r = 0.0, double i = 0.0) : real(r), imag(i) {}

    // A method to compare two Complex numbers
    bool operator== (Complex rhs) {
       return (real == rhs.real && imag == rhs.imag)? true : false;
    }
};

int main()
{
    // a Complex object
    Complex com1(3.0, 0.0);

    if (com1 == (Complex)3.0)
       cout << "Same";
    else
       cout << "Not Same";
     return 0;
}
```

输出:程序编译良好，并产生以下输出。

```cpp
Same 
```

另请参见[高级 C++ |转换运算符](https://www.geeksforgeeks.org/advanced-c-conversion-operators/)

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论