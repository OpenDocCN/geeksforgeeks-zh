# c++ STL 中的无序 _ 多集侵位()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-侵位-function-in-c-stl/](https://www.geeksforgeeks.org/unordered_multiset-emplace-function-in-c-stl/)

**无序 _ 多集::侵位()**是 C++ STL 中的一个内置函数，它在无序 _ 多集容器中插入一个新元素。插入会根据容器的标准在该位置自动完成。它将容器的尺寸增加了一个。

**语法:**

```cpp
unordered_multiset_name.emplace(val)
```

**参数:**该函数接受一个要插入容器的强制参数*值*。

**返回值:**返回一个迭代器，指向新插入的元素。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multiset::emplace() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<int> sample;

    // inserts element using emplace()
    sample.emplace(11);
    sample.emplace(11);
    sample.emplace(11);
    sample.emplace(12);
    sample.emplace(13);
    sample.emplace(13);
    sample.emplace(14);

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
// unordered_multiset::emplace() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<char> sample;

    // inserts element using emplace()
    sample.emplace('a');
    sample.emplace('a');
    sample.emplace('a');
    sample.emplace('b');
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