# 隐藏基类中所有同名重载方法

> 原文:[https://www.geeksforgeeks.org/g-fact-89/](https://www.geeksforgeeks.org/g-fact-89/)

在 C++ 中，如果派生类重新定义基类成员方法，那么所有同名的基类方法都将隐藏在派生类中。
比如下面的程序不编译。在下面的程序中，派生类重新定义了 Base 的 fun()方法，这使得 fun(int i)隐藏起来。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>

using namespace std;

class Base {
public:
    int fun() {
      cout << "Base::fun() called";
    }
    int fun(int i)
    {
      cout << "Base::fun(int i) called";
    }
};

class Derived : public Base
{
public:
    int fun()
    {
          cout << "Derived::fun() called";
    }
};

// Driver Code
int main()
{
    Derived d;
    d.fun(5); // Compiler Error
    return 0;
}
```

即使派生类方法的签名不同，基类中的所有重载方法都会隐藏起来。例如，在下面的程序中，派生类::fun(char)使 Base::fun()和 Base::fun(int)都隐藏起来。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>

using namespace std;

class Base {
public:
    int fun()
    {
         cout << "Base::fun() called";
    }
    int fun(int i)
    {
         cout << "Base::fun(int i) called";
    }
};

class Derived : public Base {
public:
    // Makes Base::fun() and Base::fun(int )
    // hidden
    int fun(char c)
    {
        cout << "Derived::fun(char c) called";
    }
};

// Driver Code
int main()
{
    Derived d;
    d.fun('e'); // No Compiler Error
    return 0;
}
```

**Output**

```cpp
Derived::fun(char c) called
```

请注意，上述事实对于静态和非静态方法都是正确的。

有一种方法可以缓解这种问题。如果我们想重载一个基类的函数，可以使用' using '关键字取消隐藏它。

## C++

```
#include<iostream>

using namespace std;

class Base
{
public:
    int fun()
    {
        cout<<"Base::fun() called";
    }
};

class Derived: public Base
{
public:
    using Base::fun;

    int fun(char c)  // Makes Base::fun() and Base::fun(int ) unhidden
    {
        cout<<"Derived::fun(char c) called";
    }
};

int main()
{
    Derived d;
    d.fun();  // Works fine now 🙂
    return 0;
}
```cpp

**Output**

```
Base::fun() called
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。