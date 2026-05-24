# 在 C++ STL 中映射 rbegin()函数

> 原文:[https://www . geesforgeks . org/map-rbe gin-function-in-c-STL-2/](https://www.geeksforgeeks.org/map-rbegin-function-in-c-stl-2/)

**std::map::rbegin()** 是 C++ STL 中的一个函数。它返回一个反向迭代器，指向映射的最后一个元素。反向迭代器以相反的顺序迭代，递增意味着向映射的开始移动。

**语法:**

```cpp
r_i rbegin();
const_r_i rbegin() const;
```

**参数:**不除任何参数。

**返回:**返回一个反向迭代器，指向地图的最后一个元素。

**时间复杂度:** O(1)

以下示例说明了 map::rbegin()方法:

**例 1:**

```cpp
// C++ Program to illustrate
// map::rbegin() method

#include <iostream>
#include <map>
using namespace std;

int main()
{

    map<char, int> mp = {
        { 'a', 1 },
        { 'b', 2 },
        { 'c', 3 },
        { 'd', 4 },
        { 'e', 5 },
    };

    cout << "Map contains following "
         << "elements in reverse order"
         << endl;

    for (auto i = mp.rbegin(); i != mp.rend(); ++ i)
        cout << i->first
             << " = " << i->second
             << endl;

    return 0;
}
```

**Output:**

```cpp
Map contains following elements in reverse order
e = 5
d = 4
c = 3
b = 2
a = 1

```

**例 2:**

```cpp
// C++ Program to illustrate
// map::rbegin() method

#include <iostream>
#include <map>
using namespace std;

int main()
{

    map<char, char> mp = {
        { 'a', 'A' },
        { 'b', 'B' },
        { 'c', 'C' },
        { 'd', 'D' },
        { 'e', 'E' },
    };

    cout << "Map contains following "
         << "elements in reverse order"
         << endl;

    for (auto i = mp.rbegin(); i != mp.rend(); ++ i)
        cout << i->first
             << " = " << i->second
             << endl;

    return 0;
}
```

**Output:**

```cpp
Map contains following elements in reverse order
e = E
d = D
c = C
b = B
a = A

```