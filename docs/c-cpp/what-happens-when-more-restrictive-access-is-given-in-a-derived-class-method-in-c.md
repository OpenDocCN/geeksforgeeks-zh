# 当 C++ 中对派生类方法给予更严格的访问时会发生什么？

> 原文:[https://www . geeksforgeeks . org/当更严格的访问在 c 中的派生类方法中给出时会发生什么/](https://www.geeksforgeeks.org/what-happens-when-more-restrictive-access-is-given-in-a-derived-class-method-in-c/)

我们在 Java [这里](https://www.geeksforgeeks.org/more-restrictive-access-is-given-to-a-derived-class-method-in-java/)也讨论过类似的话题。与 Java 不同，C++ 允许对派生类方法进行更严格的访问。例如，以下程序编译良好。

## C++

```cpp
#include<iostream>
using namespace std;

class Base {
public:
    virtual int fun(int i) { }
};

class Derived: public Base {
private:
    int fun(int x)   {  }
};

int main()
{  }
```

在上面的程序中，如果我们把 main()改为 following，会得到编译器错误，因为 fun()在派生类中是私有的。

## C++

```cpp
int main()
{
    Derived d;
    d.fun(1);
    return 0;
}
```

下面的程序呢？

## C++

```cpp
#include<iostream>
using namespace std;

class Base {
public:
    virtual int fun(int i) { cout << "Base::fun(int i) called"; }
};

class Derived: public Base {
private:
    int fun(int x)   { cout << "Derived::fun(int x) called"; }
};

int main()
{
    Base *ptr = new Derived;
    ptr->fun(10);
    return 0;
}
```

**输出:**

```cpp
 Derived::fun(int x) called 
```

在上面的程序中，私有函数“派生类::fun(int)”是通过基类指针调用的，程序运行良好，因为 fun()在基类中是公共的。在编译时检查访问说明符，fun()在基类中是公共的。在运行时，只调用与指向的对象对应的函数，不检查访问说明符。所以派生类的私有函数通过基类的指针被调用。
发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息