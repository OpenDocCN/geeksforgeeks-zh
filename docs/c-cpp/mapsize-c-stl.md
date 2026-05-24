# 地图::大小()在 C++ STL 中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/map ize-c-STL/

贴图是以贴图方式存储元素的关联容器。每个元素都有一个键值和一个映射值。没有两个映射值可以具有相同的键值。

**地图::size()**
在 C++ 中， **size()** 函数用于返回地图中存在的元素总数。

**语法:**

```cpp
map_name.size()

```

**返回值:**返回地图中存在的元素数量。

**示例:**

```cpp
Input : map1 = { 
                {1, "India"},
                {2, "Nepal"},
                {3, "Sri Lanka"},
                {4, "Myanmar"}
               }
        map1.size();
Output: 4

Input : map2 = {};
 map2.size();
Output: 0

```

```cpp
// C++ program to illustrate
// implementation of size() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Take any two maps
    map<int, string> map1, map2;

    // Inserting values
    map1.insert(make_pair(1, "India"));
    map1.insert(make_pair(2, "Nepal"));
    map1.insert(make_pair(3, "Sri Lanka"));
    map1.insert(make_pair(4, "Myanmar"));

    // Printing the size
    cout << "map1 size: " << map1.size();
    cout << endl;
    cout << "map2 size: " << map2.size();
    return 0;
}
```

输出:

```cpp
map1 size: 4
map2 size: 0

```

**时间复杂度:**常数，即 O(1)