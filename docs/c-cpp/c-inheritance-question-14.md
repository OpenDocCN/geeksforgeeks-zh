# C++ |继承|第 14 题

> 原文:[https://www.geeksforgeeks.org/c-inheritance-question-14/](https://www.geeksforgeeks.org/c-inheritance-question-14/)

考虑下面的 C++ 程序。

```cpp
#include<iostream>
using namespace std;
class A
{
public:
     A(){ cout <<"1";}
     A(const A &obj){ cout <<"2";}
};

class B: virtual A
{
public:
    B(){cout <<"3";}
    B(const B & obj){cout<<"4";}
};

class C: virtual A
{
public:
   C(){cout<<"5";}
   C(const C & obj){cout <<"6";}
};

class D:B,C
{
public:
    D(){cout<<"7";}
    D(const D & obj){cout <<"8";}
};

int main()
{
   D d1;
   D d(d1);
}
```

下面哪个没有打印出来？

*本问题由 sudhendra Baliga*
**(A)**2
**(B)**4
**(C)**6
**(D)**以上所有

**答案:****(D)**

**说明:**输出将为 13571355 还有一点，由于我们在基类之前使用的是虚函数，所以在多重继承中基类只有一个副本。而没有虚拟输出将是……13157……& …13158 as (1315713158)分别为每个派生类对象。

[本题小考](https://www.geeksforgeeks.org/c-plus-plus-gq/inheritance-gq/)