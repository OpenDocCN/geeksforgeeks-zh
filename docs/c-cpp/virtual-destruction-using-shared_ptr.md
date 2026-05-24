# 在 C++ 中使用 shared_ptr 进行虚拟销毁

> 原文:[https://www . geesforgeks . org/virtual-destroy-use-shared _ ptr/](https://www.geeksforgeeks.org/virtual-destruction-using-shared_ptr/)

**先决条件:** [共享 _ ptr](https://www.geeksforgeeks.org/auto_ptr-unique_ptr-shared_ptr-weak_ptr-2/)[虚拟析构器](https://www.geeksforgeeks.org/virtual-destructor/)

我们知道，使用指向具有非虚拟析构函数的基类的指针删除派生类对象会导致未定义的行为。因此，我们将基类[析构函数设为虚拟的](https://www.geeksforgeeks.org/virtual-destructor/)，这样多态对象就可以按照正确的顺序(也就是创建的相反顺序)被正确删除。

类似的行为也可以通过使用 shared_ptr 来实现，而不需要基类析构函数是虚拟的。让我们看看下面的代码:

```cpp
// Program to show the order of destruction of objects using
// shared_ptr
#include <iostream>
#include <memory>
using namespace std;

class Base {
public:
    Base()
    {
        cout << "Constructing Base" << endl;
    }
    ~Base()
    {
        cout << "Destructing Base" << endl;
    }
};

class Derived : public Base {
public:
    Derived()
    {
        cout << "Constructing Derived" << endl;
    }
    ~Derived()
    {
        cout << "Destructing Derived" << endl;
    }
};

int main()
{
    std::shared_ptr<Base> sp{ new Derived };

    // make_shared can also be used to create sp.
    // std::shared_ptr<Base> sp{std::make_shared<Derived>()};
    // Use sp
}
```

输出:

```cpp
Constructing Base
Constructing Derived
Destructing Derived
Destructing Base

```

如上面的输出所示，不再需要使基类的析构函数虚拟化，同时实现虚拟析构函数行为。

**shared _ ptr 是如何实现这一神奇行为的？**

shared_ptr 会记住构造过程中使用的指针类型。例如，

```cpp
If you say shared_ptr{ new Derived {} },
then shared_ptr will internally store a Derived*. 
If you say shared_ptr{ new Base {} }, 
then it stores a Base*. 
```

当 shared_ptr 被析构时，它对存储的指针调用 delete。自然，对于非虚拟析构函数，对于 Base*它将调用 Base::~Base，对于派生类*它将调用派生类::~派生类。
**要点:**

*   该行为仅通过 **shared_ptr** 实现。
*   这种行为不是通过使用 unique_ptr 实现的。
*   STL 中的所有类都没有虚拟析构函数，所以如果从它们继承，要小心。如果你想继承，你可以在这种情况下使用 shared_ptr 来应用智能销毁。

**异常情况:从基础初始化**

考虑以下示例:

```cpp
// Program to show exception to this behavior while using
// shared_ptr
#include <iostream>
#include <memory>
using namespace std;

class Base {
public:
    Base()
    {
        cout << "Constructing Base" << endl;
    }
    ~Base()
    {
        cout << "Destructing Base" << endl;
    }
};

class Derived : public Base {
public:
    Derived()
    {
        cout << "Constructing Derived" << endl;
    }
    ~Derived()
    {
        cout << "Constructing Derived" << endl;
    }
};

int main()
{
    Base* p = new Derived{};
    std::shared_ptr<Base> sp{ p };
}
```

输出:

```cpp
Constructing Base
Constructing Derived
Destructing Base

```

在这里，如果 shared_ptr 是从 Base*(这里是‘p’)初始化的，那么这种神奇的智能破坏行为将会**而不是**实现，因为这将调用 Base::~Base()而不是 Derived::~Derived()。shared_ptr 将无法找到“p”所指向的对象的确切类型。所以在这种情况下，魔法不会发生。

**相关文章:**

*   C++ 中的纯虚拟析构函数
*   [在 C++ 中调用构造函数/析构函数中的虚方法](https://www.geeksforgeeks.org/calling-virtual-methods-in-constructordestructor-in-cpp/)

本文由 **Arnav Srivastava** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。