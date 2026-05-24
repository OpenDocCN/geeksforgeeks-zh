# c++ STL 中的无序 _ 多集 end()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-end-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-end-function-in-c-stl/)

**无序 _ 多集::end()** 是 C++ STL 中的一个内置函数，它返回一个迭代器，该迭代器指向容器中最后一个元素之后的位置或其桶中最后一个元素之后的位置。

**语法:**

```cpp
unordered_multiset_name.end(n)
```

**参数:**函数接受一个参数。如果传递了一个参数，它会返回一个迭代器，指向桶中最后一个元素之后的位置。如果没有传递参数，那么它会返回一个迭代器，指向无序多集容器中最后一个元素之后的位置。

**返回值:**返回一个迭代器。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multiset::end() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<int> sample;

    // inserts element
    sample.insert(10);
    sample.insert(11);
    sample.insert(15);
    sample.insert(13);
    sample.insert(14);

    cout << "\nElements: ";

    // prints all element till the last
    for (auto it = sample.begin(); it != sample.end(); it++)
        cout << *it << " ";
    return 0;
}
```

**Output:**

```cpp
Elements: 14 13 15 10 11

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multiset::end() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<char> sample;

    // inserts element
    sample.insert('a');
    sample.insert('b');
    sample.insert('c');
    sample.insert('x');
    sample.insert('z');

    cout << "\nElements: ";

    // prints all element
    for (auto it = sample.begin(); it != sample.end(); it++)
        cout << *it << " ";
    return 0;
}
```

**Output:**

```cpp
Elements: z x c a b

```

**程序 3:**

```cpp
// C++ program to illustrate the
// unordered_multiset::end() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<char> sample;

    // inserts element
    sample.insert('a');
    sample.insert('b');
    sample.insert('c');
    sample.insert('x');
    sample.insert('z');

    cout << "\nElements in first bucket: ";

    // prints all element
    for (auto it = sample.begin(1); it != sample.end(1); it++)
        cout << *it << " ";
    return 0;
}
```

**Output:**

```cpp
Elements in first bucket: x c

```