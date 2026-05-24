# c++ STL 中的无序 _ 映射插入

> 原文:[https://www . geesforgeks . org/unordered _ map-insert-in-c-STL/](https://www.geeksforgeeks.org/unordered_map-insert-in-c-stl/)

**[无序 _ 映射](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/):insert()**是 C++ STL 中的内置函数，用于在无序 _ 映射容器中插入带有特定键的元素。该函数将容器大小增加 1。此函数不插入重复条目。该函数有以下变体。都是重载函数。
**语法-1:**

> 迭代器无序映射名称插入({key，element})

**参数:**该函数以两个参数作为输入参数。要插入的键及其值。
**返回类型:**函数返回指向容器中新元素的迭代器。

```cpp
// C++ program to illustrate
// unordered_map::insert({key, element})
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize container
    unordered_map<int, int> ump;

    // insert elements in random order
    ump.insert({ 20, 130 });
    ump.insert({ 100, 410 });
    ump.insert({ 31, 60 });

    // prints the elements
    cout << "KEY\tELEMENT\n";
    for (auto itr = ump.begin(); itr != ump.end(); itr++) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }
    return 0;
}
```

**Output:**

```cpp
KEY    ELEMENT
31    60
20    130
100    410

```