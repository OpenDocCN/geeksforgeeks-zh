# 在 C++ STL 中映射下界()函数

> 原文:[https://www . geesforgeks . org/map-下界 _ function-in-c-STL/](https://www.geeksforgeeks.org/map-lower_bound-function-in-c-stl/)

**映射::lower_bound(k)** 是 C++ STL 中的一个内置函数，它返回一个指向容器中键的迭代器，该键相当于参数中传递的 k。
**语法:**

```cpp
map_name.lower_bound(key)

```

**参数:**该函数接受一个强制参数键，该键指定要返回其下界的元素。
**返回值:**函数返回一个迭代器，指向映射容器中的键，相当于参数中传递的 k。如果 k 不在映射容器中，函数返回一个迭代器，指向刚好大于 k 的下一个元素。如果参数中传递的键超过了容器中的最大键，则返回的迭代器将映射中的元素数指向为键，元素=任何元素。

如果传递的参数超过了容器中的最大键，则返回的迭代器将指向像 std::set 中那样的 map::end()。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ function for illustration
// map::lower_bound() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    map<int, int> mp;

    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 10 });
    mp.insert({ 5, 50 });
    mp.insert({ 4, 40 });
    for (auto it = mp.begin(); it != mp.end(); it++)
    {
        cout << (*it).first << " " <<
                              (*it).second << endl;
    }

    // when 2 is present
    auto it = mp.lower_bound(2);
    cout << "The lower bound of key 2 is ";
    cout << (*it).first << " " << (*it).second << endl;

    // when 3 is not present
    // points to next greater after 3
    it = mp.lower_bound(3);
    cout << "The lower bound of key 3 is ";
    cout << (*it).first << " " << (*it).second;

    // when 6 exceeds
    it = mp.lower_bound(6);
    cout << "\nThe lower bound of key 6 is ";
    cout << (*it).first << " " << (*it).second;
    return 0;
}
```

**输出:**

```cpp
1 10
2 30
4 40
5 50
The lower bound of key 2 is 2 30
The lower bound of key 3 is 4 40
The lower bound of key 6 is 4 0

```