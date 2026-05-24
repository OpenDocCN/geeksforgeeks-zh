# c++ STL 中的无序 _ 映射查找

> 原文:[https://www.geeksforgeeks.org/unordered_map-find-in-c-stl/](https://www.geeksforgeeks.org/unordered_map-find-in-c-stl/)

**c++ 中的 find** 函数用于在无序的地图中搜索特定的键。

**语法**

```cpp
unordered_map.find(key);
```

**参数:**它以键为参数。

**返回值:**如果给定的键存在于无序映射中，它将向该元素返回一个迭代器，否则它将返回映射迭代器的末尾。

下面程序说明**查找**功能的工作:

```cpp
// CPP program to demonstrate implementation of
// find function in unordered_map.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    unordered_map<int, bool> um;

    um[12] = true;
    um[6789] = false;
    um[456] = true;

    // Searching for element 23
    if (um.find(23) == um.end())
        cout << "Element Not Present\n";
    else
        cout << "Element Present\n";

    // Searching for element 12
    if (um.find(12) == um.end())
        cout << "Element Not Present\n";
    else
        cout << "Element Present\n";

    return 0;
}
```

**输出:**

```cpp
Element Not Present
Element Present

```

时间复杂度:平均为 0(1)。