# c++ 中的虚函数

> 原文:[https://www.geeksforgeeks.org/virtual-function-cpp/](https://www.geeksforgeeks.org/virtual-function-cpp/)

虚函数是在基类中声明并由派生类重新定义(重写)的成员函数。当您使用指向基类的指针或引用来引用派生类对象时，您可以为该对象调用一个虚拟函数并执行该函数的派生类版本。

*   虚函数确保为对象调用正确的函数，而不管用于函数调用的引用(或指针)的类型如何。
*   它们主要用于实现[运行时多态](https://www.geeksforgeeks.org/polymorphism-in-c/)
*   函数在基类中用**虚拟**关键字声明。
*   函数调用的解析是在运行时完成的。

**虚拟功能规则**

1.  虚函数不能是静态的。
2.  虚拟函数可以是另一个类的友元函数。
3.  应该使用基类类型的指针或引用来访问虚拟函数，以实现运行时多态性。
4.  虚函数的原型在基类和派生类中应该是相同的。
5.  它们总是在基类中定义，并在派生类中重写。派生类不一定要重写(或重新定义虚拟函数)，在这种情况下，将使用函数的基类版本。
6.  一个类可以有[虚拟析构函数](https://www.geeksforgeeks.org/virtual-destructor/)，但不能有虚拟构造函数。

**虚函数的编译时(早期绑定)VS 运行时(后期绑定)行为**

考虑下面显示虚函数运行时行为的简单程序。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// concept of Virtual Functions

#include <iostream>
using namespace std;

class base {
public:
    virtual void print()
    {
        cout << "print base class" << endl;
    }

    void show()
    {
        cout << "show base class" << endl;
    }
};

class derived : public base {
public:
    void print()
    {
        cout << "print derived class" << endl;
    }

    void show()
    {
        cout << "show derived class" << endl;
    }
};

int main()
{
    base* bptr;
    derived d;
    bptr = &d;

    // virtual function, binded at runtime
    bptr->print();

    // Non-virtual function, binded at compile time
    bptr->show();
}
```

**输出:**

```cpp
print derived class
show base class
```

**说明:**运行时多态性只能通过基类类型的指针(或引用)来实现。此外，基类指针可以指向基类的对象以及派生类的对象。在上面的代码中，基类指针“bptr”包含派生类的对象“d”的地址。
后期绑定(Runtime)是根据指针的内容(即指针指向的位置)进行的，前期绑定(Compile time)是根据指针的类型进行的，因为 print()函数是用 virtual 关键字声明的，所以在运行时绑定(输出是 *print 派生类*因为指针指向派生类的对象)，show()是非虚化的，所以在编译时绑定(输出是 *show 基类*因为指针是基类)。
**注意:**如果我们已经在基类中创建了一个虚函数，并且它正在派生类中被重写，那么我们在派生类中不需要 virtual 关键字，函数在派生类中被自动视为虚函数。

**虚函数的工作(VTABLE 和 VPTR 的概念)**
正如这里所讨论的，如果一个类包含虚函数，那么编译器本身会做两件事:

1.  如果创建了该类的对象，则插入一个**虚拟指针(VPTR)** 作为该类的数据成员，以指向该类的 VTABLE。对于创建的每个新对象，都会插入一个新的虚拟指针作为该类的数据成员。
2.  不管是否创建了对象，**一个静态的函数指针数组，称为 VTABLE** ，其中每个单元包含该类中包含的每个虚函数的地址。

考虑下面的例子:

![](img/735d6bf3ea877ac407225b8cd8baf4f9.png)

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// working of Virtual Functions
#include <iostream>
using namespace std;

class base {
public:
    void fun_1() { cout << "base-1\n"; }
    virtual void fun_2() { cout << "base-2\n"; }
    virtual void fun_3() { cout << "base-3\n"; }
    virtual void fun_4() { cout << "base-4\n"; }
};

class derived : public base {
public:
    void fun_1() { cout << "derived-1\n"; }
    void fun_2() { cout << "derived-2\n"; }
    void fun_4(int x) { cout << "derived-4\n"; }
};

int main()
{
    base* p;
    derived obj1;
    p = &obj1;

    // Early binding because fun1() is non-virtual
    // in base
    p->fun_1();

    // Late binding (RTP)
    p->fun_2();

    // Late binding (RTP)
    p->fun_3();

    // Late binding (RTP)
    p->fun_4();

    // Early binding but this function call is
    // illegal(produces error) because pointer
    // is of base type and function is of
    // derived class
    // p->fun_4(5);
}
```

**输出:**

```cpp
base-1
derived-2
base-3
base-4
```

**说明:**最初，我们创建一个类型基类的指针，并用派生类对象的地址初始化它。当我们创建派生类的对象时，编译器创建一个指针作为包含派生类的 VTABLE 地址的类的数据成员。
类似的**后期和前期绑定**的概念如上述示例中所用。对于 fun_1()函数调用，调用函数的基类版本，fun_2()在派生类中被重写，所以调用派生类版本，fun_3()在派生类中不被重写，是虚函数，所以调用基类版本，同样 fun_4()也不被重写，所以调用基类版本。

**注:**派生类中的 fun_4(int)不同于基类中作为原型的虚函数 fun_4()两者的函数不同。
本文由**雅什·辛拉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。