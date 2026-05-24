# C++ 中对映射的 `lower_bound()` 和 `upper_bound()` 的实现

> 原文：[https://www.geeksforgeeks.org/implementation-of-lower_bound-and-upper_bound-on-map-of-pairs-in-c/](https://www.geeksforgeeks.org/implementation-of-lower_bound-and-upper_bound-on-map-of-pairs-in-c/)

## 先决条件
- [在 C++ STL 中映射 `lower_bound()` 函数](https://www.geeksforgeeks.org/lower_bound-in-cpp/)
- [在 C++ STL 中映射 `upper_bound()` 函数](https://www.geeksforgeeks.org/map-upper_bound-function-in-c-stl/)

在本文中，我们将讨论[对（pair）](https://www.geeksforgeeks.org/pair-in-cpp-stl/)的[映射（map）](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)中 [`lower_bound()`](https://www.geeksforgeeks.org/lower_bound-in-cpp/) 和 [`upper_bound()`](https://www.geeksforgeeks.org/upper_bound-in-cpp/) 的实现。

## `lower_bound()`
`lower_bound()` 返回一个迭代器，指向范围 **[first, last)** 中第一个值大于或等于给定值 **“val”** 的元素。但在对（pair）的映射中，对于 **`pair(x, y)`** 的 `lower_bound()` 将返回一个迭代器，指向第一个值大于或等于 **`x`** 且第二个值大于或等于 **`y`** 的对。
如果上述条件不满足，则返回一个指向对 **`{Map.size(), 0}`** 的迭代器。

### 语法
```cpp
mp.lower_bound({a, b})
```
其中，`mp` 是对的映射，`{a, b}` 是要查找其 `lower_bound` 的对。

## `upper_bound()`
`upper_bound()` 返回一个迭代器，指向范围 **[first, last)** 中第一个值大于给定值 **“val”** 的元素。但在对（pair）的映射中，对于 **`pair(x, y)`** 的 `upper_bound()` 将返回一个迭代器，指向第一个值大于 **`x`** 且第二个值大于 **`y`** 的对。
如果上述条件不满足，则返回一个指向对 **`{Map.size(), 0}`** 的迭代器。

### 语法
```cpp
mp.upper_bound({a, b})
```
其中，`mp` 是对的映射，`{a, b}` 是要查找其 `upper_bound` 的对。

## 示例程序
下面是演示对映射中 [`lower_bound()` 和 `upper_bound()`](https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-vector-in-cpp-stl/) 的程序：

### 程序 1
```cpp
// C++ program to demonstrate lower_bound()
// and upper_bound() in Map of Pairs

#include <bits/stdc++.h>
using namespace std;

// Function to implement lower_bound()
void findLowerBound(
    map<pair<int, int>, int>& mp,
    pair<int, int>& p)
{

    // This iterator points to the
    // lower_bound() of given pair
    auto low = mp.lower_bound(p);

    cout << "lower_bound() for {2, 5}"
         << " is: {"
         << (*low).first.first << ", "
         << (*low).first.second
         << "}" << endl;
}

// Function to implement upper_bound()
void findUpperBound(
    map<pair<int, int>, int>& mp,
    pair<int, int>& p)
{

    // This iterator points to the
    // upper_bound() of given pair
    auto up = mp.upper_bound(p);

    cout << "upper_bound() for {2, 5}"
         << " is: {"
         << (*up).first.first << ", "
         << (*up).first.second
         << "}" << endl;
}

// Driver Code
int main()
{
    // Declare map of Pairs
    map<pair<int, int>, int> mp;

    // Insert Pairs in Map
    mp.insert({ { 2, 3 }, 8 });
    mp.insert({ { 4, 1 }, 5 });
    mp.insert({ { 7, 1 }, 3 });
    mp.insert({ { 9, 3 }, 1 });
    mp.insert({ { 5, 0 }, 3 });

    // Given pair {2, 5}
    pair<int, int> p = { 2, 5 };

    // Function Call to find lower_bound
    // of pair p in map mp
    findLowerBound(mp, p);

    // Function Call to find upper_bound
    // of pair p in map mp
    findUpperBound(mp, p);

    return 0;
}
```

### 输出
```cpp
lower_bound() for {2, 5} is: {4, 1}
upper_bound() for {2, 5} is: {4, 1}
```