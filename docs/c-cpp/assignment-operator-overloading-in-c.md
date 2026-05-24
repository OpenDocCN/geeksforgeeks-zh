# 我们应该什么时候用 C++ 写自己的赋值运算符？

> 原文:[https://www . geesforgeks . org/assignment-operator-overload-in-c/](https://www.geeksforgeeks.org/assignment-operator-overloading-in-c/)

答案与复制构造函数相同。如果一个类不包含指针，那么就不需要编写赋值运算符和复制构造函数。编译器为每个类创建默认的复制构造函数和赋值操作符。当我们有指针或任何运行时资源分配(如文件句柄、网络连接)时，编译器创建的复制构造函数和赋值运算符可能是不够的..等等。例如，考虑以下程序。

```cpp
#include<iostream>
using namespace std;

// A class without user defined assignment operator
class Test
{
    int *ptr;
public:
    Test (int i = 0)      { ptr = new int(i); }
    void setValue (int i) { *ptr = i; }
    void print()          { cout << *ptr << endl; }
};

int main()
{
    Test t1(5);
    Test t2;
    t2 = t1;
    t1.setValue(10);
    t2.print();
    return 0;
}
```

上述程序的输出为“10”。如果我们看一下 main()，我们使用 setValue()函数修改了‘t1’，但是更改也反映在对象‘T2’中。这种类型的意外更改会导致问题。
由于上述程序中没有用户定义的赋值运算符，编译器创建了一个默认的赋值运算符，将右手边的‘ptr’复制到左手边。所以两个 ptr 都指向同一个位置。

我们可以用两种方法来处理上述问题。

**1)** 不允许将一个对象分配给另一个对象。我们可以创建自己的虚拟赋值运算符，并使其私有。

**2)** 自己写赋值运算符，做深度复制。

复制构造函数也是如此。

下面是一个重载上述类的赋值运算符的示例。

```cpp
#include<iostream>
using namespace std;

class Test
{
    int *ptr;
public:
    Test (int i = 0)      { ptr = new int(i); }
    void setValue (int i) { *ptr = i; }
    void print()          { cout << *ptr << endl; }
    Test & operator = (const Test &t);
};

Test & Test::operator = (const Test &t)
{
   // Check for self assignment
   if(this != &t)
     *ptr = *(t.ptr);

   return *this;
}

int main()
{
    Test t1(5);
    Test t2;
    t2 = t1;
    t1.setValue(10);
    t2.print();
    return 0;
}
```

输出

```cpp
5
```

我们还应该在上面的类中添加一个复制构造函数，这样像“Test t3 = t4 也不引起任何问题。

注意赋值运算符中的 if 条件。重载赋值运算符时，我们必须检查自身赋值。否则将对象分配给它自己可能会导致意想不到的结果(参见[本](https://www.geeksforgeeks.org/g-fact-38/))。对于上面的“测试”类，自我赋值检查是不必要的，因为“ptr”总是指向一个整数，我们可以重用相同的内存。但总的来说，做自我分配检查是一种推荐的做法。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。