# 在 C++ STL 中映射 max_size()

> 原文:[https://www.geeksforgeeks.org/map-max_size-in-c-stl/](https://www.geeksforgeeks.org/map-max_size-in-c-stl/)

**map::max_size()** 是 C++ STL 中的内置函数，返回一个 map 容器可以容纳的最大元素数。

**语法:**

```cpp
map_name.max_size()
```

**参数:**此功能不接受任何参数。

**返回值:**该函数返回地图容器可以容纳的最大元素数量。

```cpp
// C++ program to illustrate
// map::max_size()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    map<int, int> mp1, mp2;
    mp1.insert({ 1, 2 });

    // max size of Non-empty map
    cout << "The max size of mp1 is " << mp1.max_size();

    // max size of Empty-map
    cout << "\nThe max size of mp2 is " << mp2.max_size();
    return 0;
}
```

**输出:**

```cpp
The max size of mp1 is 461168601842738790
The max size of mp2 is 461168601842738790

```