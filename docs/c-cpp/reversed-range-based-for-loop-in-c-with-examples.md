# 基于反向范围的 C++ 循环示例

> 原文:[https://www . geeksforgeeks . org/基于反向范围的 c-in-loop-in-examples/](https://www.geeksforgeeks.org/reversed-range-based-for-loop-in-c-with-examples/)

**[基于范围的循环](https://www.geeksforgeeks.org/range-based-loop-c/)** 是循环[的升级版本。](https://www.geeksforgeeks.org/loops-in-c-and-cpp/)它与 Python 中使用的 for 循环非常相似。 [C++ 中基于范围的循环](https://www.geeksforgeeks.org/c-plus-plus/)是从 C++ 11 开始增加的。

我们可以使用 **boost 库头**中包含的**boost::adapters::reverse()**函数来反转循环迭代的过程。

**头文件:**

```cpp
#include <boost/range/adaptor/reversed.hpp> 

```

**语法:**

```cpp
for (auto i : boost::adaptors::reverse(x))

```

**参数:**

*   **range_declaration:** 用于迭代[容器](https://www.geeksforgeeks.org/containers-cpp-stl/)中元素的声明。通常使用自动说明符进行自动类型推导。
*   **range_expression:** 表示合适序列或支撑初始化列表的表达式。
*   **loop_statement:** 一个语句，通常是一个复合语句，它是循环的主体。

下面是用 C++ 说明反向范围循环的程序:

## CPP14

```cpp
// C++ program for reverse
// range-based for loop
#include <bits/stdc++.h>

// For reversing range based loop
#include <boost/range/adaptor/reversed.hpp>
using namespace std;

// Driver Code
int main()
{
    string s = "geeksforgeeks";

    int y[] = { 1, 2, 3, 4, 5, 6, 7, 8 };

    vector<int> v1{ 1, 2, 3, 4, 5, 6, 7, 8 };

    // Reverse range-based for loop
    // to reverse string
    for (auto x : boost::adaptors::reverse(s))
        cout << x << " ";
    cout << endl;

    // Reverse range-based for loop
    // to reverse array
    for (auto x : boost::adaptors::reverse(y))
        cout << x << " ";
    cout << endl;

    // Reverse range-based for loop
    // to reverse vector
    for (auto x : boost::adaptors::reverse(v1))
        cout << x << " ";
    cout << endl;

    return 0;
}
```

**Output:**

```cpp
s k e e g r o f s k e e g 
8 7 6 5 4 3 2 1 
8 7 6 5 4 3 2 1

```