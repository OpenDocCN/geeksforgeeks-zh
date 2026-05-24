# C++ |静态关键词|问题 4

> 原文:[https://www.geeksforgeeks.org/c-static-keyword-question-4/](https://www.geeksforgeeks.org/c-static-keyword-question-4/)

预测后续 C++ 程序的输出。

```cpp
#include <iostream>
using namespace std;

class A
{
private:
    int x;
public:
    A(int _x)  {  x = _x; }
    int get()  { return x; }
};

class B
{
    static A a;
public:
   static int get()
   {  return a.get(); }
};

int main(void)
{
    B b;
    cout << b.get();
    return 0;
}
```

**(A)** 0
**(B)** 链接器错误:未定义引用 B::a
**(C)** 链接器错误:无法访问静态 a
**(D)** 链接器错误:多个同名函数 get()

**答案:****(B)**

**解释:**存在编译器错误，因为静态成员 A 未定义

为了修复这个错误，我们需要显式地定义一个。

```cpp
#include <iostream >
using namespace std;

class A
{
private:
    int x;
public:
    A(int _x)  {  x = _x; }
    int get()  { return x; }
};

class B
{
    static A a;
public:
   static int get()
   {  return a.get(); }
};

A B::a(0);

int main(void)
{
    B b;
    cout << b.get();
    return 0;
}

```

[本题小考](https://www.geeksforgeeks.org/c-plus-plus-gq/static-keyword-gq/)