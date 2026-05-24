# 映射 C++ STL 中的 upper_bound()函数

> 原文:[https://www . geesforgeks . org/map-upper _ bound-function-in-c-STL/](https://www.geeksforgeeks.org/map-upper_bound-function-in-c-stl/)

**[映射:](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/) : [upper_bound()](https://www.geeksforgeeks.org/stdupper_bound-in-cpp/)** 是 C++ STL 中的内置函数，它返回一个迭代器，该迭代器指向刚好大于 k 的下一个元素。如果参数中传递的键超过了容器中的最大键，则返回的迭代器指向映射容器中的元素数，作为键，元素=0。

**语法:**

```cpp
map_name.upper_bound(key)
```

**参数:**该函数接受一个强制参数*键*，该键指定返回上限的元素。

**返回值:**函数返回一个迭代器，指向紧接的下一个大于 k 的元素，如果传入参数的键超过了容器中的最大键，则返回的迭代器指向 map_name.end()。请注意，end()是一个特殊的迭代器，它不存储映射的有效成员的地址。

下面是上述方法的实现:

```cpp
// C++ function for illustration
// map::upper_bound() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize container
    map<int, int> mp;

    // insert elements in random order
    mp.insert({ 12, 30 });
    mp.insert({ 11, 10 });
    mp.insert({ 15, 50 });
    mp.insert({ 14, 40 });

    // when 11 is present
    auto it = mp.upper_bound(11);
    cout << "The upper bound of key 11 is ";
    cout << (*it).first << " " << (*it).second << endl;

    // when 13 is not present
    it = mp.upper_bound(13);
    cout << "The upper bound of key 13 is ";
    cout << (*it).first << " " << (*it).second << endl;

    // when 17 is exceeds the maximum key, so size
        // of mp is returned as key and value as 0.
    it = mp.upper_bound(17);
    cout << "The upper bound of key 17 is ";
    cout << (*it).first << " " << (*it).second;
    return 0;
}
```

**Output:**

```cpp
The upper bound of key 11 is 12 30
The upper bound of key 13 is 14 40
The upper bound of key 17 is 4 0

```