# C++ STL 中的无序映射

> 原文: [https://www.geeksforgeeks.org/unordered_map-in-cpp-stl/](https://www.geeksforgeeks.org/unordered_map-in-cpp-stl/)

无序映射是一个关联的容器，它存储由键值和映射值组合而成的元素。键值用于唯一标识元素，映射值是与键相关联的内容。键和值都可以是预定义或用户定义的任何类型。

内部`unordered_map`是使用[哈希表](https://www.geeksforgeeks.org/hashing-set-1-introduction/)实现的，提供给`map`的关键字被哈希成哈希表的索引，这就是为什么数据结构的性能很大程度上依赖于哈希函数，但是平均来说，从哈希表中搜索、插入和删除的成本是`O(1)`。

**注:** 在最坏的情况下，其时间复杂度可以从`O(1)`到`O(n)`，尤其是对于大素数。您可以在[如何在C++中高效使用无序映射](https://www.geeksforgeeks.org/map-vs-unordered_map-c/)上了解更多信息。在这种情况下，最好使用`map`来避免出现TLE错误。

## C++

```cpp
// C++ program to demonstrate functionality of unordered_map
#include <iostream>
#include <unordered_map>
using namespace std;

int main()
{
    // Declaring umap to be of <string, int> type
    // key will be of string type and mapped value will
    // be of int type
    unordered_map<string, int> umap;

    // inserting values by using [] operator
    umap["GeeksforGeeks"] = 10;
    umap["Practice"] = 20;
    umap["Contribute"] = 30;

    // Traversing an unordered map
    for (auto x : umap)
        cout << x.first << " " << x.second << endl;

}
```

**输出:**

```cpp
Contribute 30
GeeksforGeeks 10
Practice 20
```