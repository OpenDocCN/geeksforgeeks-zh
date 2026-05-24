# 高级 C++ |虚拟构造器

> 原文:[https://www . geesforgeks . org/advanced-c-virtual-constructor/](https://www.geeksforgeeks.org/advanced-c-virtual-constructor/)

我们可以用 C++ 做一个类构造器*虚拟*来创建多态对象吗？不。C++ 是静态类型化的(RTTI 的目的不同)语言，对于 C++ 编译器来说，多形态地创建一个对象是没有意义的。编译器必须知道创建对象的类类型。换句话说，从 C++ 编译器的角度来看，要创建什么类型的对象是编译时决定的。如果我们将构造函数虚拟化，编译器会标记一个错误。事实上，除了*内联*之外，构造函数的声明中不允许有其他关键字。

在实际场景中，我们需要基于一些输入在类层次结构中创建一个派生类对象。换句话说，*对象创建和对象类型紧密耦合，这迫使修改扩展。虚拟构造函数的目标是将对象创建从其类型*中分离出来。

我们如何在运行时创建所需类型的对象？例如，请参见以下示例程序。

```cpp
#include <iostream>
using namespace std;

//// LIBRARY START
class Base
{
public:

    Base() { }

    virtual // Ensures to invoke actual object destructor
    ~Base() { }

    // An interface
    virtual void DisplayAction() = 0;
};

class Derived1 : public Base
{
public:
    Derived1()
    {
        cout << "Derived1 created" << endl;
    }

    ~Derived1()
    {
        cout << "Derived1 destroyed" << endl;
    }

    void DisplayAction()
    {
        cout << "Action from Derived1" << endl;
    }
};

class Derived2 : public Base
{
public:
    Derived2()
    {
        cout << "Derived2 created" << endl;
    }

    ~Derived2()
    {
        cout << "Derived2 destroyed" << endl;
    }

    void DisplayAction()
    {
        cout << "Action from Derived2" << endl;
    }
};

//// LIBRARY END

class User
{
public:

    // Creates Drived1
    User() : pBase(nullptr)
    {
        // What if Derived2 is required? - Add an if-else ladder (see next sample)
        pBase = new Derived1();
    }

    ~User()
    {
        if( pBase )
        {
            delete pBase;
            pBase = nullptr;
        }
    }

    // Delegates to actual object
    void Action()
    {
        pBase->DisplayAction();
    }

private:
    Base *pBase;
};

int main()
{
    User *user = new User();

    // Need Derived1 functionality only
    user->Action();

    delete user;
}
```

在上面的示例中，假设层次结构*基础*、*衍生 1* 和*衍生 2* 是库代码的一部分。类*用户*是试图利用层次结构的实用类。*主*功能通过*用户*类消耗*基础*层次功能。

用户类构造器总是创建*衍生 1* 对象。如果*用户*的消费者(我们这里的*主*需要*衍生 2* 功能，*用户*需要创建“ ***新衍生 2()*** ”并强制重新编译。重新编译是不好的设计方式，所以我们可以选择下面的方法。

在进入细节之前，让我们回答一下，谁来指定创建*德里维 1* 或*德里维 2* 对象？明明是*用户*阶层的消费者。*用户*类可以利用 if-else 阶梯创建*衍生 1* 或*衍生 2* ，如下例所示:

```cpp
#include <iostream>
using namespace std;

//// LIBRARY START
class Base
{
public:
    Base() { }

    virtual // Ensures to invoke actual object destructor
    ~Base() { }

    // An interface
    virtual void DisplayAction() = 0;
};

class Derived1 : public Base
{
public:
    Derived1()
    {
        cout << "Derived1 created" << endl;
    }

    ~Derived1()
    {
        cout << "Derived1 destroyed" << endl;
    }

    void DisplayAction()
    {
        cout << "Action from Derived1" << endl;
    }
};

class Derived2 : public Base
{
public:
    Derived2()
    {
        cout << "Derived2 created" << endl;
    }

    ~Derived2()
    {
        cout << "Derived2 destroyed" << endl;
    }

    void DisplayAction()
    {
        cout << "Action from Derived2" << endl;
    }
};

//// LIBRARY END

class User
{
public:

    // Creates Derived1 or Derived2 based on input
    User() : pBase(nullptr)
    {
        int input; // ID to distinguish between
                   // Derived1 and Derived2

        cout << "Enter ID (1 or 2): ";
        cin  >> input;

        while( (input !=  1) && (input !=  2) )
        {
            cout << "Enter ID (1 or 2 only): ";
            cin  >> input;
        }

        if( input == 1 )
        {
            pBase = new Derived1;
        }
        else
        {
            pBase = new Derived2;
        }

        // What if Derived3 being added to the class hierarchy?
    }

    ~User()
    {
        if( pBase )
        {
            delete pBase;
            pBase = nullptr;
        }
    }

    // Delegates to actual object
    void Action()
    {
        pBase->DisplayAction();
    }

private:
    Base *pBase;
};

int main()
{
    User *user = new User();

    // Need either Derived1 or Derived2 functionality
    user->Action();

    delete user;
}
```

上面的代码*不*开放扩展，这是一个不灵活的设计。简单来说，如果库用新的类*更新了*基础*类层次结构，那么将会得到 3* 。*用户*类如何创建*衍生 3* 对象？一种方法是更新 if-else 阶梯，该阶梯基于新的输入 ID 3 创建 *Derived3* 对象，如下所示，

```cpp
#include <iostream>
using namespace std;

class User
{
public:
    User() : pBase(nullptr)
    {
        // Creates Drived1 or Derived2 based on need

        int input; // ID to distinguish between
                   // Derived1 and Derived2

        cout << "Enter ID (1 or 2): ";
        cin  >> input;

        while( (input !=  1) && (input !=  2) )
        {
            cout << "Enter ID (1 or 2 only): ";
            cin  >> input;
        }

        if( input == 1 )
        {
            pBase = new Derived1;
        }
        else if( input == 2 )
        {
            pBase = new Derived2;
        }
        else
        {
            pBase = new Derived3;
        }
    }

    ~User()
    {
        if( pBase )
        {
            delete pBase;
            pBase = nullptr;
        }
    }

    // Delegates to actual object
    void Action()
    {
        pBase->DisplayAction();
    }

private:
    Base *pBase;
};
```

以上修改迫使 *User* 类的用户重新编译，设计不好(不灵活)！并且不会因为*基地*的扩展而关闭*用户*类的进一步修改。

问题在于对象的创建。向层次结构中添加新类迫使*用户*类的依赖者重新编译。我们不能将创建对象的动作委托给类层次结构本身或者一个行为虚拟的函数吗？通过将对象创建委托给类层次结构(或静态函数)，我们可以避免*用户*和*基础*层次结构之间的紧密耦合。够理论，看下面的代码，

```cpp
#include <iostream>
using namespace std;

//// LIBRARY START
class Base
{
public:

    // The "Virtual Constructor"
    static Base *Create(int id);

    Base() { }

    virtual // Ensures to invoke actual object destructor
    ~Base() { }

    // An interface
    virtual void DisplayAction() = 0;
};

class Derived1 : public Base
{
public:
    Derived1()
    {
        cout << "Derived1 created" << endl;
    }

    ~Derived1()
    {
        cout << "Derived1 destroyed" << endl;
    }

    void DisplayAction()
    {
        cout << "Action from Derived1" << endl;
    }
};

class Derived2 : public Base
{
public:
    Derived2()
    {
        cout << "Derived2 created" << endl;
    }

    ~Derived2()
    {
        cout << "Derived2 destroyed" << endl;
    }

    void DisplayAction()
    {
        cout << "Action from Derived2" << endl;
    }
};

class Derived3 : public Base
{
public:
    Derived3()
    {
        cout << "Derived3 created" << endl;
    }

    ~Derived3()
    {
        cout << "Derived3 destroyed" << endl;
    }

    void DisplayAction()
    {
        cout << "Action from Derived3" << endl;
    }
};

// We can also declare "Create" outside Base
// But it is more relevant to limit it's scope to Base
Base *Base::Create(int id)
{
    // Just expand the if-else ladder, if new Derived class is created
    // User code need not be recompiled to create newly added class objects

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

//// UTILITY START
class User
{
public:
    User() : pBase(nullptr)
    {
        // Receives an object of Base hierarchy at runtime

        int input;

        cout << "Enter ID (1, 2 or 3): ";
        cin >> input;

        while( (input !=  1) && (input !=  2) && (input !=  3) )
        {
            cout << "Enter ID (1, 2 or 3 only): ";
            cin >> input;
        }

        // Get object from the "Virtual Constructor"
        pBase = Base::Create(input);
    }

    ~User()
    {
        if( pBase )
        {
            delete pBase;
            pBase = nullptr;
        }
    }

    // Delegates to actual object
    void Action()
    {
        pBase->DisplayAction();
    }

private:
    Base *pBase;
};

//// UTILITY END

//// Consumer of User (UTILITY) class
int main()
{
    User *user = new User();

    // Action required on any of Derived objects
    user->Action();

    delete user;
}
```

*用户*类独立于对象创建。它将该职责委托给*基地*，并以标识的形式提供输入。如果库添加了新类*衍生 4* ，库修改器将扩展*创建*内的 if-else 阶梯以返回正确的对象。由于*基础*的扩展，*用户*的消费者无需重新编译他们的代码。

请注意，函数 *Create* 用于在运行时返回不同类型的 *Base* 类对象。它就像虚拟构造器，在模式术语中也被称为*工厂方法*。

模式世界展示了实现上述概念的不同方式。此外，上述代码还存在一些潜在的设计问题。我们的目标是提供一些关于虚拟构造的见解，基于一些输入动态地创建对象。我们有这方面的优秀书籍，感兴趣的读者可以参考它们来获得更多信息。

——**[文基](http://www.linkedin.com/in/ramanawithu)** 。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。