# c++ STL 中的无序 _ 多集空()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-empty-function-in-cstl/](https://www.geeksforgeeks.org/unordered_multiset-empty-function-in-cstl/)

**无序 _ 多集::空()**是 C++ STL 中的一个内置函数，返回一个布尔值。如果无序多集容器为空，则返回 true。否则，它返回 false。

**语法:**

```cpp
unordered_multiset_name.empty()
```

**参数:**函数不接受任何参数。

**返回值:**返回一个布尔值，表示无序多集是否为空。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multiset::empty() function
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

    // if not empty then print the elements
    if (sample.empty() == false) {
        cout << "Elements: ";

        for (auto it = sample.begin(); it != sample.end(); it++) {
            cout << *it << " ";
        }
    }

    // container is erased completely
    sample.clear();

    if (sample.empty() == true)
        cout << "\nContainer is empty";
    return 0;
}
```

**Output:**

```cpp
Elements: 14 11 11 11 12 13 13 
Container is empty

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multiset::empty() function
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

    // if not empty then print the elements
    if (sample.empty() == false) {
        cout << "Elements: ";

        for (auto it = sample.begin(); it != sample.end(); it++) {
            cout << *it << " ";
        }
    }

    // container is erased completely
    sample.clear();

    if (sample.empty() == true)
        cout << "\nContainer is empty";
    return 0;
}
```

**Output:**

```cpp
Elements: a a b c d d d 
Container is empty

```