# c++ STL 中的无序 _ 映射大小()

> 原文:[https://www.geeksforgeeks.org/unordered_map-size-in-c-stl/](https://www.geeksforgeeks.org/unordered_map-size-in-c-stl/)

**无序 _ 多映射::size()** 是 C++ 标准模板库中的一个内置函数，它返回无序映射中元素的数量。

**语法**:

```cpp
unordered_multimap_name.size()
```

**返回值**:返回无序地图中元素的个数。

**时间复杂度:**

```cpp
Constant i.e. O(1).
```

**程序 1:**

```cpp
// C++ program to demonstrate
// unordered_map size() method

#include <iostream>
#include <unordered_map>
using namespace std;

int main()
{
    unordered_map<char, char>
        n{ { 'A', 'G' },
           { 'B', 'E' },
           { 'C', 'E' },
           { 'D', 'K' },
           { 'E', 'S' } };

    cout << "size of map = "
         << n.size() << endl;

    return 0;
}
```

**Output:**

```cpp
size of map = 5

```

**程序 2:**

```cpp
// C++ program to demonstrate
// unordered_map size() method

#include <iostream>
#include <string>
#include <unordered_map>
using namespace std;

int main()
{
    unordered_map<string, double> ra;

    cout << "Initial size of map = "
         << ra.size() << endl;

    ra = {
        { "Geeks", 1.556 },
        { "For", 2.567 },
        { "Geeks", 3.345 },
        { "GeeksForGeeks", 4.789 },
        { "GFG", 5.998 }
    };

    cout << "size of map = "
         << ra.size() << endl;

    return 0;
}
```

**Output:**

```cpp
Initial size of map = 0
size of map = 4

```