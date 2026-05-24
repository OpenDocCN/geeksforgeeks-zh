# c++ STL 中的无序 _ 多集 cbegin()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-CBE gin-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-cbegin-function-in-c-stl/)

**无序 _ 多集::cbegin()** 是 C++ STL 中的内置函数，它返回指向容器中第一个元素或其桶中第一个元素的常量迭代器。

**语法:**

```cpp
unordered_multiset_name.cbegin(n)
```

**参数:**函数接受一个参数。如果传递了一个参数，它将返回一个指向桶中第一个元素的常量迭代器。如果没有传递参数，那么它会返回一个常量迭代器，指向无序多集容器中的第一个元素。

**返回值:**返回常量迭代器。它不能用于更改无序多集元素的值。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multiset::cbegin() function
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

    // prints all element
    cout << "Elements: ";
    for (auto it = sample.cbegin(); it != sample.cend(); it++)
        cout << *it << " ";

    auto it = sample.cbegin();

    // print the first element
    cout << "\nThe first element: " << *it;

    return 0;
}
```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multiset::cbegin() function
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
    auto it = sample.cbegin();
    cout << "The first element: " << *it;

    it++ ;
    cout << "\nThe second element: " << *it;

    cout << "\nElements: ";

    // prints all element
    for (auto it = sample.cbegin(); it != sample.cend(); it++)
        cout << *it << " ";
    return 0;
}
```

**程序 3:**

```cpp
// C++ program to illustrate the
// unordered_multiset::cbegin() function
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
    cout << "The first element in first bucket : " << *sample.cbegin(1);

    cout << "\nElements in first bucket: ";

    // prints all element
    for (auto it = sample.cbegin(1); it != sample.cend(1); it++)
        cout << *it << " ";
    return 0;
}
```