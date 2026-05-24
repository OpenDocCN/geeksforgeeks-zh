# c++ 中的对象切片

> 原文:[https://www.geeksforgeeks.org/object-slicing-in-c/](https://www.geeksforgeeks.org/object-slicing-in-c/)

在 C++ 中，可以将派生类对象分配给基类对象，但另一种方式是不可能的。

## C++

```cpp
class Base { int x, y; };

class Derived : public Base { int z, w; };

int main()
{
    Derived d;
    Base b = d; // Object Slicing,  z and w of d are sliced off
}
```

[对象切片](http://en.wikipedia.org/wiki/Object_slicing)当一个派生类对象被分配给一个基类对象时，派生类对象的附加属性被切片以形成基类对象。

## C++

```cpp
#include <iostream>
using namespace std;

class Base
{
protected:
    int i;
public:
    Base(int a)     { i = a; }
    virtual void display()
    { cout << "I am Base class object, i = " << i << endl; }
};

class Derived : public Base
{
    int j;
public:
    Derived(int a, int b) : Base(a) { j = b; }
    virtual void display()
    { cout << "I am Derived class object, i = "
           << i << ", j = " << j << endl;  }
};

// Global method, Base class object is passed by value
void somefunc (Base obj)
{
    obj.display();
}

int main()
{
    Base b(33);
    Derived d(45, 54);
    somefunc(b);
    somefunc(d);  // Object Slicing, the member j of d is sliced off
    return 0;
}
```

输出:

```cpp
I am Base class object, i = 33
I am Base class object, i = 45
```

我们可以通过使用指针或引用来避免上述意外行为。当指针或对对象的引用作为函数参数传递时，不会发生对象切片，因为任何类型的指针或引用都占用相同的内存。例如，如果我们将上面程序中的全局方法 myfunc()更改为 following，则不会发生对象切片。

## C++

```cpp
// rest of code is similar to above
void somefunc (Base &obj)
{
    obj.display();
}          
// rest of code is similar to above
```

输出:

```cpp
I am Base class object, i = 33
I am Derived class object, i = 45, j = 54
```

如果我们使用指针并将程序更改为如下，我们会得到相同的输出。

## C++

```cpp
// rest of code is similar to above
void somefunc (Base *objp)
{
    objp->display();
}

int main()
{
    Base *bp = new Base(33) ;
    Derived *dp = new Derived(45, 54);
    somefunc(bp);
    somefunc(dp);  // No Object Slicing
    return 0;
}
```

输出:

```cpp
I am Base class object, i = 33
I am Derived class object, i = 45, j = 54
```

通过禁止对象创建，使基类函数在那里成为纯虚函数，可以防止对象切片。不可能创建包含纯虚拟方法的类的对象。
本文由 **Pravasi Meet** 供稿。如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息