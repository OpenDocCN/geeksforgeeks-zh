# c++ 程序输出|第 16 集

> 原文:[https://www.geeksforgeeks.org/output-of-c-program-set-16/](https://www.geeksforgeeks.org/output-of-c-program-set-16/)

预测以下 C++ 程序的输出。

**问题 1**

```cpp
#include<iostream>
using namespace std;

class Base 
{
public:
    int fun()      { cout << "Base::fun() called"; }
    int fun(int i) { cout << "Base::fun(int i) called"; }
};

class Derived: public Base 
{
public:
    int fun(char x)   { cout << "Derived::fun(char ) called"; }
};

int main() 
{
    Derived d;
    d.fun();
    return 0;
}
```

输出:编译器错误。
在上述程序中，基类的 fun()在派生类中是不可访问的。如果一个派生类创建了一个成员方法，其名称与基类中的一个方法相同，那么所有具有该名称的基类方法都会隐藏在派生类中(详见[本](https://www.geeksforgeeks.org/g-fact-89/)

**问题 2**

```cpp
#include<iostream>
using namespace std;
class Base 
{
   protected:
      int x;
   public:
      Base (int i){ x = i;}
};

class Derived : public Base 
{
   public:
      Derived (int i):x(i) { }
      void print() { cout << x ; }
};

int main()
{
    Derived d(10);
    d.print();
}
```

输出:编译器错误
在上面的程序中，x 是受保护的，所以在派生类中是可以访问的。派生类构造函数试图使用[初始化列表](https://www.geeksforgeeks.org/when-do-we-use-initializer-list-in-c/)直接初始化 x，即使 x 是可访问的，也不允许这样做。基类的成员只能通过基类的构造函数调用来初始化。以下是修正后的程序。

```cpp
#include<iostream>
using namespace std;
class Base {
   protected:
      int x;
   public:
      Base (int i){ x = i;}
};

class Derived : public Base {
   public:
      Derived (int i):Base(i) { }
      void print() { cout << x; }
};

int main()
{
    Derived d(10);
    d.print();
}
```

输出:

```cpp
 10 
```

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论