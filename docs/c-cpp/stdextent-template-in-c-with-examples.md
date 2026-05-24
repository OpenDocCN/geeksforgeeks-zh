# 标准::范围()C++ 模板，带示例

> 原文:[https://www . geeksforgeeks . org/STD extend-template-in-c-with-examples/](https://www.geeksforgeeks.org/stdextent-template-in-c-with-examples/)

[C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的 **std::is_const** 模板存在于**<**type _ traits**>**头文件中。如果 A 是秩大于 B 的数组，则范围是 Ath 维度的界限，如果 B 为零，并且 A 是未知界限的数组，则范围值为零。

**头文件:**

```cpp
#include<type_traits>

```

**语法:**

```cpp
template 
  <class A, unsigned B = 0>
  struct extent;

```

**参数:**接受以下参数:

*   **A** :代表一种特定的类型。
*   **B** :表示要获取范围的尺寸。

以下是演示 STD::extend()的程序:

**程序 1:**

```cpp
// C++ program to demonstrate
// std::extent()

#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{
    // By default dimension is zero
    cout << extent<int[3]>::value << endl;
    cout << extent<int[3][4], 0>::value << endl;
    cout << extent<int[3][4], 1>::value << endl;
    cout << extent<int[3][4], 2>::value << endl;
    cout << extent<int[]>::value << endl;

    const int ints[] = { 1, 2, 3, 4 };

    // Used to print the size of array
    cout << extent<decltype(ints)>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
3
3
4
0
0
4

```

**程序二:**

```cpp
// C++ program to demonstrate
// std::extent()

#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{
    typedef int gfg[][50][70];
    cout << "gfg array (int[][50][70]):" << endl;
    cout << "rank: " << rank<gfg>::value << endl;
    cout << extent<gfg, 0>::value << endl;
    cout << extent<gfg, 1>::value << endl;
    cout << extent<gfg, 2>::value << endl;
    cout << extent<gfg, 3>::value << endl;
    return 0;
}
```

**输出:**

```cpp
gfg array (int[][50][70]):
rank: 3
0
50
70
0

```

**参考:**T2】http://www.cplusplus.com/reference/type_traits/extent/