# c++ 中初始化列表的执行顺序

> 原文:[https://www . geeksforgeeks . org/初始化器中的执行顺序-c 中的列表/](https://www.geeksforgeeks.org/order-of-execution-in-initializer-list-in-c/)

**先决条件:** [类](https://www.geeksforgeeks.org/c-classes-and-objects/)[构造函数](https://www.geeksforgeeks.org/constructors-c/)[初始化列表](https://www.geeksforgeeks.org/when-do-we-use-initializer-list-in-c/)

在本文中，我们将讨论 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中初始化列表的执行顺序。一般执行顺序是从上到下，从左到右。但是当这个规则失败时，一个罕见的情况出现了，那就是在课堂上使用[初始化列表](https://www.geeksforgeeks.org/when-do-we-use-initializer-list-in-c/)。在初始化列表中，执行的顺序根据成员变量的声明顺序而定。在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中使用类的初始化列表时，成员变量的声明顺序会影响程序的输出。

**程序 1:**

## c++

```cpp
// C++ program to illustrate the
// order of initializer in list
#include <iostream>
using namespace std;

class MyClass {
private:
    // Declared first
    int b;

    // Declared Second
    int a;

public:
    MyClass(int value)
        : b(value), a(b * 2)
    {
        cout << b << " " << a;
    }
};

// Driver Code
int main()
{
    // Create an object
    MyClass obj(10);

    return 0;
}
```

**输出:**

```cpp
10 20

```