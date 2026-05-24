# c++ 中函数重载的优缺点

> 原文:[https://www . geesforgeks . org/CPP 中函数重载的优缺点/](https://www.geeksforgeeks.org/advantages-and-disadvantages-of-function-overloading-in-cpp/)

[函数重载](https://www.geeksforgeeks.org/function-overloading-c/)是面向对象编程的重要特征之一。它允许用户拥有多个名称相同但属性不同的函数。重载函数使用户能够根据函数的签名为函数提供不同的语义。

**函数重载的优点如下:**

*   The main advantage of function overloading is to improve code readability and allow code reuse.
*   Function overloading is used to save memory space, consistency and readability.
*   It speeds up the execution of the program.
*   The maintenance of the code is also easy.
*   Function overloading brings flexibility to the code.
*   This function can perform different operations, so it eliminates the use of different function names for the same kind of operations.

**函数重载的缺点如下:**

*   Only function declarations with different return types cannot be overloaded.

插图:

```cpp
int fun();
float fun();
```

它会给出一个错误，因为函数不能仅通过返回类型重载。

*   Member function declarations with the same name and the same parameter type cannot be overloaded if any of them is a static member function declaration.
*   The main disadvantage of is that it requires the compiler to perform name management on function names to contain information about parameter types.

**示例:**

## c++

```cpp
// Importing input output stream files
#include <iostream>

using namespace std;

// Methods to print

// Method 1
void print(int i)
{

    // Print and display statement whenever
    // method 1 is called
    cout << " Here is int " << i << endl;
}

// Method 2
void print(double f)
{

    // Print and display statement whenever
    // method 2 is called
    cout << " Here is float " << f << endl;
}

// Method 3
void print(char const* c)
{

    // Print and display statement whenever
    // method 3 is called
    cout << " Here is char* " << c << endl;
}

// Method 4
// Main driver method
int main()
{

    // Calling method 1
    print(10);
    // Calling method 2
    print(10.10);
    // Calling method 3
    print("ten");

    return 0;
}
```

**输出**

```cpp
 Here is int 10
 Here is float 10.1
 Here is char* ten
```

**输出说明:**

在上面的例子中，所有被命名为 3 的函数都是相同的，但是打印不同，我们可以感觉到对它们进行了不同的调用。这是可能的，因为传递了参数，根据这些参数执行函数调用，而不管这些函数是否共享一个公共名称。此外，请记住，我们可以通过在返回类型中更改它们的签名来重载函数。例如，这里布尔 print()函数可以对它们三个都调用。