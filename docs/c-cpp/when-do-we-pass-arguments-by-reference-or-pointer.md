# 我们什么时候通过引用或者指针传递参数？

> 原文:[https://www . geesforgeks . org/when-do-we-pass-arguments-by-reference-or-pointer/](https://www.geeksforgeeks.org/when-do-we-pass-arguments-by-reference-or-pointer/)

在 C++ 中，变量是通过引用传递的，原因如下:
**1)** ***要修改调用者函数的局部变量:*** 引用(或指针)允许被调用的函数修改调用者函数的局部变量。例如，考虑以下示例程序，其中 *fun()* 能够修改 *main()* 的局部变量 *x* 。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <bits/stdc++.h>
using namespace std;

void fun(int& x) { x = 20; }

int main()
{
    int x = 10;
    fun(x);
    cout << "New value of x is " << x;
    return 0;
}
```

输出:
x 的新值为 20

**2)** ***对于传递大尺寸的参数:*** 如果一个参数很大，通过引用(或指针)传递效率更高，因为真正传递的只是一个地址，而不是整个对象。例如，让我们考虑下面的*雇员*类和一个打印雇员详细信息的函数 *printEmpDetails()* 。

## C

```cpp
class Employee {
private:
    string name;
    string desig;

    // More attributes and operations
};

void printEmpDetails(Employee emp)
{
    cout << emp.getName();
    cout << emp.getDesig();

    // Print more attributes
}
```

上面代码的问题是:每次调用 *printEmpDetails()* 时，都会构造一个新的 Employee 对象，该对象涉及创建所有数据成员的副本。因此，更好的实现方式是将 Employee 作为参考。

## C

```cpp
void printEmpDetails(const Employee& emp)
{
    cout << emp.getName();
    cout << emp.getDesig();

    // Print more attributes
}
```

这一点只对结构和类变量有效，因为我们对像 int、char 这样的基本类型没有任何效率优势..等等。

**3)** ***避免对象切片:*** 如果我们将子类的对象传递给一个期望超类对象的函数，那么传递的对象如果是按值传递的，那么就是[切片的](http://en.wikipedia.org/wiki/Object_slicing)。例如，考虑以下程序，它打印“这是宠物类”。

## C

```cpp
#include <iostream>
#include <string>

using namespace std;

class Pet {
public:
    virtual string getDescription() const
    {
        return "This is Pet class";
    }
};

class Dog : public Pet {
public:
    virtual string getDescription() const
    {
        return "This is Dog class";
    }
};

void describe(Pet p)
{ // Slices the derived class object
    cout << p.getDescription() << endl;
}

int main()
{
    Dog d;
    describe(d);
    return 0;
}
```

输出:
这是宠物类
如果我们在上面的程序中使用了按引用传递，那么它会正确打印“这是狗类”。参见以下修改后的程序。

## C++

```cpp
#include <iostream>
#include <string>

using namespace std;

class Pet {
public:
    virtual string getDescription() const
    {
        return "This is Pet class";
    }
};

class Dog : public Pet {
public:
    virtual string getDescription() const
    {
        return "This is Dog class";
    }
};

void describe(const Pet& p)
{ // Doesn't slice the derived class object.
    cout << p.getDescription() << endl;
}

int main()
{
    Dog d;
    describe(d);
    return 0;
}
```

输出:
这是 Dog 类
这一点对于 int，char，..等等。

**4)** ***要在函数中实现运行时多态***
我们可以通过将对象作为引用(或指针)传递给函数来使函数多态。例如，在下面的程序中，print()接收对基类对象的引用。如果传递基类对象，print()调用基类函数 show()，如果传递派生类对象，则调用派生类函数 show()。

## C++

```cpp
#include <iostream>
using namespace std;

class base {
public:
    virtual void show()
    { // Note the virtual keyword here
        cout << "In base \n";
    }
};

class derived : public base {
public:
    void show() { cout << "In derived \n"; }
};

// Since we pass b as reference, we achieve run time
// polymorphism here.
void print(base& b) { b.show(); }

int main(void)
{
    base b;
    derived d;
    print(b);
    print(d);
    return 0;
}
```

输出:
在基地
在衍生
感谢[文基](https://www.geeksforgeeks.org/forums/users/venki/)加了这个点。
作为补充说明，如果引用参数仅由于上述原因 2 或 3 而被引用通过，建议将它们设为常量。建议这样做以避免对对象进行意外修改。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。