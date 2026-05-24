# c++ STL 中无序 _ 多映射插入()

> 原文:[https://www . geesforgeks . org/unordered _ multimap-insert-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-insert-in-c-stl/)

函数**STD::unordered_multimap::insert()**是 C++ STL 中的内置函数，通过在 unordered _ multimap 中插入新元素来扩展容器。该函数将容器大小增加一。insert()函数可用于插入单个键值对、完整的无序映射、初始化列表插入等。

**语法:**

```cpp
iterator insert(const_iterator position, const value_type& val);
```

**参数:**该方法取以下参数:

*   **位置:**插入元素的位置
*   **值:**要插入的值

**返回值:**这个方法返回一个指向新插入元素的迭代器。
**时间复杂度:**

*   一般情况下为 0(1)
*   O(n)在最坏的情况下

以下程序说明了*无序 _ 多映射::插入功能*:
T3】程序 1:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
#include <unordered_map>

using namespace std;
int main(void)
{
    // Declare unordered_multimap
    unordered_multimap<char, int> cmap = {
        { 'B', 2 },
        { 'C', 3 },
        { 'D', 4 },
        { 'E', 5 },
    };

    // insert a key-value pair using insert()
    auto pos
        = cmap.insert(cmap.begin(),
                      pair<char, int>('A', 1));

    // print the map with the newly inserted key-value pair
    for (auto x : cmap)
        cout << x.first << ": "
             << x.second << endl;

    return 0;
}
```

**Output:** 

```cpp
A: 1
B: 2
C: 3
D: 4
E: 5
```

**程序 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
#include <unordered_map>

using namespace std;
int main()
{
    // Declare unordered_multimap
    unordered_multimap<char, int> cmap = {
        { 'b', 2 },
        { 'c', 3 },
        { 'd', 4 },
        { 'e', 5 },
    };

    unordered_multimap<char, int> dmap
        = { { 'A', 1 },
            { 'G', 6 } };

    // Insert the map from begin to end
    cmap.insert(dmap.begin(), dmap.end());

    // Print the map
    for (auto x : cmap)
        cout << x.first << ": "
             << x.second << endl;

    return 0;
}
```

**Output:** 

```cpp
G: 6
A: 1
b: 2
c: 3
d: 4
e: 5
```

**程序 3:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
#include <unordered_map>

using namespace std;
int main()
{
    // Declare unordered_multimap
    unordered_multimap<char, int> cmap = {
        { 'B', 2 },
        { 'C', 3 },
        { 'D', 4 },
        { 'E', 5 },
    };

    // Insert a new list
    cmap.insert({ { 'A', 1 },
                  { 'F', 6 },
                  { 'G', 7 } });

    // Print the map
    for (auto x : cmap)
        cout << x.first << ": "
             << x.second << endl;

    return 0;
}
```

**Output:** 

```cpp
G: 7
F: 6
A: 1
B: 2
C: 3
D: 4
E: 5
```