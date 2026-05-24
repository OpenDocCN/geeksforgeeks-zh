# C++ 最终说明符

> 原文:[https://www.geeksforgeeks.org/c-final-specifier/](https://www.geeksforgeeks.org/c-final-specifier/)

在 Java 中，我们可以对一个函数使用 [final](http://geeksquiz.com/java/final-keyword/) 来确保它不能被覆盖。我们还可以在 Java 中使用 final 来确保类不能被继承。同样，最新的 C++ 标准 [C++ 11](http://en.wikipedia.org/wiki/C%2B%2B11) 增加了 final。
**在 C++ 11 中使用最终说明符:**
有时候你不想让派生类覆盖基类的虚函数。 [C++ 11](http://en.wikipedia.org/wiki/C%2B%2B11) 允许内置工具防止使用最终说明符重写虚函数。

考虑下面的例子，它显示了最终说明符的使用。这个程序编译失败。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

class Base
{
public:
    virtual void myfun() final
    {
        cout << "myfun() in Base";
    }
};
class Derived : public Base
{
    void myfun()
    {
        cout << "myfun() in Derived\n";
    }
};

int main()
{
    Derived d;
    Base &b = d;
    b.myfun();
    return 0;
}
```

**输出:**

```cpp
prog.cpp:14:10: error: virtual function ‘virtual void Derived::myfun()’
     void myfun()
          ^
prog.cpp:7:18: error: overriding final function ‘virtual void Base::myfun()’
     virtual void myfun() final 

```

**第二次使用最终说明符:**
c++ 11 中的最终说明符也可以用来防止类/结构的继承。如果一个类或结构被标记为 final，那么它就变得不可继承，并且不能用作基类/结构。

以下程序显示了如何使用最终说明符使类不可继承:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
class Base final
{
};

class Derived : public Base
{
};

int main()
{
    Derived d;
    return 0;
}
```

**输出:**

```cpp
error: cannot derive from ‘final’ base ‘Base’ in derived type ‘Derived’
 class Derived : public Base

```

**C++ 11 中的 final vs . Java 中的**
注意，C++ 11 中 final 说明符的使用与 Java 中相同，但是 Java 在类名前使用 final，而在 c++ 11 中 final 说明符在类名后使用。同样，Java 在方法定义的开头(在方法的返回类型之前)使用 final 关键字，但是 C++ 11 在函数名之后使用 final 说明符。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
class Test
{
    final void fun()// use of final in Java
    { }
}
class Test
{
public:
    virtual void fun() final //use of final in C++ 11
    {}
};
```

与 Java 不同，final 在 C++ 11 中不是关键字。final 只有在上述上下文中使用时才有意义，否则它只是一个标识符。
不做 final 关键字的一个可能原因是为了保证向后兼容。可能存在将 final 用于其他目的的生产代码。例如，下面的程序编译和运行没有错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

int main()
{
    int final = 20;
    cout << final;
    return 0;
}
```

**输出:**

```cpp
20

```

在 java 中，final 也可以与变量一起使用，以确保一个值只能赋值一次。C++ 11 中没有 final 的这种用法。
本文投稿**遇见普拉瓦西**。如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息