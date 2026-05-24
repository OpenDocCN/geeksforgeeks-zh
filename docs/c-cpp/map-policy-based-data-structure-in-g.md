# 在 g++

中映射基于策略的数据结构

> 原文:[https://www . geesforgeks . org/map-policy-based-data-structure-in-g/](https://www.geeksforgeeks.org/map-policy-based-data-structure-in-g/)

g++ 编译器支持一些数据结构，但它们不是 C++ 标准库的一部分。其中之一是:[基于策略的数据结构](https://www.geeksforgeeks.org/policy-based-data-structures-g/)，用于高性能、灵活性、语义安全性以及与 std 中相应容器的一致性。
这也可以用作[地图](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)，以排序顺序存储键和值(对)。
所以要使用这个数据结构，必须在代码中添加以下几行:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <ext/pb_ds/assoc_container.hpp> // Common file
#include <ext/pb_ds/tree_policy.hpp>
#include <functional> // for less

using namespace __gnu_pbds;
```

下面是将基于策略的数据结构显示为映射的代码，它可以添加/删除元素对，可以找到小于(x，y)的对的数量，kth 最小对等。在 0(对数 N)时间内。这张地图的特别之处在于，我们可以访问这一对元素在有序的 2D 数组中的索引。如果这一对没有出现在地图上，我们就得到这一对在地图上的位置。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// Program showing a Policy Based Data Structure as a map
#include <ext/pb_ds/assoc_container.hpp>
#include <ext/pb_ds/tree_policy.hpp>
#include <functional>
#include <iostream>
using namespace __gnu_pbds;
using namespace std;

// A new data structure is defined
// Please refer https : // goo.gl/WVDL6g
typedef tree<pair<int, int>, null_type, less<pair<int, int> >,
             rb_tree_tag, tree_order_statistics_node_update>
    ordered_map;

// Driver code
int main()
{
    ordered_map om;

    om.insert({ 23, 20 });
    om.insert({ 23, 10 });
    om.insert({ 23, 30 });
    om.insert({ 12, 35 });
    om.insert({ 12, 22 });

    // Another method to insert pair
    // om.insert(make_pair(23, 20));

    // Print the contents of the map
    cout << "Contents of map:\n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = om.begin(); itr != om.end(); ++ itr) {
        cout << itr->first << "\t" << itr->second << "\n";
    }

    // value at 3rd index in sorted array.
    cout << "The value at 3rd index is "
         << "{" << om.find_by_order(3)->first << ", "
         << om.find_by_order(3)->second << "}\n";

    // Index of pair {23, 30}
    cout << "The index of pair {23, 30} is "
         << om.order_of_key({ 23, 30 }) << endl;

    // Pair {23, 40} is not in the map but it will show the
    // index number if it was there in sorted array
    cout << "The index of pair {23, 40} is "
         << om.order_of_key({ 23, 40 }) << endl;

    return 0;
}
```

**Output:** 

```cpp
Contents of map:
KEY    ELEMENT
12    22
12    35
23    10
23    20
23    30
The value at 3rd index is {23, 20}
The index of pair {23, 30} is 4
The index of pair {23, 40} is 5
```