# C++ |继承|第 11 题

> 原文:[https://www.geeksforgeeks.org/c-inheritance-question-11/](https://www.geeksforgeeks.org/c-inheritance-question-11/)

```cpp
#include<iostream>
using namespace std;

class Base
{
public :
    int x, y;
public:
    Base(int i, int j){ x = i; y = j; }
};

class Derived : public Base
{
public:
    Derived(int i, int j):x(i), y(j) {}
    void print() {cout << x <<" "<< y; }
};

int main(void)
{
    Derived q(10, 10);
    q.print();
    return 0;
}
```

**(A)** 10 10
**(B)** 编译器错误
**(C)**0 0

**答案:****(B)**

**解释:**不能使用[初始化列表](https://www.geeksforgeeks.org/when-do-we-use-initializer-list-in-c/)直接赋值基类成员。我们应该调用基类构造函数来初始化基类成员。

以下是无错误程序并打印“10 10”

```cpp
#include<iostream>
using namespace std;

class Base
{
public :
    int x, y;
public:
    Base(int i, int j){ x = i; y = j; }
};

class Derived : public Base
{
public:
    Derived(int i, int j): Base(i, j) {}
    void print() {cout << x <<" "<< y; }
};

int main(void)
{
    Derived q(10, 10);
    q.print();
    return 0;
}
```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)