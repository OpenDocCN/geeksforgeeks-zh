# 理解 C++ 中的常量表达式说明符

> 原文:[https://www . geesforgeks . org/understanding-consexper-说明符-in-c/](https://www.geeksforgeeks.org/understanding-constexper-specifier-in-c/)

constexpr 是 C++ 11 中增加的一个特性。主要思想是通过在编译时而不是运行时进行计算来提高程序的性能。请注意，一旦一个程序被开发人员编译并最终确定，它就会被用户运行多次。其思想是在编译时花费时间，在运行时节省时间(类似于[模板元编程](https://www.geeksforgeeks.org/template-metaprogramming-in-c/))

constexpr 指定可以在编译时计算对象或函数的值，并且该表达式可以用在其他常量表达式中。例如，在下面的代码中，product()是在编译时计算的。

```cpp
// constexpr function for product of two numbers.
// By specifying constexpr, we suggest compiler to 
// to evaluate value at compile time
constexpr int product(int x, int y)
{
    return (x * y);
}

int main()
{
    const int x = product(10, 20);
    cout << x;
    return 0;
}
```

输出:

```cpp
200
```

函数被声明为常量表达式

1.  在 C++ 11 中，constexpr 函数应该只包含一条返回语句。C++ 14 允许多个语句。
2.  constexpr 函数应该只引用常量全局变量。
3.  constexpr 函数只能调用其他 constexpr 函数，不能调用简单函数。
4.  函数不应为 void 类型，并且在 constexpr 函数中不允许使用某些运算符，如前缀增量(++ v)。

**const expr vs inline functions:**
两者都是为了性能提升，inline functions 要求编译器在编译时进行扩展，节省函数调用的时间开销。在内联函数中，表达式总是在运行时计算。constexpr 不同，这里的表达式是在编译时计算的。

**const expr 提高性能的例子:**
考虑下面的 C++ 程序

```cpp
// A C++ program to demonstrate the use of constexpr
#include<iostream>
using namespace std;

constexpr long int fib(int n)
{
    return (n <= 1)? n : fib(n-1) + fib(n-2);
}

int main ()
{
    // value of res is computed at compile time. 
    const long int res = fib(30);
    cout << res;
    return 0;
}
```

当上述程序在 GCC 上运行时，需要 **0.003 秒**(我们可以使用[时间命令](https://www.geeksforgeeks.org/how-to-find-time-taken-by-a-program-on-linux-shell/)来测量时间)

如果我们从下面的行中移除 const，那么 fib(5)的值在编译时不会被计算，因为 constexpr 的结果不会在 const 表达式中使用。

```cpp
Change,
  const long int res = fib(30);  
To,
  long int res = fib(30);

```

进行上述更改后，程序花费的时间变高 **0.017 秒**。

**constexpr 带构造函数:**
constexpr 也可以用在构造函数和对象中。有关可以使用 constexpr 的构造函数的所有限制，请参见本中的[。](https://www.ibm.com/support/knowledgecenter/SSGH3R_13.1.0/com.ibm.xlcpp131.aix.doc/language_ref/constexpr_constructors.html)

```cpp
//  C++ program to demonstrate uses of constexpr in constructor
#include <bits/stdc++.h>
using namespace std;

//  A class with constexpr constructor and function
class Rectangle
{
    int _h, _w;
public:
    // A constexpr constructor
    constexpr Rectangle (int h, int w) : _h(h), _w(w) {}

    constexpr int getArea ()  {   return _h * _w; }
};

//  driver program to test function
int main()
{
    // Below object is initialized at compile time
    constexpr Rectangle obj(10, 20);
    cout << obj.getArea();
    return 0;
}
```

输出:

```cpp
200
```

**constexpr vs const**
它们服务于不同的目的。constexpr 主要用于优化，而 const 用于实际的 const 对象，如 Pi 的值。
两者都可以应用于成员方法。成员方法被设为 const，以确保该方法没有意外更改。另一方面，使用 constexpr 的想法是在编译时计算表达式，以便在代码运行时节省时间。
const 只能用于非静态成员函数，而 constexpr 可以用于成员函数和非成员函数，甚至可以用于构造函数，但条件是参数和返回类型必须是文字类型。

本文由乌卡什·特里维迪供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论