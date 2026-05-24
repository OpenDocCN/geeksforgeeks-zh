# c++ 中的构造函数委托

> 原文:[https://www.geeksforgeeks.org/constructor-delegation-c/](https://www.geeksforgeeks.org/constructor-delegation-c/)

有时候[构造函数](https://www.geeksforgeeks.org/constructors-c/)能够调用同一个类的另一个构造函数是很有用的。这个名为**构造函数委托**的特性是在 C++ 11 中引入的。
**无委托示例程序:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// A C++ program to demonstrate need of
// constructor delegation.
#include <iostream>
using namespace std;

class A {
    int x, y, z;

public:
    A()
    {
        x = 0;
        y = 0;
        z = 0;
    }
    A(int z)
    {
        // The below two lines are redundant
        x = 0;
        y = 0;

        /* Only initialize z by passing an argument,
           while all the other arguments are
           initialized the same way they were,
           as in the previous constructor*/
        this->z = z;
    }

    void show()
    {
        cout << x << '\n'
             << y << '\n'
             << z;
    }
};

int main()
{
    A obj(3);
    obj.show();
    return 0;
}
```

**Output:** 

```cpp
0
0
3
```

**使用 init()**
解决上面的冗余代码问题我们可以在上面的例子中看到，上面的类的构造函数，尽管有不同的签名，但是它们之间有前两行代码是公共的，导致代码重复。避免这种情况的一个解决方案是创建一个 **init** 函数，该函数可以从两个构造函数中调用。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Program to demonstrate use of init() to
// avoid redundant code.
#include <iostream>
using namespace std;

class A {
    int x, y, z;

    // init function to initialize x and y
    void init()
    {
        x = 0;
        y = 0;
    }

public:
    A()
    {
        init();
        z = 0;
    }
    A(int z)
    {
        init();
        this->z = z;
    }

    void show()
    {
        cout << x << '\n'
             << y << '\n'
             << z;
    }
};

int main()
{
    A obj(3);
    obj.show();
    return 0;
}
```

**Output:** 

```cpp
0
0
3
```