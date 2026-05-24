# c++ STL 中的无序 _ 多集 find()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-find-function-in-cstl/](https://www.geeksforgeeks.org/unordered_multiset-find-function-in-cstl/)

**无序 _ 多集::find()** 是 C++ STL 中的一个内置函数，它返回一个迭代器，该迭代器指向具有元素*值*的位置。如果元素不包含元素*值*，那么它返回一个迭代器，指向容器中最后一个元素之后的位置。

**语法:**

```cpp
unordered_multiset_name.find(val)
```

**参数:**函数接受一个强制参数*值*，其位置的迭代器将被返回。

**返回值:**返回一个迭代器，该迭代器指向*值*所在的位置。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multiset::find() function
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

    // find the position of 500 and print
    auto it = sample.find(500);
    if (it != sample.end())
        cout << *it << endl;
    else
        cout << "500 not found\n";

    // find the position of 300 and print
    it = sample.find(300);
    if (it != sample.end())
        cout << *it << endl;
    else
        cout << "300 not found\n";

    // find the position of 100 and print
    it = sample.find(100);
    if (it != sample.end())
        cout << *it << endl;
    else
        cout << "100 not found\n";

    return 0;
}
```

**Output:**

```cpp
500
300 not found
100

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multiset::find() function
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

    // find the position of 'a' and print
    auto it = sample.find('a');
    if (it != sample.end())
        cout << *it << endl;
    else
        cout << "a not found\n";

    // find the position of 'z' and print
    it = sample.find('z');
    if (it != sample.end())
        cout << *it << endl;
    else
        cout << "z not found\n";

    return 0;
}
```

**Output:**

```cpp
a
z not found

```