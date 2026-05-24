# c++ STL 中的无序 _ 多集等范围()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-equal _ range-function-in-cstl/](https://www.geeksforgeeks.org/unordered_multiset-equal_range-function-in-cstl/)

**无序 _ 多集::相等 _ 范围()**是 C++ STL 中的内置函数，返回所有元素等于给定的*值*的范围。它返回一对迭代器，其中第一个迭代器指向范围的下限，第二个迭代器指向范围的上限。如果容器中没有等于给定*值*的元素，则返回一对，其中下限和上限都指向容器结束后的位置。

**语法:**

```cpp
unordered_multiset_name.equal_range(value)
```

**参数:**该函数接受一个要返回其范围的元素*值*。

**返回值:**返回一对迭代器。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multiset::equal_range() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<int> sample;

    // inserts element
    sample.insert(100);
    sample.insert(100);
    sample.insert(100);
    sample.insert(200);
    sample.insert(500);
    sample.insert(500);
    sample.insert(600);

    // iterator of pairs pointing to range
    // which includes 500 and print by iterating in range
    auto itr = sample.equal_range(500);
    for (auto it = itr.first; it != itr.second; it++) {
        cout << *it << " ";
    }

    cout << endl;

    // iterator of pairs pointing to range
    // which includes 100 and print by iterating in range
    itr = sample.equal_range(100);
    for (auto it = itr.first; it != itr.second; it++) {
        cout << *it << " ";
    }

    return 0;
}
```

**Output:**

```cpp
500 500 
100 100 100

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multiset::equal_range() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<char> sample;

    // inserts element
    sample.insert('a');
    sample.insert('a');
    sample.insert('b');
    sample.insert('c');
    sample.insert('d');
    sample.insert('d');
    sample.insert('d');

    // iterator of pairs pointing to range
    // which includes 'a' and print by iterating in range
    auto itr = sample.equal_range('a');
    for (auto it = itr.first; it != itr.second; it++) {
        cout << *it << " ";
    }

    cout << endl;

    // iterator of pairs pointing to range
    // which includes 'd' and print by iterating in range
    itr = sample.equal_range('d');
    for (auto it = itr.first; it != itr.second; it++) {
        cout << *it << " ";
    }

    return 0;
}
```

**Output:**

```cpp
a a 
d d d

```