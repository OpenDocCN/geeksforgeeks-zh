# c++ 中的结构、并集和枚举

> 原文:[https://www . geesforgeks . org/structures-unions-and-enumerations-in-CPP/](https://www.geeksforgeeks.org/structures-unions-and-enumerations-in-cpp/)

在本文中，我们将讨论结构、联合和枚举及其差异。

*   This structure is a user-defined [data type](https://www.geeksforgeeks.org/c-data-types/) , which can be obtained in [C++ ](https://www.geeksforgeeks.org/c-plus-plus/).
*   Structures are used to combine different types of data types, just as [array](https://www.geeksforgeeks.org/array-data-structure/) is used to combine data types of the same type.
*   Use the [keyword](https://www.geeksforgeeks.org/variables-and-keywords-in-c/) " **structure** to declare the structure. When we declare a variable of the structure, we need to write [keyword](https://www.geeksforgeeks.org/variables-and-keywords-in-c/) and **structure** in C language, but this keyword is not mandatory for C++.

**语法:**

```cpp
struct 
{
   // Declaration of the struct
}
```

下面是 C++ 程序演示 struct 的使用:

## c++

```cpp
// C++ program to demonstrate the
// making of structure
#include <bits/stdc++.h>
using namespace std;

// Define structure
struct GFG {
    int G1;
    char G2;
    float G3;
};

// Driver Code
int main()
{
    // Declaring a Structure
    struct GFG Geek;
    Geek.G1 = 85;
    Geek.G2 = 'G';
    Geek.G3 = 989.45;
    cout << "The value is : "
         << Geek.G1 << endl;
    cout << "The value is : "
         << Geek.G2 << endl;
    cout << "The value is : "
         << Geek.G3 << endl;

    return 0;
}
```

**输出:**

```cpp
The value is : 85
The value is : G
The value is : 989.45
```