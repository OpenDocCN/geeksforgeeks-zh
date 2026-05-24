# C++ |继承|第 13 题

> 原文:[https://www.geeksforgeeks.org/c-inheritance-question-13/](https://www.geeksforgeeks.org/c-inheritance-question-13/)

```cpp
#include<iostream>
using namespace std;

class Base1
{
public:
    char c;
};

class Base2
{
public:
    int c;
};

class Derived: public Base1, public Base2
{
public:
    void show()  { cout << c; }
};

int main(void)
{
    Derived d;
    d.show();
    return 0;
}
```

**(A)** 编译器错误在“cout<<c；”
**(B)** 垃圾值
**(C)** 编译器在“类派生类:公共 Base1，公共 base 2”

**中出错答案:****(A)**

**解释:**变量‘C’在派生类的两个超类中都存在。所以对 c 的访问是不明确的。使用范围解析运算符可以消除歧义。

```cpp
#include<iostream>
using namespace std;

class Base1
{
public:
    char c;
};

class Base2
{
public:
    int c;
};

class Derived: public Base1, public Base2
{
public:
    void show()  { cout << Base2::c; }
};

int main(void)
{
    Derived d;
    d.show();
    return 0;
}
```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)