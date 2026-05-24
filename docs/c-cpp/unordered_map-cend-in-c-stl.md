# c++ STL 中的无序 _ 映射 cend

> 原文:[https://www.geeksforgeeks.org/unordered_map-cend-in-c-stl/](https://www.geeksforgeeks.org/unordered_map-cend-in-c-stl/)

**无序 _map::cend()** 是 C++ STL 中的一个内置函数，它返回一个迭代器，该迭代器指向容器或其一个桶中结束元素的位置。在无序映射对象中，不能保证哪个特定元素被认为是它的第一个元素。但是容器中的所有元素都被覆盖了，因为范围从它的开始到它的结束一直到无效。

这个函数有两种变体。
**语法-1:**

```cpp
unordered_map.cend()

```

**参数:**此功能不接受任何参数。
**返回类型:**这个函数返回一个迭代器到容器末尾的元素。

```cpp
// CPP program to illustrate
// unordered_map cend()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    unordered_map<int, int> ump;

    // inserting data into unordered_map
    ump[1] = 2;
    ump[3] = 4;
    ump[5] = 6;

    // here 'it' can not be modified
    for (auto it = ump.cbegin(); it != ump.cend(); ++ it)
        cout << it->first << " " << it->second << endl;
    return 0;
}
```

**Output:**

```cpp
5 6
1 2
3 4

```