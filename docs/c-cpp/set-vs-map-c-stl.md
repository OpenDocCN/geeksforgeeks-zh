# 在 C++ STL 中设置 vs 贴图

> 原文:[https://www.geeksforgeeks.org/set-vs-map-c-stl/](https://www.geeksforgeeks.org/set-vs-map-c-stl/)

STL 中的 [set](https://www.geeksforgeeks.org/set-in-cpp-stl/) 和 [map](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/) 在某种意义上是相似的，它们都使用[红黑树](https://www.geeksforgeeks.org/red-black-tree-set-1-introduction-2/)(一种自平衡 [BST](https://www.geeksforgeeks.org/binary-search-tree-set-1-search-and-insertion/) )。请注意，搜索、插入和删除的时间复杂度是 O(Log n)。
**差异** :
设置的差异仅用于存储键，而 map 用于存储键值对。例如，在[打印排序的不同元素](https://www.geeksforgeeks.org/print-sorted-distinct-elements-array-c/)的问题中，我们使用 set，因为某个键需要值。如果我们改变问题来打印不同排序元素的频率，我们使用 map。我们需要映射来将数组值存储为键，将频率存储为值。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate working of set
#include <bits/stdc++.h>
using namespace std;

int main()
{
    set<int> s1;
    s1.insert(2);
    s1.insert(5);
    s1.insert(3);
    s1.insert(6);

    cout << "Elements in set:\n";
    for (auto it : s1)
        cout << it << " "; // Sorted

    return 0;
}
```

**Output:** 

```cpp
Elements in set:
2 3 5 6
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate working of map
#include <bits/stdc++.h>
using namespace std;

int main()
{
    map<int, int> m;

    m[1] = 2; // Insertion by indexing

    // Direct pair insertion
    m.insert({ 4, 5 });

    // Insertion of pair by make_pair
    m.insert(make_pair(8, 5));

    cout << "Elements in map:\n";
    for (auto it : m)
        cout << "[ " << it.first << ", "
             << it.second << "]\n"; // Sorted

    return 0;
}
```

**Output:** 

```cpp
Elements in map:
[ 1, 2]
[ 4, 5]
[ 8, 5]
```

**集合和映射的变体** :
集合和映射都存储唯一值和排序值。但是如果我们没有这样的要求，我们使用多集/多映射和无序集/无序映射。
**多映射**:多映射不允许通过索引来存储元素。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate working of Multimap
#include <bits/stdc++.h>
using namespace std;

int main()
{
    multimap<int, int> m;

    m.insert({ 1, 2 });
    m.insert({ 2, 3 });
    m.insert({ 4, 5 });
    m.insert({ 2, 3 });
    m.insert({ 1, 2 });

    cout << "Elements in Multimap:\n";
    for (auto it : m)
        cout << "[ " << it.first << ", "
             << it.second << "]\n"; // Sorted

    return 0;
}
```

**Output:** 

```cpp
Elements in Multimap:
[ 1, 2]
[ 1, 2]
[ 2, 3]
[ 2, 3]
[ 4, 5]
```

**多组**:T2

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate working of Multiset
#include <bits/stdc++.h>
using namespace std;

int main()
{
    multiset<int> ms;

    ms.insert(1);
    ms.insert(3);
    ms.insert(4);
    ms.insert(2);
    ms.insert(2);

    cout << "Elements in Multiset:\n";
    for (auto it : ms)
        cout << it << " ";

    return 0;
}
```

**Output:** 

```cpp
Elements in Multiset:
1 2 2 3 4
```

**无序 _ 集合** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate working of Unordered_set
#include <bits/stdc++.h>
using namespace std;

int main()
{
    unordered_set<int> us;

    us.insert(1);
    us.insert(3);
    us.insert(4);
    us.insert(2);
    us.insert(2);

    cout << "Elements in unordered_set:\n";
    for (auto it : us)
        cout << it << " "; // Sorted

    return 0;
}
```

**Output:** 

```cpp
Elements in unordered_set:
2 4 1 3
```

**无序 _ 地图** :

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate working of Unordered_map
#include <bits/stdc++.h>
using namespace std;

int main()
{
    unordered_map<int, int> um;

    um[1] = 2;
    um[4] = 5;
    um[2] = 3;
    um[8] = 5;
    um[3] = 6;

    cout << "Elements in unordered_map:\n";
    for (auto it : um)
        cout << "[ " << it.first << ", " << it.second << "]\n";

    return 0;
}
```

**Output:** 

```cpp
Elements in unordered_map:
[ 3, 6]
[ 2, 3]
[ 8, 5]
[ 1, 2]
[ 4, 5]
```