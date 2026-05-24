# c++ STL 中的无序 _ 地图侵位()

> 原文:[https://www . geesforgeks . org/unordered _ map-侵位-in-c-stl/](https://www.geeksforgeeks.org/unordered_map-emplace-in-c-stl/)

**无序 _map::炮位()**是 C++ STL 中的内置函数，它将键及其元素插入无序 _map 容器中。它有效地将容器尺寸增加了一个。如果同一个键被放置多次，地图只存储第一个元素，因为地图是一个不存储多个相同值的键的容器。

**与[无序 _ 映射 insert()有何不同？](https://www.geeksforgeeks.org/unordered_map-insert-in-c-stl/)**
炮台的优势在于，它做原地插入，避免了不必要的物体复制。对于原始数据类型，我们使用哪一种并不重要。详见[本](https://www.geeksforgeeks.org/emplace-vs-insert-c-stl/)。

**语法:**

```cpp
unordered_map_name.emplace(key, element)

```

**参数:**该功能接受两个强制参数，如下所述:

*   **键–**指定要插入多映射容器的键。
*   **元素–**指定要插入到地图容器中的键的元素。

**返回值**:返回一对迭代器和一个 bool。如果元素已经存在，它返回一个指向已经插入的元素的迭代器，如果元素不存在，它返回一个指向新添加的容器的迭代器。bool 表示插入是否发生。

以下程序说明**定位**功能的工作:

**例 1:**

```cpp
// C++ program for the illustration of
// unordered_map::emplace() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    unordered_map<int, int> mp;

    // insert elements in random order
    mp.emplace(2, 30);
    mp.emplace(1, 40);
    mp.emplace(2, 20);
    mp.emplace(1, 50);
    mp.emplace(4, 50);

    // prints the elements
    for (auto it = mp.begin(); it != mp.end(); it++)
        cout << it->first << "==>>"
             << it->second << "\n";
}
```

**Output:**

```cpp
4==>>50
2==>>30
1==>>40

```

**示例 2** :假设我们想要显示一个字符串的所有具有索引的唯一字符。如果一个字符出现多次，则显示它第一次出现的索引。

```cpp
// C++ program for the illustration of
// unordered_map::emplace() function

#include <bits/stdc++.h>

using namespace std;

int main()
{
    string str = "geeksforgeeks";

    unordered_map<char, int> mp;
    for (int i = 0; i < str.length(); i++)
        mp.emplace(str[i], i);

    for (auto it = mp.begin(); it != mp.end(); it++)
        cout << it->first << "==>>" << it->second << "\n";
}
```

**Output:**

```cpp
r==>>7
e==>>1
s==>>4
g==>>0
k==>>3
f==>>5
o==>>6

```

**说明:**“g”在字符串中出现了 2 次，第一次出现在索引“0”处，然后出现在索引“8”处，但是定位功能不允许我们保存在无序 _map 中，直到给定的键是唯一的。这就是为什么“0”被保存而“8”没有。
同样为“e”，“1”被保存而“2”，“9”，“10”没有。