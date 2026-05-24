# c++ STL 中的 multimap size()函数

> 原文:[https://www . geesforgeks . org/multimap-size-function-in-c-STL/](https://www.geeksforgeeks.org/multimap-size-function-in-c-stl/)

**multimap::size()** 是 C++ STL 中的内置函数，返回 multimap 容器中的元素个数。

**语法:**

```cpp
multimap_name.size()
```

**参数:**函数不接受任何参数。

**返回值:**这个函数返回一个多映射容器的元素数量。

```cpp
// C++ function for illustration
// multimap::size() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    multimap<int, int> mp;

    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 2, 60 });
    mp.insert({ 2, 20 });
    mp.insert({ 1, 50 });
    mp.insert({ 4, 50 });

    cout << "multimap mp has " << mp.size()
         << " number of elements";
    return 0;
}
```

**输出:**

```cpp
multimap mp has 6 number of elements

```