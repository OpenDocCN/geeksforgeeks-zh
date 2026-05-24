# 基于构造函数/析构函数的 C++ 面试题。

> 原文:[https://www . geesforgeks . org/c-面试-提问-基于构造函数-析构函数/](https://www.geeksforgeeks.org/c-interview-questions-based-on-constructors-destructors/)

**1。什么是[析构器](https://www.geeksforgeeks.org/destructors-c/)？**
俺们。析构函数是一个成员函数，当一个对象被删除/销毁或超出范围时调用。

```cpp
class String {
private:
    char* s;
    int size;

public:
    String(char*); // constructor
    ~String(); // destructor
};
```

**2。C++ 中使用析构函数的目的是什么？**
俺们。析构函数的主要目的是释放所有资源(打开的文件、打开的套接字、数据库连接、资源锁等)。)是在对象的生命周期中分配的。

```cpp
// CPP program to demonstrate destructors.
class Geeks {
private:

    // a private-access pointer to integer
    int* myPrvIntPtr; 
public:
    Geeks()
    {
        // default constructor
        myPrvIntPtr = new int(0);

        // allocate a new integer, place its address in myPrvIntPtr
    }

    ~Geeks()
    {
        // de-allocate the integer whose address 
        // is stored in myPrvIntPtr
        delete myPrvIntPtr;       
    }
};
```

**3。构造函数有什么用？**
构造函数是一个与类名同名的特殊函数。构造函数是在为类创建对象时调用的。构造函数用于在创建对象时初始化对象的实例变量。构造函数也用于为虚拟函数创建虚拟表。

**4。不使用复制构造函数怎么办？它在哪里产生问题？**
请看[复制建造师](https://www.geeksforgeeks.org/copy-constructor-in-cpp/)

**5。C++ 编译器会在我们自己编写的时候创建默认构造函数吗？**
在 C++ 中，编译器默认为每个类创建默认构造函数。但是，如果我们定义自己的构造函数，编译器不会创建默认的构造函数。

**6。C++ 中构造函数的执行顺序是怎样的？**
俺们。首先执行基类构造函数，然后执行派生类构造函数，所以在继承树中从上到下执行。

**7。C++ 中析构函数的执行顺序是怎样的？**
俺们。一般是派生类析构函数，然后是基类析构函数。除非我们将派生类对象放入基类指针(或引用变量)中，并且忘记为基类析构函数提供虚拟关键字。详见[虚拟析构器](https://www.geeksforgeeks.org/virtual-destructor/)。

**8。我们能有虚拟析构函数吗？如果是这样，虚拟析构函数有什么用。**
俺们。是的，我们可以。这是为了确保在运行时调用正确的类析构函数。特别是当我们使用基类指针或引用来保存派生类对象时。如果我们没有虚拟析构函数，那么它最终只会调用基类析构函数。

```cpp
// CPP program without virtual destructor
// causing undefined behavior
#include <iostream>

using namespace std;

class base {
public:
    base()
    {
        cout << "Constructing base \n";
    }
    ~base()
    {
        cout << "Destructing base \n";
    }
};

class derived : public base {
public:
    derived()
    {
        cout << "Constructing derived \n";
    }
    ~derived()
    {
        cout << "Destructing derived \n";
    }
};

int main(void)
{
    derived* d = new derived();
    base* b = d;
    delete b;
    getchar();
    return 0;
}
```