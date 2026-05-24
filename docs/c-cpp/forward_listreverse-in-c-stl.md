# c++ STL 中的 forward_list::reverse()

> 原文:[https://www.geeksforgeeks.org/forward_listreverse-in-c-stl/](https://www.geeksforgeeks.org/forward_listreverse-in-c-stl/)

**STD::forward_list::reverse()**是 CPP STL 中的一个内置函数，用于反转 forward _ list 中元素的顺序。

**语法:**

```cpp
forwardlist_name.reverse()
```

**参数:**函数不接受任何参数。

**返回值:**函数没有返回值。它反转正向列表。

下面的程序演示了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// reverse() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialising forward list
    forward_list<int> forward = { 10, 20, 40, 30, 70 };

    cout << "List elements before performing reverse operation: ";

    for (auto it = forward.begin(); it != forward.end(); ++ it)
        cout << *it << " ";

    // Function that performs reverse operation
    forward.reverse();

    // printing elements of list
    cout << "\nList elements after performing reverse operation: ";

    for (auto it = forward.begin(); it != forward.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**输出:**

```cpp
List elements before performing reverse operation: 10 20 40 30 70 
List elements after performing reverse operation: 70 30 40 20 10

```