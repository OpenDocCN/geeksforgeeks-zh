# c++ STL 中的 multimap upper _ bound()函数

> 原文:[https://www . geesforgeks . org/multimap-upper _ bound-function-in-c-STL/](https://www.geeksforgeeks.org/multimap-upper_bound-function-in-c-stl/)

**multimap::upper_bound(k)** 是 C++ STL 中的一个内置函数，它返回一个迭代器，指向刚好大于 k 的下一个元素，如果传入参数的键超过了容器中的最大键，那么返回的迭代器指向键+1，元素=0。

**语法:**

```cpp
multimap_name.upper_bound(key)
```

**参数:**该函数接受一个强制参数键，该键指定返回其下界的元素。

**返回值:**函数返回一个迭代器，指向刚好大于 k 的下一个元素，如果传入参数的键超过容器中的最大键，则返回的迭代器指向键+1，元素=0。

```cpp
// C++ function for illustration
// multimap::upper_bound() function
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
    mp.insert({ 2, 20 });
    mp.insert({ 1, 50 });
    mp.insert({ 4, 50 });

    // when 2 is present
    auto it = mp.upper_bound(2);
    cout << "The upper bound of key 2 is ";
    cout << (*it).first << " " << (*it).second << endl;

    // when 3 is not present
    it = mp.upper_bound(3);
    cout << "The upper bound of key 3 is ";
    cout << (*it).first << " " << (*it).second << endl;

    // when 5 is exceeds the maximum key
    it = mp.upper_bound(5);
    cout << "The upper bound of key 5 is ";
    cout << (*it).first << " " << (*it).second;
    return 0;
}
```

**Output:**

```cpp
The upper bound of key 2 is 4 50
The upper bound of key 3 is 4 50
The upper bound of key 5 is 6 0

```