# c++ STL 中的 forward_list::max_size()

> 原文:[https://www . geesforgeks . org/forward _ listmax _ size-in-c-STL/](https://www.geeksforgeeks.org/forward_listmax_size-in-c-stl/)

**STD::forward_list::max _ size()**是 CPP STL 中的一个内置函数，返回 forward _ list 可以容纳的最大元素数。该值取决于系统或库实现。

**语法:**

```cpp
forwardlist_name.max_size ()

```

**参数:**函数不接受任何参数。

**返回值:**该函数返回可以存储到 forward_list 中的最大数量。

下面程序演示了上面的功能:

```cpp
// C++ program to illustrate the
// max_size() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialising the forward list
    forward_list<int> f;

    // print max number of values that 
    // can be held by forward_list
    cout << "Max_size of the list is " 
    << f.max_size() << endl;

    return 0;
}
```

**输出:**

```cpp
Max_size of the list is 1152921504606846975

```