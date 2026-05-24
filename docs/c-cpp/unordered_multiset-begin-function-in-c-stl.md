# c++ STL 中的无序 _ 多集 begin()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-begin-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-begin-function-in-c-stl/)

**无序 _ 多集::begin()** 是 C++ STL 中的内置函数，它返回指向容器中第一个元素或其桶中第一个元素的迭代器。

**语法:**

```cpp
unordered_multiset_name.begin(n)
```

**参数:**函数接受一个参数。如果传递了一个参数，它将返回一个指向桶中第一个元素的迭代器。如果没有传递参数，那么它返回一个迭代器，指向无序多集容器中的第一个元素。

**返回值:**返回一个迭代器。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multiset::begin() function
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

    // print the first element
    cout << "The first element: " << *sample.begin();

    cout << "\nElements: ";

    // prints all element
    for (auto it = sample.begin(); it != sample.end(); it++)
        cout << *it << " ";
    return 0;
}
```

**Output:**

```cpp
The first element: 14
Elements: 14 13 15 10 11

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multiset::begin() function
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

    // print the first element

    auto it = sample.begin();
    cout << "The first element: " << *it;

    it++ ;
    cout << "\nThe second element: " << *it;

    cout << "\nElements: ";

    // prints all element
    for (auto it = sample.begin(); it != sample.end(); it++)
        cout << *it << " ";
    return 0;
}
```

**Output:**

```cpp
The first element: z
The second element: x
Elements: z x c a b

```

**程序 3:**

```cpp
// C++ program to illustrate the
// unordered_multiset::begin() function
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

    // print the first element
    cout << "The first element in first bucket : " << *sample.begin(1);

    cout << "\nElements in first bucket: ";

    // prints all element
    for (auto it = sample.begin(1); it != sample.end(1); it++)
        cout << *it << " ";
    return 0;
}
```

**Output:**

```cpp
The first element in first bucket : x
Elements in first bucket: x c

```