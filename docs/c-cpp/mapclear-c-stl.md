# 地图::C++ STL 中的 clear()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/mapclear-c-STL/

[地图](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)是字典般的数据结构。它是(键、值)对的关联数组，其中只有单个值与每个唯一键相关联。

**map::clear()**
clear()函数用于移除地图容器中的所有元素，从而使其大小为 0。

**语法:**

```cpp
map1.clear()
where map1 is the name of the map.

Parameters:
No parameters are passed.

```

**返回值:**无

**示例:**

```cpp
Input : map1 = { 
                {1, "India"},
                {2, "Nepal"},
                {3, "Sri Lanka"},
                {4, "Myanmar"}
               }
 map1.clear();
Output: map1 = {}

Input : map2 = {}
 map2.clear();
Output: map2 = {}

```

```cpp
// CPP program to illustrate
// Implementation of clear() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Take any two maps
    map<int, string> map1, map2;

    // Inserting values
    map1[1] = "India";
    map1[2] = "Nepal";
    map1[3] = "Sri Lanka";
    map1[4] = "Myanmar";

    // Print the size of map
    cout<< "Map size before running function: \n";
    cout << "map1 size = " << map1.size() << endl;
    cout << "map2 size = " << map2.size() << endl;;

    // Deleting the map elements
    map1.clear();
    map2.clear();

    // Print the size of map
    cout<< "Map size after running function: \n";
    cout << "map1 size = " << map1.size() << endl;
    cout << "map2 size = " << map2.size();
    return 0;
}
```

输出:

```cpp
Map size before running function: 
map1 size = 4
map2 size = 0
Map size after running function: 
map1 size = 0
map2 size = 0

```

**时间复杂度:**线性即 O(n)