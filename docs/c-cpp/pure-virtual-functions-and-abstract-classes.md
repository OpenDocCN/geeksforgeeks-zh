# c++ 中的纯虚函数和抽象类

> 原文:[https://www . geesforgeks . org/pure-virtual-functions-and-abstract-class/](https://www.geeksforgeeks.org/pure-virtual-functions-and-abstract-classes/)

有时不能在基类中提供所有函数的实现，因为我们不知道实现。这样的类叫做抽象类。例如，让 Shape 成为一个基类。我们不能在 Shape 中提供函数 draw()的实现，但是我们知道每个派生类都必须有 draw()的实现。同样，一个动物类没有 move()的实现(假设所有动物都会移动)，但是所有动物都必须知道如何移动。我们不能创建抽象类的对象。
c++ 中的纯虚函数(或抽象函数)是[虚函数](https://www.geeksforgeeks.org/virtual-functions-and-runtime-polymorphism-in-c-set-1-introduction/)，我们可以对其进行实现，但是我们必须在派生类中重写该函数，否则派生类也将成为抽象类(有关我们在哪里为这些函数提供实现的更多信息，请参考本[https://stack overflow . com/questions/2089083/pure-virtual-function-with-implementation](https://stackoverflow.com/questions/2089083/pure-virtual-function-with-implementation))。纯虚函数通过在声明中赋值 0 来声明。请参见以下示例。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// An abstract class
class Test
{   
    // Data members of class
public:
    // Pure Virtual Function
    virtual void show() = 0;

   /* Other members */
};
```

**一个完整的例子:**
一个纯虚函数是由抽象类派生的类实现的。下面是一个简单的例子来证明这一点。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;

class Base
{
   int x;
public:
    virtual void fun() = 0;
    int getX() { return x; }
};

// This class inherits from Base and implements fun()
class Derived: public Base
{
    int y;
public:
    void fun() { cout << "fun() called"; }
};

int main(void)
{
    Derived d;
    d.fun();
    return 0;
}
```

**输出:**

```cpp
fun() called
```

**一些有趣的事实:**
**1)** *一个类如果至少有一个纯虚函数就是抽象的。*
在下面的例子中，Test 是一个抽象类，因为它有一个纯虚函数 show()。

## C++

// pure virtual functions make a class abstract#include <iostream>using namespace std;

类测试
{
int x；
公:
虚空显()= 0；
int GetX(){ return x；}
}；

int main(void)
{
Test t；
返回 0；
}</iostream> 

**输出:**

```cpp
Compiler Error: cannot declare variable 't' to be of abstract
 type 'Test' because the following virtual functions are pure 
within 'Test': note:     virtual void Test::show() 
```

**2)** *我们可以有抽象类类型的指针和引用。*
例如，以下程序运行良好。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;

class Base
{
public:
    virtual void show() = 0;
};

class Derived: public Base
{
public:
    void show() { cout << "In Derived \n"; }
};

int main(void)
{
    Base *bp = new Derived();
    bp->show();
    return 0;
}
```

**输出:**

```cpp
In Derived 
```

**3)** *如果我们不覆盖派生类中的纯虚函数，那么派生类也就变成了抽象类。*
下面的例子演示了同样的情况。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;
class Base
{
public:
    virtual void show() = 0;
};

class Derived : public Base { };

int main(void)
{
  Derived d;
  return 0;
}
```

```cpp
Compiler Error: cannot declare variable 'd' to be of abstract type 
'Derived'  because the following virtual functions are pure within
'Derived': virtual void Base::show() 
```

**4)** *抽象类可以有构造函数。*
例如，下面的程序编译运行良好。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;

// An abstract class with constructor
class Base
{
protected:
int x;
public:
virtual void fun() = 0;
Base(int i) {
              x = i; 
            cout<<"Constructor of base called\n";
            }
};

class Derived: public Base
{
    int y;
public:
    Derived(int i, int j):Base(i) { y = j; }
    void fun() { cout << "x = " << x << ", y = " << y<<'\n'; }
};

int main(void)
{ 
    Derived d(4, 5); 
    d.fun();

  //object creation using pointer of base class
    Base *ptr=new Derived(6,7);
      ptr->fun();
    return 0;
}
```

**输出:**

```cpp
Constructor of base called
x = 4, y = 5
Constructor of base called
x = 6, y = 7
```

**与 Java 的比较**
在 Java 中，一个类可以通过使用抽象关键字进行抽象。类似地，通过使用抽象关键字，可以使函数成为纯虚拟的或抽象的。详见
Java 中的[抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/)。
**接口 vs 抽象类:**
一个接口没有它的任何方法的实现，它可以被认为是方法声明的集合。在 C++ 中，可以通过将所有方法都设为纯虚拟来模拟一个接口。在 Java 中，接口有一个单独的关键字。

我们可以把 Interface 看作 C++ 中的头文件，就像在头文件中，我们只提供将要实现它的类的主体。类似地，在接口中的 java 中，我们只提供类的主体，并在实现它的任何类中编写实际代码。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。