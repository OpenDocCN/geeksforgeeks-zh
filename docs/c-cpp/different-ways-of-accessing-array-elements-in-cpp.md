# c++ 中访问数组元素的不同方式

> 原文:[https://www . geesforgeks . org/不同的访问方式-cpp 中的数组元素/](https://www.geeksforgeeks.org/different-ways-of-accessing-array-elements-in-cpp/)

在本文中，下面将讨论从[数组](https://www.geeksforgeeks.org/array-data-structure/)而不是传统的**arr【I】**表达式中访问元素的两种独特且不同的方式。

*   Use [pointer](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/) *** (arr+1)**
*   Use the small operation **I [arr]** to use the array and the reasons behind it.

编译 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 程序时，同时生成[符号表](https://www.geeksforgeeks.org/symbol-table-compiler/)。它的形成是为了存储程序中使用的所有变量的地址的相应值。

让我们考虑一个 C++ 程序，看看对应程序的符号表会是什么:

## c++

```cpp
// C++ program for the above concepts

#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Assigning a value to a
    int a = 5;

    // Printing the value of a
    cout << "Value of a: " << a;

    // Printing the address of a
    cout << "\nAddress of a: " << &a;

    return 0;
}
```

**输出:**

```cpp
Value of a: 5
Address of a: 0x7ffe25768fa4
```