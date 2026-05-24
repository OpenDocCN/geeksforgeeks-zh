# 是否可以显式调用构造函数和析构函数？

> 原文:[https://www . geesforgeks . org/可能-调用-构造函数-析构函数-显式/](https://www.geeksforgeeks.org/possible-call-constructor-destructor-explicitly/)

[构造函数](http://geeksquiz.com/constructors-c/)是创建对象时编译器自动调用的特殊成员函数，[析构函数](http://geeksquiz.com/destructors-c/)也是对象超出范围时编译器也隐式调用的特殊成员函数。当动态分配的对象被分配和销毁时，新操作符分配存储并调用构造函数，删除操作符调用析构函数并释放新操作符分配的内存时，也会调用它们。

可以显式调用构造函数和析构函数吗？
是的，可以由程序员显式调用特殊成员函数。以下程序显式调用构造函数和析构函数。

```cpp
#include <iostream>
using namespace std;

class Test
{
public:
    Test()  { cout << "Constructor is executed\n"; }
    ~Test() { cout << "Destructor is executed\n";  }
};

int main()
{
    Test();  // Explicit call to constructor
    Test t;    // local object
    t.~Test(); // Explicit call to destructor
    return 0;
}
```

输出:

```cpp
Constructor is executed
Destructor is executed
Constructor is executed
Destructor is executed
Destructor is executed 
```

当显式调用构造函数时，编译器会创建一个无名的临时对象，并立即销毁它。这就是为什么输出中的第二行是对析构函数的调用。
下面是我和比雅尼·斯特劳斯特鲁普博士通过邮件就这个话题的对话:

***Me:为什么 C++ 允许显式调用构造函数？你不觉得这不应该吗？
Bjarne 博士:不，类类型的临时对象是有用的。***

C++ 标准 12.4/14 节说
一旦对一个对象调用析构函数，该对象就不再存在；如果为生存期已结束的对象调用析构函数，则行为未定义[示例:如果显式调用自动对象的析构函数，并且随后以通常调用对象隐式销毁的方式保留块，则行为未定义。—结束示例]。

正如这里提到的，我们永远不应该在局部(自动)对象上显式调用析构函数，因为这样做可能会得到非常糟糕的结果。

本地对象在超出范围时会被编译器自动销毁，这是 C++ 语言的保证。一般来说，不应该显式调用特殊成员函数。
构造函数和析构函数也可以从类的成员函数中调用。参见以下程序:

```cpp
#include <iostream>
using namespace std;

class Test
{
public:
    Test()  { cout << "Constructor is executed\n"; }
    ~Test() { cout << "Destructor is executed\n";  }
    void show()  {  Test();  this->Test::~Test();  }
};

int main()
{
    Test t;
    t.show();
    return 0;
}
```

输出:

```cpp
Constructor is executed
Constructor is executed
Destructor is executed
Destructor is executed
Destructor is executed
```

只有当通过使用 placement new 将对象放置在内存中的特定位置时，才需要显式调用析构函数。动态分配对象时不应显式调用析构函数，因为 delete 运算符会自动调用析构函数。

作为练习，预测以下程序的输出:

```cpp
#include <iostream>
using namespace std;

class Test
{
public:
    Test()  { cout << "Constructor is executed\n"; }
    ~Test() { cout << "Destructor is executed\n";  }
    friend void fun(Test t);
};
void fun(Test t)
{
    Test();
    t.~Test();
}
int main()
{
    Test();
    Test t;
    fun(t);
    return 0;
}
```

**来源:**
[http://www . paras shift . com/c++-FAQ/don-call-dtor-on-local . html](http://www.parashift.com/c++-faq/dont-call-dtor-on-local.html)
[http://www.parashift.com/c++-faq/placement-new.html](http://www.parashift.com/c++-faq/placement-new.html)
[http://msdn.microsoft.com/en-us/library/35xa3368.aspx](http://msdn.microsoft.com/en-us/library/35xa3368.aspx)

本文投稿**遇见普拉瓦西**。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论