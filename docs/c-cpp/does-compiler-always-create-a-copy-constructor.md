# 编译器什么时候在 C++ 中创建和复制默认构造函数？

> 原文:[https://www . geesforgeks . org/do-编译器-总是-创建-复制-构造器/](https://www.geeksforgeeks.org/does-compiler-always-create-a-copy-constructor/)

在 C++ 中，如果我们不定义自己的构造函数，编译器会创建一个[默认构造函数](http://en.wikipedia.org/wiki/Default_constructor)(参见[这个](https://www.geeksforgeeks.org/g-fact-26/))。编译器创建的默认构造函数体为空，即不为数据成员赋予默认值([在 java 中，默认构造函数赋予默认值](https://www.geeksforgeeks.org/g-fact-50/))。

如果我们不编写自己的复制构造函数，编译器也会创建一个复制构造函数。与默认构造函数不同，编译器创建的复制构造函数的主体不是空的，它将传递对象的所有数据成员复制到正在创建的对象。

***当我们只编写一个复制构造函数时会发生什么——编译器会创建默认构造函数吗？***
如果我们编写任何构造函数，编译器不会创建默认构造函数，即使它是复制构造函数。例如，下面的程序不编译。

```cpp
#include <iostream>
using namespace std;

class Point
{
    int x, y;
public:
   Point(const Point &p) { x = p.x; y = p.y; }
};

int main()
{
    Point p1;  // COMPILER ERROR
    Point p2 = p1;
    return 0;
}
```

输出:

```cpp
COMPILER ERROR: no matching function for call to 'Point::Point()

```

***那么逆向呢——我们写一个普通的构造函数，不写复制构造函数会怎么样？***
颠倒不正。如果我们不自己编写，编译器会创建一个复制构造函数。即使我们在类中编写了其他构造函数，编译器也会创建它。例如，下面的程序运行良好。

```cpp
#include <iostream>
using namespace std;

class Point
{
    int x, y;
public:
   Point(int i, int j) { x = 10; y = 20; }
   int getX() { return x; }
   int getY() { return y; }
};

int main()
{
    Point p1(10, 20);
    Point p2 = p1; // This compiles fine
    cout << "x = " << p2.getX() << " y = " << p2.getY();
    return 0;
}
```

输出:

```cpp
x = 10 y = 20
```

因此，只有当我们有指针或运行时资源分配(如文件句柄、网络连接等)时，我们才需要编写复制构造函数(参见[这个](https://www.geeksforgeeks.org/g-fact-22/))

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论