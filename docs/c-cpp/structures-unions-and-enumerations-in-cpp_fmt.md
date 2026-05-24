# C++ 中的结构、联合和枚举

> 原文: [https://www.geeksforgeeks.org/structures-unions-and-enumerations-in-cpp/](https://www.geeksforgeeks.org/structures-unions-and-enumerations-in-cpp/)

在本文中，我们将讨论结构、联合和枚举及其差异。

## 结构（Structures）

*   结构是一种用户定义的[数据类型](https://www.geeksforgeeks.org/c-data-types/)，可以在[C++](https://www.geeksforgeeks.org/c-plus-plus/)中使用。
*   结构用于组合不同类型的数据，就像[数组](https://www.geeksforgeeks.org/array-data-structure/)用于组合相同类型的数据一样。
*   使用[关键字](https://www.geeksforgeeks.org/variables-and-keywords-in-c/) `struct`来声明结构。在C语言中声明结构变量时，需要同时写出关键字`struct`和结构名，但在C++中这个关键字不是必需的。

**语法:**

```cpp
struct StructName {
   // 结构成员的声明
}
```

下面是演示如何使用`struct`的C++程序：

```cpp
// C++ program to demonstrate the
// making of structure
#include <bits/stdc++.h>
using namespace std;

// 定义结构
struct GFG {
    int G1;
    char G2;
    float G3;
};

// 驱动代码
int main()
{
    // 声明一个结构变量
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