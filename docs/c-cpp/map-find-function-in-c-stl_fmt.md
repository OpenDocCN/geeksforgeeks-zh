# C++ STL 中的 map::find() 函数

> 原文：[https://www.geeksforgeeks.org/map-find-function-in-c-stl/](https://www.geeksforgeeks.org/map-find-function-in-c-stl/)

`map::find()` 是 C++ STL 中的一个内置函数，它返回一个迭代器（或常量迭代器），指向键在映射中出现的位置。如果该键不在 `map` 容器中，它将返回一个迭代器或常量迭代器，指向 `map.end()`。

## 语法

```cpp
iterator = map_name.find(key)
// 或者
constant_iterator = map_name.find(key)
```

## 参数
该函数接受一个强制参数 `key`，该参数指定要在 `map` 容器中搜索的键。

## 返回值
该函数返回一个迭代器或常量迭代器，该迭代器指向键在映射中出现的位置。如果该键不在 `map` 容器中，它将返回一个迭代器或常量迭代器，指向 `map.end()`。

## 时间复杂度
在 `std::map` 中搜索元素的时间复杂度为 O(log n)。即使在最坏的情况下，它也将是 O(log n)，因为元素在内部存储为平衡二叉查找树（BST）。而在 `std::unordered_map` 中，搜索的最佳时间复杂度是 O(1)。

## 示例代码

```cpp
// C++ program for illustration
// of map::find() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialize container
    map<int, int> mp;

    // Insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 3, 20 });
    mp.insert({ 4, 50 });

    cout << "Elements from position of 3 in the map are : \n";
    cout << "KEY\tELEMENT\n";

    // find() function finds the position
    // at which 3 is present
    for (auto itr = mp.find(3); itr != mp.end(); itr++) {
        cout << itr->first << '\t' << itr->second << '\n';
    }

    return 0;
}
```

## 输出

```
The elements from position 3 in map are : 
KEY    ELEMENT
3    20
4    50
```