# c++ STL 中的 multimap maxsize()

> 原文:[https://www.geeksforgeeks.org/multimap-maxsize-in-c-stl/](https://www.geeksforgeeks.org/multimap-maxsize-in-c-stl/)

**multimap::max_size()** 是 C++ STL 中的内置函数，返回 multimap 容器可以容纳的最大元素数量。

**语法:**

```cpp
multimap_name.max_size()

```

**参数:**此功能不接受任何参数。

**返回值:**该函数返回列表容器可以容纳的最大元素数量。

## c++

```cpp
// C++ program to illustrate
// multimap::max_size()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    multimap<int, int> mp1, mp2;

    cout << "The max size of mp1 is " << mp1.max_size();
    cout << "\nThe max size of mp2 is " << mp2.max_size();
    return 0;
}
```

**输出:**

```cpp
The max size of mp1 is 461168601842738790
The max size of mp2 is 461168601842738790

```