# c++ STL 中的无序 _ 多集侵位 _ 提示()函数

> 原文:[https://www . geesforgeks . org/无序 _ 多集-侵位 _ 提示-函数 in-c-stl/](https://www.geeksforgeeks.org/unordered_multiset-emplace_hint-function-in-c-stl/)

**无序 _ 多集::侵位 _ 提示()**是 C++ STL 中的一个内置函数，它在无序 _ 多集容器中插入一个新元素。它从参数中提供的位置开始搜索元素的插入点。位置只是一个提示，它并不决定插入的位置。插入会根据容器的标准在该位置自动完成。它将容器的尺寸增加了一个。

**语法:**

```cpp
unordered_multiset_name.emplace_hint(iterator position, val)
```

**参数:**该功能接受两个强制参数，如下所述:

*   **位置:**指定迭代器指向插入搜索操作开始的位置。
*   **val:** 指定要插入容器的元素。

**返回值:**返回一个迭代器，指向新插入的元素。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multiset::emplace_hint()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<int> sample;

    // inserts element using emplace_hint()

    // fast insertions as the search starts
    // from the previously inserted positions
    auto it = sample.emplace_hint(sample.begin(), 11);
    it = sample.emplace_hint(it, 11);
    it = sample.emplace_hint(it, 11);

    // slow insertions as the search starts from the
    // beginning of the containers
    sample.emplace_hint(sample.begin(), 12);
    sample.emplace_hint(sample.begin(), 13);
    sample.emplace_hint(sample.begin(), 13);
    sample.emplace_hint(sample.begin(), 14);

    cout << "Elements: ";

    for (auto it = sample.begin(); it != sample.end(); it++)
        cout << *it << " ";
    return 0;
}
```

**Output:**

```cpp
Elements: 14 11 11 11 12 13 13

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multiset::emplace_hint() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<char> sample;

    // inserts element using emplace_hint()

    // fast insertions as the search starts
    // from the previously inserted positions
    auto it = sample.emplace_hint(sample.begin(), 'a');
    it = sample.emplace_hint(it, 'a');
    it = sample.emplace_hint(it, 'a');
    it = sample.emplace_hint(it, 'b');

    // slow insertions as the search starts from the
    // beginning of the containers
    sample.emplace('b');
    sample.emplace('c');
    sample.emplace('d');

    cout << "Elements: ";

    for (auto it = sample.begin(); it != sample.end(); it++)
        cout << *it << " ";
    return 0;
}
```

**Output:**

```cpp
Elements: d a a a b b c

```