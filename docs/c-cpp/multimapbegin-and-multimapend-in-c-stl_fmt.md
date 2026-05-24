# C++ STL 中的 `multimap::begin()` 和 `multimap::end()`

> 原文：[https://www.geeksforgeeks.org/multimapbegin-and-multimapend-in-c-stl/](https://www.geeksforgeeks.org/multimapbegin-and-multimapend-in-c-stl/)

## `multimap::begin()`

`multimap::begin()` 是 C++ STL 中的一个内置函数，它返回一个指向 `multimap` 容器中第一个元素的迭代器。由于 `multimap` 容器中的元素是有序存储的，`begin()` 将指向根据容器排序准则排在最前面的那个元素。

**语法：**

```cpp
multimap_name.begin()
```

**参数：** 函数不接受任何参数。

**返回值：** 函数返回一个迭代器，引用 `multimap` 容器中的第一个元素。

```cpp
// C++ function to illustrate
// the multimap::begin() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize container
    multimap<int, int> mp;

    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 3, 60 });
    mp.insert({ 4, 20 });
    mp.insert({ 5, 50 });

    auto ite = mp.begin();

    cout << "The first element is: ";
    cout << "{" << ite->first << ", "
         << ite->second << "}\n";

    // prints the elements
    cout << "\nThe multimap is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }
    return 0;
}
```

**Output:**

```cpp
The first element is: {1, 40}

The multimap is : 
KEY    ELEMENT
1    40
2    30
3    60
4    20
5    50
```

## `multimap::end()`

`multimap::end()` 是 C++ STL 中的一个内置函数，它返回一个指向 `multimap` 容器中“末尾之后”位置的迭代器。该位置不指向容器中的任何元素，它是一个占位符，表示序列的结束。如果容器为空，则 `begin()` 和 `end()` 返回相同的值。

**语法：**

```cpp
multimap_name.end()
```

**参数：** 函数不接受任何参数。

**返回值：** 函数返回一个指向容器中“末尾之后”位置的迭代器。

```cpp
// C++ program to illustrate
// the multimap::end() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize container
    multimap<int, int> mp;

    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 3, 60 });
    mp.insert({ 4, 20 });
    mp.insert({ 5, 50 });

    // get the end iterator
    auto ite = mp.end();

    // decrement the end iterator to get the last element
    --ite;

    cout << "The last element is: ";
    cout << "{" << ite->first << ", "
         << ite->second << "}\n";

    // prints the elements
    cout << "\nThe multimap is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }
    return 0;
}
```

**Output:**

```cpp
The last element is: {5, 50}

The multimap is : 
KEY    ELEMENT
1    40
2    30
3    60
4    20
5    50
```