# c++ STL 中的多映射查找()

> 原文:[https://www.geeksforgeeks.org/multimap-find-in-cpp-stl/](https://www.geeksforgeeks.org/multimap-find-in-cpp-stl/)

**multimap::find()** 是 C++ STL 中的一个内置函数，它返回一个迭代器，一个常量迭代器，引用键在 multimap 中出现的位置。在存在多个相同键的情况下，引用其中一个键(通常是第一个键)的迭代器。如果我们希望用给定的密钥获得所有项目，我们可以使用 [equal_range()。](https://www.geeksforgeeks.org/multimap-equal_range-in-c-stl/)如果键不在 multimap 容器中，它将返回一个迭代器，一个引用 multimap.end()的常量迭代器。
**语法:**

```cpp
iterator multimap_name.find(key)
        or 
constant iterator multimap_name.find(key)
```

**参数:**该函数接受一个强制参数*键*，该参数指定要在多映射容器中搜索的键。
**返回值:**该函数返回一个迭代器或常量迭代器，该迭代器引用键在多映射中的位置。如果键不在 multimap 容器中，它将返回一个迭代器或常量迭代器，引用 multimap.end()。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program for illustration
// of multimap::find() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    multimap<int, int> mp;

    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 2, 60 });
    mp.insert({ 3, 20 });
    mp.insert({ 1, 50 });
    mp.insert({ 4, 50 });

    cout << "The elements from position 3 in multimap are : \n";
    cout << "KEY\tELEMENT\n";

    // find() function finds the position at which 3 is
    for (auto itr = mp.find(3); itr != mp.end(); itr++)
        cout << itr->first
             << '\t' << itr->second << '\n';

    return 0;
}
```

**Output:** 

```cpp
The elements from position 3 in multimap are : 
KEY    ELEMENT
3    20
4    50
```