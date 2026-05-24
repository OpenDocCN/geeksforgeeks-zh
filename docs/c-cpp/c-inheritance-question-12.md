# C++ |继承|第 12 题

> 原文:[https://www.geeksforgeeks.org/c-inheritance-question-12/](https://www.geeksforgeeks.org/c-inheritance-question-12/)

```cpp
#include<iostream>
using namespace std;

class Base
{
protected:
    int a;
public:
    Base() {a = 0;}
};

class Derived1:  public Base
{
public:
    int c;
};

class Derived2:  public Base
{
public:
    int c;
};

class DerivedDerived: public Derived1, public Derived2
{
public:
    void show()  {   cout << a;  }
};

int main(void)
{
    DerivedDerived d;
    d.show();
    return 0;
}
```

**(A)** 第< <行编译器错误；A
**(B)** 0
**(C)** 编译器行内错误”类 DerivedDerived: public Derived1，public derived 2 "

**答案:****(A)**

**解释:**这是[钻石多重继承问题的典型例子](https://www.geeksforgeeks.org/multiple-inheritance-in-c/)。这里基类成员“a”是通过*衍生 1* 和*衍生 2* 继承的。所以在*中有两个“a”的副本衍生*，这使得陈述“cout<<a；”模棱两可。

C++ 中的解决方案是使用虚拟基类。例如，下面的程序运行良好，可以打印

#包含 <iostream>使用命名空间 std</iostream>

基类
{
受保护:
int a；
公:
基(){ a = 0；}
}；

class Derived1:虚拟公共基础
{
公共:
int c；
}；

class Derived2:虚拟公共基础
{
公共:
int c；
}；

class derived 派生类:public Derived1，public derived 2
{
public:
void show(){ cout<T5】a；}
}；

int main(void)
{
derived d d；
马超()；
返回 0；
}

[本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)