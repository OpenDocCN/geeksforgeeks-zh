# c++ 11 中明确默认和删除的函数

> 原文:[https://www . geesforgeks . org/显式-默认-已删除-函数-c-11/](https://www.geeksforgeeks.org/explicitly-defaulted-deleted-functions-c-11/)

**Defaulted Function**

**什么是默认函数？**
显式默认函数声明是 C++ 11 标准中引入的一种新的函数声明形式，允许您附加**“= default；”**函数声明末尾的说明符，用于将该函数声明为显式默认函数。这使得编译器为显式默认的函数生成默认实现，这比手动编程的函数实现更有效。
例如，每当我们声明参数化构造函数时，编译器不会创建默认构造函数。在这种情况下，我们可以使用默认说明符来创建默认说明符。以下代码演示了如何:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the
// use of defaulted functions
#include <iostream>
using namespace std;

class A {
public:

    // A user-defined
    // parameterized constructor
    A(int x)
    {
        cout << "This is a parameterized constructor";
    }

    // Using the default specifier to instruct
    // the compiler to create the default
    // implementation of the constructor.
    A() = default;
};

int main()
{
    // executes using defaulted constructor
    A a;

    // uses parameterized constructor
    A x(1);
    return 0;
}
```

**输出** :

```cpp
This is a parameterized constructor
```

在上面的例子中，我们不必指定构造函数的主体 **A()** ，因为通过附加说明符“=default”，编译器将创建这个函数的默认实现。
**功能默认有哪些约束？**
默认函数需要是特殊成员函数(默认构造函数、复制构造函数、析构函数等)，或者没有默认参数。例如下面的代码解释了非特殊成员函数**不能**默认:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate that
// non-special member functions
// can't be defaulted
class B {
public:

    // Error, func is not a special member function.
    int func() = default;

    // Error, constructor B(int, int) is not
    // a special member function.
    B(int, int) = default;

    // Error, constructor B(int=0)
    // has a default argument.
    B(int = 0) = default;
};

// driver program
int main()
{
    return 0;
}
```

**当我们可以简单地使用“{ 0 }”留下函数的空体时，' =default '有什么好处？**
即使两者的行为可能相同，使用默认值仍然比留下构造函数的空体有好处。以下几点说明如何:

1.  给定一个用户定义的构造函数，即使它什么也不做，也会使类型不是一个集合，也不是微不足道的。如果你希望你的类是一个集合或者一个简单的类型(或者通过传递，一个 POD 类型)，那么你需要使用' = default '。
2.  使用“= default”也可以与复制构造函数和析构函数一起使用。例如，空复制构造函数与默认的复制构造函数不同(默认的复制构造函数对其成员执行按成员复制)。为这些特殊的成员函数统一使用' = default '语法使得代码更容易阅读。

**Deleted Function**

在 C++ 11 之前，操作符 [**【删除】**](https://www.geeksforgeeks.org/g-fact-30/) 只有一个目的，就是释放一个已经动态分配的内存。
c++ 11 标准引入了该运算符的另一种用法，即:**禁用成员函数的使用。**这是通过追加**=删除来完成的；**该函数声明末尾的说明符。
任何使用“=delete”说明符禁用的成员函数都称为显式**删除函数。**
虽然不限于它们，但这通常是对隐函数做的。以下示例展示了该功能可以派上用场的一些任务:
**禁用复制构造函数**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to disable the usage of
// copy-constructor using delete operator
#include <iostream>
using namespace std;

class A {
public:
    A(int x): m(x)
    {
    }

    // Delete the copy constructor
    A(const A&) = delete;

    // Delete the copy assignment operator
    A& operator=(const A&) = delete;
    int m;
};

int main()
{
    A a1(1), a2(2), a3(3);

    // Error, the usage of the copy
    // assignment operator is disabled
    a1 = a2;

    // Error, the usage of the
    // copy constructor is disabled
    a3 = A(a2);
    return 0;
}
```

**禁用不良参数转换**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to disable undesirable argument
// type conversion using delete operator
#include <iostream>
using namespace std;

class A {
public:
    A(int) {}

    // Declare the conversion constructor as a
    // deleted function. Without this step,
    // even though A(double) isn't defined,
    // the A(int) would accept any double value
    // for it's argumentand convert it to an int
    A(double) = delete;
};

int main()
{
    A A1(1);

    // Error, conversion from
    // double to class A is disabled.
    A A2(100.1);
    return 0;
}
```

请注意，删除的函数是隐式内联的，这一点非常重要。删除的函数定义必须是函数的第一个声明。换句话说，以下方式是将函数声明为已删除的正确方式:

```cpp
class C 
{
public:
         C(C& a) = delete;
};
```

但是以下试图声明函数被删除的方式会产生错误:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Sample C++ code to demonstrate the
// incorrect syntax of declaring a member
// function as deleted
class C
{
public:
    C();
};

// Error, the deleted definition 
// of function C must be the first
// declaration of the function.
C::C() = delete;
```

**显式删除函数有什么好处？**

1.  删除特殊成员函数提供了一种更干净的方法来防止编译器生成我们不想要的特殊成员函数。(如“禁用复制构造函数”示例所示)。
2.  删除普通成员函数或非成员函数可防止有问题的类型提升导致调用非预期的函数(如“禁用不需要的参数转换”示例所示)。