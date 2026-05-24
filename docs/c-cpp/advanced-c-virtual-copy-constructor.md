# 高级 C++ |虚拟副本构造器

> 原文:[https://www . geesforgeks . org/advanced-c-virtual-copy-constructor/](https://www.geeksforgeeks.org/advanced-c-virtual-copy-constructor/)

在[虚拟构造函数](https://www.geeksforgeeks.org/advanced-c-virtual-constructor/)这个成语中，我们已经看到了构造一个对象的方法，这个对象的类型直到运行时才被确定。有没有可能在不知道对象确切的类类型的情况下创建对象？*虚拟副本构造器*解决了这个问题。

有时我们可能需要从另一个现有的对象构造一个对象。确切地说，复制构造函数也是如此。新对象的初始状态将基于另一个现有的对象状态。当一个对象从另一个对象实例化时，编译器调用复制构造函数。然而，编译器需要具体的类型信息来调用适当的复制构造函数。

```cpp
#include <iostream>
using namespace std;

class Base
{
public:
    //
};

class Derived : public Base
{
public:
    Derived()
    {
        cout << "Derived created" << endl;
    }

    Derived(const Derived &rhs)
    {
        cout << "Derived created by deep copy" << endl;
    }

    ~Derived()
    {
        cout << "Derived destroyed" << endl;
    }
};

int main()
{
    Derived s1;

    Derived s2 = s1;  // Compiler invokes "copy constructor"
                      // Type of s1 and s2 are concrete to compiler

    // How can we create Derived1 or Derived2 object
    // from pointer (reference) to Base class pointing Derived object?

    return 0;
}
```

如果我们不能决定从哪种类型的对象，复制结构要做什么？例如，[虚拟构造器](https://www.geeksforgeeks.org/advanced-c-virtual-constructor/)在运行时基于一些输入创建一个类层次的对象。当我们想从虚拟构造函数创建的另一个对象复制构造一个对象时，我们不能使用通常的复制构造函数。我们需要一个特殊的克隆函数，它可以在运行时复制对象。

例如，考虑一个绘图应用程序。您可以选择已经在画布上绘制的对象，并粘贴同一对象的另一个实例。从程序员的角度来看，我们不能决定复制粘贴哪个对象，因为这是运行时的决定。我们需要虚拟副本构造器来帮助。

同样，考虑夹板应用。剪切板可以容纳不同类型的对象，并从现有对象复制对象，将它们粘贴到应用程序画布上。同样，要复制什么类型的对象是运行时决定的。虚拟复制构造函数填补了这一空白。见下例，

```cpp
#include <iostream>
using namespace std;

//// LIBRARY SRART
class Base
{
public:
    Base() { }

    virtual // Ensures to invoke actual object destructor
        ~Base() { }

    virtual void ChangeAttributes() = 0;

    // The "Virtual Constructor"
    static Base *Create(int id);

    // The "Virtual Copy Constructor"
    virtual Base *Clone() = 0;
};

class Derived1 : public Base
{
public:
    Derived1()
    {
        cout << "Derived1 created" << endl;
    }

    Derived1(const Derived1& rhs)
    {
        cout << "Derived1 created by deep copy" << endl;
    }

    ~Derived1()
    {
        cout << "~Derived1 destroyed" << endl;
    }

    void ChangeAttributes()
    {
        cout << "Derived1 Attributes Changed" << endl;
    }

    Base *Clone()
    {
        return new Derived1(*this);
    }
};

class Derived2 : public Base
{
public:
    Derived2()
    {
        cout << "Derived2 created" << endl;
    }

    Derived2(const Derived2& rhs)
    {
        cout << "Derived2 created by deep copy" << endl;
    }

    ~Derived2()
    {
        cout << "~Derived2 destroyed" << endl;
    }

    void ChangeAttributes()
    {
        cout << "Derived2 Attributes Changed" << endl;
    }

    Base *Clone()
    {
        return new Derived2(*this);
    }
};

class Derived3 : public Base
{
public:
    Derived3()
    {
        cout << "Derived3 created" << endl;
    }

    Derived3(const Derived3& rhs)
    {
        cout << "Derived3 created by deep copy" << endl;
    }

    ~Derived3()
    {
        cout << "~Derived3 destroyed" << endl;
    }

    void ChangeAttributes()
    {
        cout << "Derived3 Attributes Changed" << endl;
    }

    Base *Clone()
    {
        return new Derived3(*this);
    }
};

// We can also declare "Create" outside Base.
// But is more relevant to limit it's scope to Base
Base *Base::Create(int id)
{
    // Just expand the if-else ladder, if new Derived class is created
    // User need not be recompiled to create newly added class objects

    if( id == 1 )
    {
        return new Derived1;
    }
    else if( id == 2 )
    {
        return new Derived2;
    }
    else
    {
        return new Derived3;
    }
}
//// LIBRARY END

//// UTILITY SRART
class User
{
public:
    User() : pBase(0)
    {
        // Creates any object of Base heirarchey at runtime

        int input;

        cout << "Enter ID (1, 2 or 3): ";
        cin >> input;

        while( (input !=  1) && (input !=  2) && (input !=  3) )
        {
            cout << "Enter ID (1, 2 or 3 only): ";
            cin >> input;
        }

        // Create objects via the "Virtual Constructor"
        pBase = Base::Create(input);
    }

    ~User()
    {
        if( pBase )
        {
            delete pBase;
            pBase = 0;
        }
    }

    void Action()
    {
        // Duplicate current object
        Base *pNewBase = pBase->Clone();

        // Change its attributes
        pNewBase->ChangeAttributes();

        // Dispose the created object
        delete pNewBase;
    }

private:
    Base *pBase;
};

//// UTILITY END

//// Consumer of User (UTILITY) class
int main()
{
    User *user = new User();

    user->Action();

    delete user;
}
```

*用户*类在虚拟构造器的帮助下创建对象。要创建的对象基于用户输入。*动作()*正在复制正在创建的对象并修改其属性。借助*克隆()*虚拟函数创建的复制对象，该函数也被认为是*虚拟复制构造器*。*克隆()*方法背后的概念是*原型模式*的构建块。

——**[文基](http://www.linkedin.com/in/ramanawithu)** 。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。