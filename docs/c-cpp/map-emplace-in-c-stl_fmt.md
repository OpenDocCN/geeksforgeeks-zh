# C++ STL

## map::emplace()

> 原文: [https://www.geeksforgeeks.org/map-emplace-in-c-stl/](https://www.geeksforgeeks.org/map-emplace-in-c-stl/)

`map::emplace()` 是 C++ STL 中的内置函数，它在 `map` 容器中插入键及其元素。它有效地将容器尺寸增加了一个。如果同一个键被放置多次，`map` 只存储第一个元素，因为 `map` 是一个不存储多个相同值的键的容器。

**语法:**

```cpp
map_name.emplace(key, element)
```

**参数:** 该函数接受两个强制参数，如下所述:

*   `Key` – 指定要插入到多重映射容器中的键。
*   `Element` – 指定要插入到 `map` 容器中的键所对应的元素。

**返回值:** 函数不返回任何内容。

```cpp
// C++ program for the illustration of
// map::emplace() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

// initialize container
    map<int, int> mp;

// insert elements in random order
    mp.emplace(2, 30);
    mp.emplace(1, 40);
    mp.emplace(2, 20);
    mp.emplace(1, 50);
    mp.emplace(4, 50);

// prints the elements
    cout << "\nThe map is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); itr++)
        cout << itr->first << "\t" << itr->second << endl;

return 0;
}
```

**输出:**

```cpp
The map is : 
KEY    ELEMENT
1    40
2    30
4    50
```