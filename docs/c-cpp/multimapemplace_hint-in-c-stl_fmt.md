# `multimap::emplace_hint()` in C++ STL

> 原文: [https://www.geeksforgeeks.org/multimapemplace_hint-in-c-stl/](https://www.geeksforgeeks.org/multimapemplace_hint-in-c-stl/)

`multimap::emplace_hint()` 是 C++ STL 中的内置函数，它使用给定的提示将键及其元素插入 `multimap` 容器中。它有效地将容器大小增加了一个，因为 `multimap` 是存储具有相同值的多个键的容器。所提供的提示并不影响要输入的位置，它只是增加了插入的速度，因为它指向开始搜索排序的位置。它以容器后面的相同顺序插入。它的工作原理类似于 `multimap::emplace()` 函数，但如果用户提供的位置准确，它的速度有时会比它快。

## 语法

```cpp
multimap_name.emplace_hint(position, key, element)
```

## 参数

该功能接受三个强制参数 `key`，`element` 和 `position`，描述如下:

*   `Key` – 指定要插入到多映射容器中的键。
*   `Element` – 指定要插入到多映射容器键对应的元素。
*   `Position` – 指定开始排序搜索操作的位置，从而加快插入速度。

## 返回值

函数不返回任何内容。

## 示例代码

```cpp
// C++ program to illustrate the
// multimap::emplace_hint() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize container
    multimap<int, int> mp;

    // insert elements in random order
    mp.emplace_hint(mp.begin(), 2, 30); // faster
    mp.emplace_hint(mp.begin(), 1, 40); // faster
    mp.emplace_hint(mp.begin(), 2, 60); // slower
    mp.emplace_hint(mp.begin(), 2, 20); // slower
    mp.emplace_hint(mp.begin(), 1, 50); // faster
    mp.emplace_hint(mp.begin(), 1, 50); // faster

    // prints the elements
    cout << "\nThe multimap is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); itr++)
        cout << itr->first << "\t" << itr->second << endl;

    return 0;
}
```

## 输出

```
The multimap is : 
KEY    ELEMENT
1    50
1    50
1    40
2    20
2    60
2    30
```