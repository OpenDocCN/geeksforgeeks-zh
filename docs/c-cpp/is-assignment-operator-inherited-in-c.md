# 赋值运算符是遗传的吗？

> 原文:[https://www . geesforgeks . org/is-赋值-运算符-继承-in-c/](https://www.geeksforgeeks.org/is-assignment-operator-inherited-in-c/)

在 C++ 中，像其他函数一样，赋值运算符函数在派生类中被继承。

例如，在下面的程序中，可以使用派生类对象访问基类赋值运算符函数。

```cpp
#include<iostream>

using namespace std;

class A {
 public:
   A & operator= (A &a) { 
    cout<<" base class assignment operator called "; 
    return *this;
   }
};

class B: public A { };

int main()
{
  B a, b;
  a.A::operator=(b); //calling base class assignment operator function 
                    // using derived class
  getchar();
  return 0;
}
```

输出:*名为*的基类赋值运算符

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。