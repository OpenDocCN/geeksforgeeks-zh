# 虚拟析构器

> 原文:[https://www.geeksforgeeks.org/virtual-destructor/](https://www.geeksforgeeks.org/virtual-destructor/)

使用具有非虚拟析构函数的基类类型的指针删除派生类对象会导致未定义的行为。为了纠正这种情况，基类应该用虚拟析构函数来定义。例如，以下程序导致未定义的行为。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program without virtual destructor
// causing undefined behavior
#include <iostream>

using namespace std;

class base {
  public:
    base()    
    { cout << "Constructing base\n"; }
    ~base()
    { cout<< "Destructing base\n"; }    
};

class derived: public base {
  public:
    derived()    
     { cout << "Constructing derived\n"; }
    ~derived()
       { cout << "Destructing derived\n"; }
};

int main()
{
  derived *d = new derived(); 
  base *b = d;
  delete b;
  getchar();
  return 0;
}
```

虽然以下程序的输出在不同的编译器上可能不同，但是当使用 Dev-CPP 编译时，它会打印如下:

```cpp
Constructing base
Constructing derived
Destructing base
```

使基类析构函数虚拟保证了派生类的对象被正确析构，即基类和派生类析构函数都被调用。例如

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// A program with virtual destructor
#include <iostream>

using namespace std;

class base {
  public:
    base()    
    { cout << "Constructing base\n"; }
    virtual ~base()
    { cout << "Destructing base\n"; }    
};

class derived : public base {
  public:
    derived()    
    { cout << "Constructing derived\n"; }
    virtual ~derived()
    { cout << "Destructing derived\n"; }
};

int main()
{
  derived *d = new derived(); 
  base *b = d;
  delete b;
  getchar();
  return 0;
}
```

输出:

```cpp
Constructing base
Constructing derived
Destructing derived
Destructing base
```

作为一个指导方针，任何时候当你在一个类中有一个虚函数时，你应该立即添加一个虚析构函数(即使它什么也不做)。这样，您可以确保以后不会有任何意外。

参考:[安全编码](https://www.securecoding.cert.org/confluence/display/cplusplus/OOP34-CPP.+Ensure+the+proper+destructor+is+called+for+polymorphic+objects)
本文由**拉胡尔·古普塔**供稿。如果您发现任何不正确的地方，请写评论，或者您想分享更多关于上面讨论的主题的信息