# 地图 vs c++ 中的无序 _ 地图

> 原文:[https://www.geeksforgeeks.org/map-vs-unordered_map-c/](https://www.geeksforgeeks.org/map-vs-unordered_map-c/)

先决条件: [std::map](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/) 、 [std::无序 _map](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/)
说到效率，地图和无序地图有着巨大的区别。
我们必须知道两者的内部工作，才能决定使用哪一个。

**差异:**

```cpp
                  | map             | unordered_map
---------------------------------------------------------
Ordering        | increasing  order   | no ordering
                | (by default)        |

Implementation  | Self balancing BST  | Hash Table
                | like Red-Black Tree |  

search time     | log(n)              | O(1) -> Average 
                |                     | O(n) -> Worst Case

Insertion time  | log(n) + Rebalance  | Same as search

Deletion time   | log(n) + Rebalance  | Same as search

```

**使用标准::地图时**

*   你需要有序的数据。
*   您必须打印/访问数据(按排序顺序)。
*   您需要元素的前置/后置。
*   更多情况参见[BST 相对 Hash tab](https://www.geeksforgeeks.org/advantages-of-bst-over-hash-table/)e 的优势。

## 卡片打印处理机（Card Print Processor 的缩写）

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
    for (auto i = order.begin(); i
         != order.end(); i++) {
        std::cout << i->first
                  << " : "
                  << i->second << '\n';
    }
}
```

**Output**

```cpp
1 : 1
3 : 5
5 : 10
20 : 100

```

**在**时使用标准::无序 _ 映射

*   您需要记录一些数据(例如字符串)，并且不需要排序。
*   您需要单个元素访问，即没有遍历。

## 卡片打印处理机（Card Print Processor 的缩写）

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
    for (auto i = order.begin();
         i != order.end(); i++)
    {
        std::cout << i->first
                  << " : "
                  << i->second << '\n';
    }
}
```

**Output**

```cpp
1 : 1
20 : 100
5 : 10
3 : 5

```