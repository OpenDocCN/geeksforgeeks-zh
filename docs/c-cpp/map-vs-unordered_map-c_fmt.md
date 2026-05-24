# C++中map与unordered_map的对比

> 原文：[https://www.geeksforgeeks.org/map-vs-unordered_map-c/](https://www.geeksforgeeks.org/map-vs-unordered_map-c/)

先决条件：[`std::map`](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)、[`std::unordered_map`](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/)

说到效率，`map`和`unordered_map`有着巨大的区别。我们必须知道两者的内部工作原理，才能决定使用哪一个。

**差异：**

| 特性 | `map` | `unordered_map` |
| :--- | :--- | :--- |
| **排序** | 递增顺序（默认） | 无排序 |
| **实现** | 自平衡二叉搜索树（如红黑树） | 哈希表 |
| **查找时间** | `log(n)` | `O(1)` -> 平均<br>`O(n)` -> 最坏情况 |
| **插入时间** | `log(n)` + 重新平衡 | 与查找相同 |
| **删除时间** | `log(n)` + 重新平衡 | 与查找相同 |

**使用`std::map`时**

*   你需要有序的数据。
*   你需要按排序顺序打印/访问数据。
*   你需要元素的前驱或后继。
*   更多情况参见[BST相对哈希表的优势](https://www.geeksforgeeks.org/advantages-of-bst-over-hash-table/)。

## 使用`std::map`的示例

```cpp
// CPP program to demonstrate use of std::map
#include <bits/stdc++.h>

int main()
{
    // Ordered map
    std::map<int, int> order;

    // Mapping values to keys
    order[5] = 10;
    order[3] = 5;
    order[20] = 100;
    order[1] = 1;

    // Iterating the map and
    // printing ordered values
    for (auto i = order.begin(); i != order.end(); i++) {
        std::cout << i->first << " : " << i->second << '\n';
    }
}
```

**输出**

```cpp
1 : 1
3 : 5
5 : 10
20 : 100
```

**使用`std::unordered_map`时**

*   你需要记录一些数据（例如字符串），并且不需要排序。
*   你需要单个元素访问，即不需要遍历。

## 使用`std::unordered_map`的示例

```cpp
// CPP program to demonstrate use of
// std::unordered_map
#include <bits/stdc++.h>

int main()
{
    // Unordered map
    std::unordered_map<int, int> order;

    // Mapping values to keys
    order[5] = 10;
    order[3] = 5;
    order[20] = 100;
    order[1] = 1;

    // Iterating the map and
    // printing unordered values
    for (auto i = order.begin(); i != order.end(); i++)
    {
        std::cout << i->first << " : " << i->second << '\n';
    }
}
```

**输出**

```cpp
1 : 1
20 : 100
5 : 10
3 : 5
```