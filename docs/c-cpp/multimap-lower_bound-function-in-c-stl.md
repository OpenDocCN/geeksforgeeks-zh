# c++ STL 中的 multimap 下界()函数

> 原文:[https://www . geesforgeks . org/multimap-下界 _ function-in-c-STL/](https://www.geeksforgeeks.org/multimap-lower_bound-function-in-c-stl/)

**multimap::lower_bound(k)** 是 C++ STL 中的一个内置函数，它返回一个指向容器中键的迭代器，该键相当于参数中传递的 k。如果 k 不在 multimap 容器中，函数返回一个迭代器，指向刚好大于 k 的下一个元素。如果参数中传递的键超过了容器中的最大键，则返回的迭代器指向键+1 和元素= 0。

**语法:**

```cpp
multimap_name.lower_bound(key)
```

**参数:**该函数接受一个强制参数键，该键指定要返回其下界的元素。

**返回值:**函数返回一个迭代器，指向容器中的键，相当于参数中传递的 k。如果 k 不在 multimap 容器中，函数返回一个迭代器，指向刚好大于 k 的下一个元素。如果参数中传递的键超过了容器中的最大键，则返回的迭代器指向键+1 和元素=0。

```cpp
// C++ function for illustration
// multimap::lower_bound() function
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
    auto it = mp.lower_bound(2);
    cout << "The lower bound of key 2 is ";
    cout << (*it).first << " "
         << (*it).second << endl;

    // when 3 is not present
    it = mp.lower_bound(3);
    cout << "The lower bound of key 3 is ";
    cout << (*it).first << " "
         << (*it).second << endl;

    // when 5 exceeds
    it = mp.lower_bound(5);
    cout << "The lower bound of key 5 is ";
    cout << (*it).first << " "
         << (*it).second << endl;
    return 0;
}
```

**Output:**

```cpp
The lower bound of key 2 is 2 30
The lower bound of key 3 is 4 50
The lower bound of key 5 is 6 0

```