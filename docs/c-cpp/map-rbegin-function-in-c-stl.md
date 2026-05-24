# 在 C++ STL 中映射 rbegin()函数

> 原文:[https://www.geeksforgeeks.org/map-rbegin-function-in-c-stl/](https://www.geeksforgeeks.org/map-rbegin-function-in-c-stl/)

**rbegin()** 是 C++ STL 中的一个函数。它返回一个反向迭代器，指向映射的最后一个元素。反向迭代器以相反的顺序迭代，递增意味着向映射的开始移动。

**语法:**

```cpp
r_i rbegin();
const_r_i rbegin() const;

```

**参数:**
不排除任何参数。

**返回值:**这个方法向序列容器的反向开始抛出一个反向迭代器。

**时间复杂度:**

```cpp
O(1)
```

**示例:**

```cpp
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

    cout << "Map contains "
         << "following elements in"
         << " reverse order"
         << endl;

    for (auto i = mp.rbegin(); i != mp.rend(); ++ i) {

        cout << i->first
             << " = "
             << i->second
             << endl;
    }

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