# 为什么同时覆盖全局新运算符和类特定运算符不含糊？

> 原文:[https://www . geeksforgeeks . org/why-override-both-the-global-new-operator-和-class-specific-operator-不含糊/](https://www.geeksforgeeks.org/why-overriding-both-the-global-new-operator-and-the-class-specific-operator-is-not-ambiguous/)

下一节讨论重载解析，因为它有助于重载和重写的基础。
**预测产量:**

```cpp
#include <iostream>
using namespace std;

class Gfg {
public:
    void printHello()
    {
        cout << "hello gfg-class specific" << endl;
    }
};

void printHello()
{
    cout << "hello gfg-global" << endl;
}
int main()
{
    Gfg a;
    a.printHello();
    printHello();
}
```

```cpp
Output:
hello gfg-class specific
hello gfg-global

```

**编译器如何区分类特定函数和全局函数？**
为了将函数调用映射到相应的函数定义，编译器执行名称查找的过程。这个过程产生一些同名的函数集，它们被称为候选函数。如果有多个候选函数，编译器将执行依赖于参数的查找过程。如果这个过程也产生一个以上的候选函数，那么执行重载解析的过程来选择必须被调用的函数。
如果任何候选函数是相应类(静态或非静态)的成员函数，它将被添加一个隐式对象参数，该参数表示为其调用的对象，并出现在第一个实际参数之前。

**预测输出:**

```cpp
#include <iostream>
using namespace std;

class Gfg {
public:
    Gfg operator+(Gfg& a)
    {
        cout << "class specific + operator" << endl;
        return Gfg(); // Just return some temporary object
    }
};

Gfg operator+(Gfg& a, Gfg& b)
{
    cout << "global + operator called" << endl;
    return Gfg(); // Just return some temporary object
}

int main()
{
    Gfg a, b;
    Gfg c = a + b;
}
```

```cpp
Output: Compilation error
plusOverride.cpp: In function ‘int main()’:
plusOverride.cpp:19:9: error: ambiguous overload for ‘operator+’ 
(operand types are ‘Gfg’ and ‘Gfg’)
  Gfg c=a+b;
         ^
plusOverride.cpp:19:9: note: candidates are:
plusOverride.cpp:6:9: note: Gfg Gfg::operator+(Gfg&)
     Gfg operator+(Gfg& a){
         ^
plusOverride.cpp:12:5: note: Gfg operator+(Gfg&, Gfg&)
 Gfg operator+(Gfg& a, Gfg& b){
     ^

```

**这是重载解析如何处理运算符重载:**
一元和二元运算符的候选函数是从不同的范围中选择的。它们是
1)成员候选:类中定义的运算符重载函数。
2)非成员候选:运算符重载了全局函数。
3)内置候选:执行指定操作的内置功能。
因此，对于编译期间的上述程序，候选函数的数量多于一个并且**所有这些候选函数具有相同的优先级**，因此出现模糊的重载错误。
**预测输出:**

```cpp
#include <iostream>
#include <stdio.h>
#include <stdlib.h>
using namespace std;

class Gfg {
public:
    int a;
    void* operator new(size_t sz)
    {
        cout << "class-specific new for size " << sz << '\n';
        return malloc(sz);
    }

    void* operator new[](size_t sz)
    {
        cout << "class-specific new[] for size " << sz << '\n';
        return malloc(sz);
    }
};

void* operator new[](size_t sz)
{
    cout << "global new[] for size" << sz << '\n';
    return malloc(sz);
}

void* operator new(size_t sz)
{
    cout << "global new for size" << sz << '\n';
    return malloc(sz);
}

int main()
{
    Gfg* p1 = new Gfg;
    delete p1;
    Gfg* p2 = new Gfg[10];
    delete[] p2;
}
```

```cpp
Output: 
class-specific new for size 4
class specific new[] for size 40

```

**程序工作的原因如下:**
c++ 标准规定“如果一个类有一个类特定的分配函数，那么将被调用的是函数，而不是全局分配函数。这是有意为之的:希望该类成员最了解如何处理该类”。这意味着，当新表达式寻找相应的分配函数时，它在检查全局范围之前从类范围开始，如果提供了类特定的 new，则调用它。否则它检查全局范围并调用它。如果全局作用域新函数不存在，它将调用内置的新函数。此后，**候选函数在上述示例中不具有相同的优先级**，因此它编译时没有任何错误。

**即使定义了类特有的新运算符，程序员还能调用全局新运算符吗？**
是的。C++ 为此提供了范围解析运算符。如果新运算符前面有作用域解析(::)运算符，编译器将在全局作用域中搜索新运算符。

**如果新运算符未在全局范围内定义，并且您正在使用::一元运算符调用新运算符，会发生什么情况？**
编译器会调用内置的新函数。下面的例子演示了它是如何工作的。它确实包含特定于类的运算符 new，但包含全局运算符 new。此后，在调用::new 时，编译器调用标准库 new 函数。

```cpp
#include <iostream>
#include <stdio.h>
#include <stdlib.h>
using namespace std;

class Gfg {
public:
    int a;
    void* operator new(size_t sz)
    {
        cout << "class-specific new for size " << sz << '\n';
        return malloc(sz);
    }

    void* operator new[](size_t sz)
    {
        cout << "class-specific new[] for size " << sz << '\n';
        return malloc(sz);
    }
};

void* operator new[](size_t sz)
{
    cout << "global new[] for size " << sz << '\n';
    return malloc(sz);
}

int main()
{
    Gfg* p1 = ::new Gfg;
    cout << "Allocated sie of p1: " << sizeof(*p1) << endl;
    delete p1;
    Gfg* p2 = ::new Gfg[10];
    delete[] p2;
}
```

```cpp
Output:
Allocated sie of p1: 4
global new[] for size 40

```

**为什么 C++ 为新函数提供了这种可扩展性？**

1.  **性能:**内置内存分配器函数是一个通用函数，适合预定义的数据类型。对于需要分配非常具体数据的用户定义数据类型，通过定制它们的分配方式，您可以大大加快内存管理。
2.  **调试&统计:**拥有对内存使用方式的控制，为调试、统计和性能分析提供了极大的灵活性。

这些是在解决复杂问题时使编程更容易的各种原因中的一些。