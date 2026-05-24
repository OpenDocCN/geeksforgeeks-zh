# c++ STL 中的 map rend()函数

> 原文:[https://www.geeksforgeeks.org/map-rend-function-in-c-stl/](https://www.geeksforgeeks.org/map-rend-function-in-c-stl/)

**rend()** 函数是 C++ STL 中的一个内置函数，它返回一个反向迭代器，指向映射中第一个键值对之前的理论元素(这被认为是它的反向结束)。

**语法:**

```cpp
map_name.rend()
```

**参数:**函数不取任何参数。

**返回值:**函数返回一个**反向迭代器**，指向地图中第一个元素前的理论元素。

**注意:**反向迭代器向后迭代，即当它们增加时，它们向容器的开头移动。

以下程序说明了该功能。

**程序 1:**

```cpp
// C++ program to illustrate map::rend() function

#include <iostream>
#include <map>
using namespace std;

int main()
{
    map<char, int> mymap;

    // Insert pairs in the multimap
    mymap.insert(make_pair('a', 1));
    mymap.insert(make_pair('b', 3));
    mymap.insert(make_pair('c', 5));

    // Show content
    for (auto it = mymap.rbegin(); it != mymap.rend(); it++) {

        cout << it->first
             << " = "
             << it->second
             << endl;
    }

    return 0;
}
```

**Output:**

```cpp
c = 5
b = 3
a = 1

```

**程序 2:**

```cpp
// C++ program to illustrate map::rend() function

#include <iostream>
#include <map>
using namespace std;

int main()
{

    map<char, int> mymap;

    // Insert pairs in the multimap
    mymap.insert(make_pair('a', 1));
    mymap.insert(make_pair('b', 3));
    mymap.insert(make_pair('c', 5));

    // Get the iterator pointing to
    // the preceding position of
    // 1st element of the map
    auto it = mymap.rend();

    // Get the iterator pointing to
    // the 1st element of the multimap
    it--;

    cout << it->first
         << " = "
         << it->second;

    return 0;
}
```

**Output:**

```cpp
a = 1

```