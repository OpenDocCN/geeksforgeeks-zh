# 在 C++ 中调用构造函数/析构函数中的虚方法

> 原文:[https://www . geesforgeks . org/calling-virtual-methods-in-constructordestructor-in-CPP/](https://www.geeksforgeeks.org/calling-virtual-methods-in-constructordestructor-in-cpp/)

**先决条件:**[c++ 中的虚函数](https://www.geeksforgeeks.org/virtual-function-cpp/)
从构造函数或析构函数调用虚函数在大多数情况下被认为是危险的，必须尽可能避免。所有 C++ 实现都需要调用在当前构造函数的层次结构级别定义的函数版本，而不是进一步调用。
可以在构造函数中调用虚函数。对象是从基础向上构建的，“先基础后派生”。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// calling virtual methods in
// constructor/destructor
#include<iostream>
using namespace std;

class dog
{
public:
    dog()
    {
        cout<< "Constructor called" <<endl;
        bark() ;
    }

    ~dog()
    {
        bark();
    }

    virtual void bark()
    {
        cout<< "Virtual method called" <<endl;
    }

    void seeCat()
    {
        bark();
    }
};

class Yellowdog : public dog
{
public:
        Yellowdog()
        {
            cout<< "Derived class Constructor called" <<endl;
        }
        void bark()
        {
            cout<< "Derived class Virtual method called" <<endl;
        }
};

int main()
{
    Yellowdog d;
    d.seeCat();
}
```

输出:

```cpp
Constructor called
Virtual method called
Derived class Constructor called
Derived class Virtual method called
Virtual method called
```

**说明:**

*   dog 类中的 bark 方法在构造函数和析构函数中被调用。
*   当创建黄狗的对象时，调用狗的构造函数，然后调用黄狗的构造函数，并颠倒调用析构函数的顺序。
*   虽然，bark 方法是虚方法，但是当它在构造函数内部被调用**时，它将表现为非虚方法，因为到了 dog(base)类的构造函数**被调用的时候，就像上面的代码一样，Yellowdog(派生类)并不是在那个时候被构造的。
*   因此，调用对象尚未构造的类的成员函数，编译器调用 bark 方法的狗类版本是很危险的。析构函数也是如此，当黄狗的对象“d”被破坏时，首先调用黄狗类的析构函数，然后调用狗类的析构函数，但此时黄狗已经被破坏，因此调用狗类版本的树皮。

**注意:**强烈建议避免从构造函数/析构函数调用虚方法。
[虚拟功能小测验](https://www.geeksforgeeks.org/c-plus-plus-gq/virtual-functions-gq/)
本文由**雅什辛拉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。