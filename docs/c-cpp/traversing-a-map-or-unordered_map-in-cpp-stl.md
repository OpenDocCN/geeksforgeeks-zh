# 在 C++ STL 中遍历一个地图(或无序地图)

> 原文:[https://www . geeksforgeeks . org/遍历-a-map-or-无序 _map-in-cpp-stl/](https://www.geeksforgeeks.org/traversing-a-map-or-unordered_map-in-cpp-stl/)

我们可以使用以下不同方式遍历[地图](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)和[无序 _ 地图](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/)。

**使用** [**范围为循环基础**](https://www.geeksforgeeks.org/range-based-loop-c/)

## 地图

```cpp
// CPP program to traverse a map using range
// based for loop
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int arr[] = { 1, 1, 2, 1, 1, 3, 4, 3 };
    int n = sizeof(arr) / sizeof(arr[0]);

    map<int, int> m;
    for (int i = 0; i < n; i++)
        m[arr[i]]++ ;

    cout << "Element  Frequency" << endl;
    for (auto i : m)
        cout << i.first << "   " << i.second
             << endl;

    return 0;
}
```

## 无序地图

```cpp
// CPP program to traverse a unordered_map using
// range based for loop
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int arr[] = { 1, 1, 2, 1, 1, 3, 4, 3 };
    int n = sizeof(arr) / sizeof(arr[0]);

    unordered_map<int, int> m;
    for (int i = 0; i < n; i++)
        m[arr[i]]++ ;

    cout << "Element Frequency" << endl;
    for (auto i : m)
        cout << i.first << "    " << i.second
             << endl;

    return 0;
}
```

**Output**

```cpp
Element  Frequency
1   4
2   1
3   2
4   1

```