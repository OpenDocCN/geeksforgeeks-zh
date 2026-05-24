# c++ 中的 basic_istream::swap()，示例

> 原文:[https://www . geesforgeks . org/basic _ is tream swap-in-c-with-examples/](https://www.geeksforgeeks.org/basic_istreamswap-in-c-with-examples/)

**basic_ios::swap(x)** 用于交换基类中除 **rdbuf()** 以外的所有数据成员，并在*this 和 x 之间交换 gcount()计数器的值。这个 basic_ios::swap(x)函数是一个受保护的函数。下面是其语法和头文件:

**头文件:**

```cpp
#include<iostream>

```

**语法:**

```cpp
void swap (basic_istream& x);

```

**参数:**接受以下参数:

*   **x** :表示参数相同的另一个对象。

**返回值:**方法 **basic_istream::get()** 不返回任何内容。

下面是演示 **basic_istream::swap():** 的程序

**程序 1:**

```cpp
// C++ program to demonstrate
// basic_istream::swap()

#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    // Input String gfg1
    istringstream gfg1("Welcome");

    // Input String gfg2
    istringstream gfg2("Geeks");

    // swap function for swapping
    // both the strings
    swap(gfg1, gfg2);
    cout << gfg1.rdbuf() << " "
         << gfg2.rdbuf() << endl;

    return 0;
}
```

**输出:**

```cpp
Geeks Welcome

```

**程序二:**

```cpp
// C++ program to demonstrate
// basic_istream::swap()

#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    // Input String gfg1
    istringstream gfg1("forGeeks");

    // Input String gfg2
    istringstream gfg2("Geeks");

    // swap function for swapping
    // both the strings
    gfg1.swap(gfg2);
    cout << gfg1.rdbuf() << " "
         << gfg2.rdbuf() << endl;

    return 0;
}
```

**输出:**

```cpp
Geeks forGeeks

```

**参考:**T2【http://www . cplusplus . com/Reference/is tream/basic _ is tream/swap/