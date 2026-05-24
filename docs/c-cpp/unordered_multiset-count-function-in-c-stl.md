# c++ STL 中的无序 _ 多集计数()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-count-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-count-function-in-c-stl/)

**无序 _ 多集::count()** 是 C++ STL 中的内置函数，返回无序 _ 多集容器中等于给定值的元素计数。

**语法:**

```cpp
unordered_multiset_name.count(val)
```

**参数:**该函数接受单个强制参数*值*，该参数指定要返回无序多集容器中其计数的元素。

**返回值:**它返回一个无符号整数类型，表示一个*值*在容器中出现的次数。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multiset::count() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<int> sample;

    // inserts element
    sample.insert(11);
    sample.insert(11);
    sample.insert(11);
    sample.insert(12);
    sample.insert(13);
    sample.insert(13);
    sample.insert(14);

    cout << "11 occurs " << sample.count(11) << " times";
    cout << "\n12 occurs " << sample.count(13) << " times";
    cout << "\n13 occurs " << sample.count(13) << " times";
    cout << "\n14 occurs " << sample.count(14) << " times";

    return 0;
}
```

**Output:**

```cpp
11 occurs 3 times
12 occurs 2 times
13 occurs 2 times
14 occurs 1 times

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multiset::count() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<char> sample;

    // inserts element
    sample.insert('a');
    sample.insert('a');
    sample.insert('a');
    sample.insert('b');
    sample.insert('b');
    sample.insert('c');
    sample.insert('c');

    cout << "a occurs " << sample.count('a') << " times";
    cout << "\nb occurs " << sample.count('b') << " times";
    cout << "\nc occurs " << sample.count('c') << " times";

    return 0;
}
```

**Output:**

```cpp
a occurs 3 times
b occurs 2 times
c occurs 2 times

```