# c++ STL 中的无序 _ 集合侵位 _ 提示()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-侵位 _hint-function-in-c-stl/](https://www.geeksforgeeks.org/unordered_set-emplace_hint-function-in-c-stl/)

函数的作用是:C++ STL 中的一个内置函数，只有当要插入的值是唯一的，并且有一个给定的提示时，它才会在无序集中插入一个新元素。

**语法:**

```cpp
unordered_set_name.emplace_hint( position, value )
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **位置:**此参数用于描述插入操作的位置。
*   **值:**该参数用于保存需要插入的。

**返回值:**如果该值不存在于无序集中，则函数插入该值并返回指向插入元素的迭代器。否则，如果该值已经存在于无序集中，那么函数返回指向该元素的迭代器。

下面的程序说明了 C++ STL 中的无序 _ 集合::侵位 _ 提示()函数:

**程序 1:**

```cpp
// CPP program to illustrate
// unordered_set::emplace_hint() function
#include <iostream>
#include <unordered_set>
using namespace std;

// main program
int main()
{

    // Initialize an unordered_set
    unordered_set<int> uset = { 20, 40, 50, 60 };

    // Insert an element that is not present
    uset.emplace_hint(uset.begin(), 80);

    // Display uset
    cout << "uset: ";
    for (auto it = uset.begin(); it != uset.end(); it++)
        cout << *it << " ";
}
```

**Output:**

```cpp
uset: 80 20 40 50 60

```

**程序 2:**

```cpp
// CPP program to illustrate
// unordered_set::emplace_hint() function
#include <iostream>
#include <unordered_set>
using namespace std;

// main program
int main()
{

    // Initialize an unordered_set
    unordered_set<int> uset = { 20, 40, 50, 60 };

    // Try to Insert an element that is not present
    uset.emplace_hint(uset.begin(), 50);

    // Display uset
    cout << "uset: ";
    for (auto it = uset.begin(); it != uset.end(); it++)
        cout << *it << " ";
}
```

**Output:**

```cpp
uset: 60 50 40 20

```