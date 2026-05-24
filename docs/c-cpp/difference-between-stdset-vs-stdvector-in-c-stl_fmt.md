# C++ STL 中 `std::set` 与 `std::vector` 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-stdset-vs-stdvector-in-c-stl/](https://www.geeksforgeeks.org/difference-between-stdset-vs-stdvector-in-c-stl/)

## `std::vector`

[`std::vector`](https://www.geeksforgeeks.org/vector-in-cpp-stl/) 是类似于[动态数组](https://www.geeksforgeeks.org/how-do-dynamic-arrays-work/)的容器，可以在插入或删除新元素时调整大小。它是[标准模板库或 **STL**](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的模板，为程序提供了更多的灵活性。向量的元素被放置在[连续存储](https://www.geeksforgeeks.org/difference-between-contiguous-and-noncontiguous-memory-allocation/)中，并使用[迭代器](https://www.geeksforgeeks.org/iterators-c-stl/)遍历。

**示例：**

```cpp
vector <int> v;
v.push_back(1);
v.push_back(2);
v.clear();
```

下面是向量在 C++ 中的实现：

```cpp
// C++ program to demonstrate the
// working of vector in cpp
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    vector<int> v;

    // Inserting elements in vector
    v.push_back(11);
    v.push_back(6);
    v.push_back(12);
    v.push_back(0);
    v.push_back(0);

    // Elements are stored in the
    // order of insertion with the
    // duplicate element
    cout << "Elements in vector are:\n";
    for (auto it : v) {
        cout << it << " ";
    }

    return 0;
}
```

**Output：**

```cpp
Elements in vector are:
11 6 12 0 0
```

## `std::set`

[`std::set`](https://www.geeksforgeeks.org/set-in-cpp-stl/) 是一个存储唯一元素的容器，并且元素总是有序的。它是[标准模板库或 **STL**](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的模板。`std::set` 中的元素总是唯一的，并且以特定的顺序存储。`std::set` 中的元素可以通过迭代器访问。

**示例：**

```cpp
set<int> s;
s.insert(1);
s.insert(2);
s.insert(2); // 重复元素不会被插入
s.erase(1);
```

下面是集合在 C++ 中的实现：

```cpp
// C++ program to demonstrate the
// working of set in cpp
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    set<int> s;

    // Inserting elements in set
    s.insert(11);
    s.insert(6);
    s.insert(12);
    s.insert(0);
    s.insert(0); // 重复元素不会被插入

    // Elements are stored in sorted order
    // and are unique
    cout << "Elements in set are:\n";
    for (auto it : s) {
        cout << it << " ";
    }

    return 0;
}
```

**Output：**

```cpp
Elements in set are:
0 6 11 12
```

## 主要区别

| 特性 | `std::vector` | `std::set` |
| :--- | :--- | :--- |
| **存储** | 连续存储 | 非连续存储（通常为红黑树） |
| **元素顺序** | 按插入顺序存储 | 按排序顺序存储 |
| **唯一性** | 允许重复元素 | 元素唯一，不允许重复 |
| **访问时间** | 随机访问为 O(1)，插入/删除在末尾为 O(1)，在中间为 O(n) | 查找、插入、删除均为 O(log n) |
| **迭代器** | 随机访问迭代器 | 双向迭代器 |
| **使用场景** | 需要快速随机访问和尾部高效操作的场景 | 需要有序、唯一元素集合的场景 |