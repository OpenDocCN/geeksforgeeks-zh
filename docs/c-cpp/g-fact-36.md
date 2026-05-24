# 派生类中的虚函数

> 原文:[https://www.geeksforgeeks.org/g-fact-36/](https://www.geeksforgeeks.org/g-fact-36/)

在 C++ 中，一旦成员函数在基类中声明为虚函数，它在从该基类派生的每个类中就变成了虚函数。换句话说，在声明虚拟基类函数的重新定义版本时，不必在派生类中使用关键字 virtual。

例如，以下程序将名为“B::fun()的“C::fun()打印为”自动变为虚拟。

```cpp
#include<iostream>

using namespace std;

class A {
  public:
    virtual void fun()
    { cout<<"\n A::fun() called ";}
};

class B: public A {
  public: 
    void fun() 
    { cout<<"\n B::fun() called "; }      
};

class C: public B {
  public:
    void fun()
    { cout<<"\n C::fun() called "; }      
};

int main()
{
   C c; // An object of class C
   B *b = &c; // A pointer of type B* pointing to c
   b->fun();  // this line prints "C::fun() called"
   getchar();
   return 0;
}
```

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论