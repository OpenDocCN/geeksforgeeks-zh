# c++ 中单参数构造函数的问题及解决方法

> 原文:[https://www . geeksforgeeks . org/单参数构造函数问题及其解决方法/](https://www.geeksforgeeks.org/problem-with-single-argument-constructor-in-c-and-how-to-solve-it/)

在 C++ 中，如果一个类有一个可以用单个参数调用的构造函数，那么这个构造函数就变成了一个转换构造函数，因为这样的构造函数允许自动转换到被构造的类。

**问题:**
每当有一个具有单个参数的构造函数，并且有一个函数采用相同类类型的参数，但是当使用与构造函数相同的参数类型调用该函数时，在这种情况下，该函数被成功调用。这是因为构造函数将参数隐式转换为类类型。参数被传递给构造函数，然后函数被执行。这是我们无法预料的。

下面是演示上述问题的 C++ 程序:

## C++

```cpp
// C++ program to implement
// the above approach
#include <iostream>
using namespace std;

// Defining the class
class GfG {
    int data;

public:
    // Constructor with single parameter
    GfG(int a)
        : data(a)
    {
    }

    // Default constructor
    GfG() {}

    // Defining function to print
    // the value of data member
    void display()
    {
        cout << "Value of data is: " << data;
    }
};

// User-defined function that takes
// object of class GfG as argument
void func(GfG o)
{
    o.display();
}

// Driver code
int main()
{
    int var = 10;

    // Function gets called even if
    // int type argument is passed
    func(var);
}
```

**Output**

```cpp
Value of data is: 10
```