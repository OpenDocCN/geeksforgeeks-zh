# c++ STL 中的多集 find()函数

> 原文:[https://www . geesforgeks . org/multist-find-function-in-c-STL/](https://www.geeksforgeeks.org/multiset-find-function-in-c-stl/)

**多集::find()** 是 C++ STL 中的内置函数，它返回一个迭代器，指向在多集容器中搜索的元素的下界。如果没有找到该元素，则迭代器指向集合中最后一个元素之后的位置。

**语法:**

```cpp
multiset_name.find(element)
```

**参数:**该函数接受一个强制参数*元素*，该元素指定要在多集容器中搜索的元素。

**返回值:**该函数返回一个迭代器，该迭代器指向在多集容器中搜索的元素。如果找不到元素，迭代器会指向多集合中最后一个元素之后的位置。

下面的程序说明了上面的功能。

**程序 1:**

```cpp
// CPP program to demonstrate the
// multiset::find() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    // Initialize multiset
    multiset<int> s;

    s.insert(1);
    s.insert(4);
    s.insert(2);
    s.insert(5);
    s.insert(3);
    s.insert(3);
    s.insert(3);
    s.insert(5);

    cout << "The set elements are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    // iterator pointing to
    // position where 2 is
    auto pos = s.find(3);

    // prints the set elements
    cout << "\nThe set elements after 3 are: ";
    for (auto it = pos; it != s.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
The set elements are: 1 2 3 3 3 4 5 5 
The set elements after 3 are: 3 3 3 4 5 5

```

**程序 2:**

```cpp
// CPP program to demonstrate the
// multiset::find() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    // Initialize multiset
    multiset<char> s;

    s.insert('a');
    s.insert('a');
    s.insert('a');
    s.insert('b');
    s.insert('c');
    s.insert('a');
    s.insert('a');
    s.insert('c');

    cout << "The set elements are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    // iterator pointing to
    // position where 2 is
    auto pos = s.find('b');

    // prints the set elements
    cout << "\nThe set elements after b are: ";
    for (auto it = pos; it != s.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
The set elements are: a a a a a b c c 
The set elements after b are: b c c

```