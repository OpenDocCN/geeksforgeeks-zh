# c++ 中内联函数和普通函数的区别

> 原文:[https://www . geesforgeks . org/内联函数和普通函数的区别/CPP/](https://www.geeksforgeeks.org/difference-between-inline-and-normal-function-in-cpp/)

[**【内联函数】**](https://www.geeksforgeeks.org/inline-functions-cpp/) 是编译器在调用时内联展开的函数。在函数调用期间，会执行许多开销任务，如保存寄存器、将参数推送到堆栈以及返回调用函数。这些开销对于小型功能来说既耗时又低效。在 C++ 中，内联函数用于解决这些开销。调用时由编译器进行行内扩展，避免了开销成本。在函数声明之前使用了一个名为“*内联***”**的关键字。

**语法:**

```cpp
inline return_type function_name(parameters) 
{
// Insert your Function code here
}
```

**示例:**

## c++

```cpp
// C++ program to demonstrate inline function

// Importing input output stream files
#include <iostream>

using namespace std;

// Method 1
// Inline function
// To multiply two integer numbers
inline int multiplication(int x, int y)
{

    // Returning the producus of two numbers
    return x * y;
}

// Method 2
// Main driver method/function
// Execution begins here
int main()
{
    // Print and display the multiplication resultant number
    // with usage of above created multiplication() inline()
    cout << "Multiplication ( 20 , 30 ):"
         << multiplication(20, 30) << endl;

    return 0;
}
```

**输出**

```cpp
Multiplication ( 20 , 30 ):600
```