# 默认分配运算符和引用

> 原文:[https://www . geesforgeks . org/default-assignment-operator-and-references/](https://www.geeksforgeeks.org/default-assignment-operator-and-references/)

我们已经讨论了动态分配资源[的赋值运算符重载。这是前一篇文章的延伸。在](https://www.geeksforgeeks.org/assignment-operator-overloading-in-c/)[之前的帖子](https://www.geeksforgeeks.org/assignment-operator-overloading-in-c/)中，我们讨论了当我们不编写自己的赋值运算符时，编译器创建的赋值运算符会进行浅拷贝，从而导致问题。当我们的类中有引用并且没有用户定义的赋值操作符时会发生什么。例如，预测以下程序的输出。

```cpp
#include<iostream>
using namespace std;

class Test
{
    int x;
    int &ref;
public:
    Test (int i):x(i), ref(x) {}
    void print() { cout << ref; }
    void setX(int i) { x = i; }    
};

int main()
{
    Test t1(10);
    Test t2(20);
    t2 = t1;
    t1.setX(40);
    t2.print();
    return 0;
}
```

输出:

```cpp
Compiler Error: non-static reference member 'int& Test::ref', 
             can't use default assignment operator
```

在下列情况下，编译器不会创建默认赋值运算符

**1。**类有一个常量类型或引用类型的非静态数据成员
**2。**类有一个类型的非静态数据成员，该成员有一个不可访问的复制分配运算符
**3。**类是从带有不可访问的复制分配运算符的基类派生的

当上述任一条件成立时，用户必须定义赋值运算符。例如，如果我们在上面的代码中添加一个赋值操作符，代码可以正常工作，没有任何错误。

```cpp
#include<iostream>
using namespace std;

class Test
{
    int x;
    int &ref;
public:
    Test (int i):x(i), ref(x) {}
    void print() { cout << ref; }
    void setX(int i) { x = i; }    
    Test &operator = (const Test &t) { x = t.x; return *this; } 
};

int main()
{
    Test t1(10);
    Test t2(20);
    t2 = t1;
    t1.setX(40);
    t2.print();
    return 0;
}
```

输出:

```cpp
10
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。