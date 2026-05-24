# c++ 中的运算符重载

> 原文:[https://www.geeksforgeeks.org/operator-overloading-c/](https://www.geeksforgeeks.org/operator-overloading-c/)

在 C++ 中，我们可以让操作符为用户定义的类工作。这意味着 C++ 能够为操作符提供一种特殊的数据类型含义，这种能力被称为操作符重载。
例如，我们可以在一个像 String 这样的类中重载一个运算符“+”，这样我们只需使用+就可以连接两个字符串。
算术运算符可能重载的其他示例类有复数、小数、大整数等。

**一个简单完整的例子**

```cpp
#include<iostream>
using namespace std;

class Complex {
private:
    int real, imag;
public:
    Complex(int r = 0, int i =0)  {real = r;   imag = i;}

    // This is automatically called when '+' is used with
    // between two Complex objects
    Complex operator + (Complex const &obj) {
         Complex res;
         res.real = real + obj.real;
         res.imag = imag + obj.imag;
         return res;
    }
    void print() { cout << real << " + i" << imag << endl; }
};

int main()
{
    Complex c1(10, 5), c2(2, 4);
    Complex c3 = c1 + c2; // An example call to "operator+"
    c3.print();
}
```

输出:

```cpp
12 + i9
```

**算子函数和正规函数有什么区别？**
操作员功能与正常功能相同。唯一的区别是，运算符函数的名称总是运算符关键字后跟运算符符号，并且在使用相应的运算符时调用运算符函数。
下面是全局算子函数的一个例子。

```cpp
#include<iostream>
using namespace std;

class Complex {
private:
    int real, imag;
public:
    Complex(int r = 0, int i =0)  {real = r;   imag = i;}
    void print() { cout << real << " + i" << imag << endl; }

// The global operator function is made friend of this class so
// that it can access private members
friend Complex operator + (Complex const &, Complex const &);
};

Complex operator + (Complex const &c1, Complex const &c2)
{
     return Complex(c1.real + c2.real, c1.imag + c2.imag);
}

int main()
{
    Complex c1(10, 5), c2(2, 4);
    Complex c3 = c1 + c2; // An example call to "operator+"
    c3.print();
    return 0;
}
```

**我们能让所有运营商超负荷吗？**
几乎所有的运营商都可能过载，只有少数例外。以下是不能重载的运算符列表。

```cpp
   . (dot) 
   :: 
   ?: 
   sizeof 
```

**为什么不能。(点)，::，？:大小会过载吗？**
参见[本](http://www.stroustrup.com/bs_faq2.html#overload-dot)获取斯特鲁德鲁普本人的答案。

**关于运算符重载的要点**
**1)** 要使运算符重载起作用，至少有一个操作数必须是用户定义的类对象。

**2)** **赋值运算符:**编译器自动为每个类创建一个默认赋值运算符。默认赋值操作符确实将右侧的所有成员都赋值给左侧，并且在大多数情况下都可以正常工作(这种行为与复制构造函数相同)。详见[本](https://www.geeksforgeeks.org/assignment-operator-overloading-in-c/)。

**3)** **转换运算符:**我们还可以编写转换运算符，用于将一种类型转换为另一种类型。

```cpp
#include <iostream>
using namespace std;
class Fraction
{
    int num, den;
public:
    Fraction(int n,  int d) { num = n; den = d; }

    // conversion operator: return float value of fraction
    operator float() const {
        return float(num) / float(den);
    }
};

int main() {
    Fraction f(2, 5);
    float val = f;
    cout << val;
    return 0;
}
```

输出:

```cpp
0.4
```

重载转换运算符必须是成员方法。其他运算符可以是成员方法或全局方法。

**4)** 任何可以用单个参数调用的构造函数都可以作为转换构造函数，这意味着它也可以用于隐式转换到正在构造的类。

```cpp
#include<iostream> 
using namespace std;

class Point
{
private:
    int x, y;
public:
    Point(int i = 0, int j = 0) {
        x = i;   y = j;
    }
    void print() {
        cout << endl << " x = " << x << ", y = " << y;
    }
};

int main() {
    Point t(20, 20);
    t.print();
    t = 30;   // Member x of t becomes 30
    t.print();
    return 0;
}
```

输出:

```cpp
 x = 20, y = 20
 x = 30, y = 0
```

我们将很快讨论一些重要运算符的重载，如 new、delete、逗号、函数调用、arrow 等。

[操作员超载测验](https://www.geeksforgeeks.org/c-plus-plus-gq/operator-overloading-gq/)

**参考文献:**
[http://en.wikipedia.org/wiki/Operator_overloading](http://en.wikipedia.org/wiki/Operator_overloading)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。