# C++ |继承|问题 1

> 原文:[https://www.geeksforgeeks.org/c-inheritance-question-1/](https://www.geeksforgeeks.org/c-inheritance-question-1/)

```cpp
#include<iostream>

using namespace std;
class Base1 {
 public:
     Base1()
     { cout << " Base1's constructor called" << endl;  }
};

class Base2 {
 public:
     Base2()
     { cout << "Base2's constructor called" << endl;  }
};

class Derived: public Base1, public Base2 {
   public:
     Derived()
     {  cout << "Derived's constructor called" << endl;  }
};

int main()
{
   Derived d;
   return 0;
}
```

**(A)** 编译器依赖

**(B)** Base1 的构造函数调用
Base2 的构造函数调用
派生类的构造函数调用

T12】(C)Base2 的构造函数调用
Base1 的构造函数调用
派生类的构造函数调用

**(D)** 编译器错误

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)