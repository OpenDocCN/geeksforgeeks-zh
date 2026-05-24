# 在 C++ STL 中映射 equal_range()

> 原文:[https://www.geeksforgeeks.org/map-equal_range-in-c-stl/](https://www.geeksforgeeks.org/map-equal_range-in-c-stl/)

**映射::equal_range()** 是 C++ STL 中的内置函数，返回一对迭代器。该对指的是一个范围的边界，该范围包括容器中所有关键字等于 K 的元素。由于映射容器只包含唯一的关键字，因此返回的对中的第一个迭代器指向该元素，对中的第二个迭代器指向关键字 K 之后的下一个关键字。如果与关键字 K 不匹配，并且关键字 K 大于最大的关键字， 返回的范围长度为 1，两个迭代器都指向一个元素，该元素的键表示 map 的大小，元素为 0。 否则，下界和上界指向仅大于关键字 k 的元素。
**语法:**

```cpp
iterator map_name.equal_range(key)
```

**参数:**该函数接受单个强制参数*键*，该键指定容器中要返回其范围的元素。
**返回值:**函数返回一对迭代器，如上所述。
以下程序举例说明上述方法:
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// map::equal_range() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    map<int, int> mp;

    // insert elements in random order
    mp.insert({ 4, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 6, 60 });

    pair<map<int, int>::iterator,
         map<int, int>::iterator>
        it;

    // iterator of pairs
    it = mp.equal_range(1);
    cout << "The lower bound is "
         << it.first->first
         << ":" << it.first->second;

    cout << "\nThe upper bound is "
         << it.second->first
         << ":" << it.second->second;

    return 0;
}
```

**Output:** 

```cpp
The lower bound is 1:40
The upper bound is 4:30
```

**程序 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// map::equal_range() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    map<int, int> mp;

    // insert elements in random order
    mp.insert({ 4, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 6, 60 });

    pair<map<int, int>::iterator,
         map<int, int>::iterator>
        it;

    // iterator of pairs
    it = mp.equal_range(10);
    cout << "The lower bound is "
         << it.first->first << ":"
         << it.first->second;

    cout << "\nThe upper bound is "
         << it.second->first
         << ":" << it.second->second;

    return 0;
}
```

**Output:** 

```cpp
The lower bound is 3:0
The upper bound is 3:0
```