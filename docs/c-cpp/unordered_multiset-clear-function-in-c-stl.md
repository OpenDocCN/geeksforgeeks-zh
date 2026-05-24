# c++ STL 中的无序 _ 多集 clear()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-clear-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-clear-function-in-c-stl/)

**无序 _ 多集::clear()** 是 C++ STL 中的内置函数，用于清除无序 _ 多集容器的内容。调用函数后，容器的最终大小为 0。

**语法:**

```cpp
unordered_multiset_name.clear()
```

**参数:**函数不接受任何参数。

**返回值:**不返回任何内容。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multiset::clear() function
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

    cout << "Elements: ";

    for (auto it = sample.begin(); it != sample.end(); it++) {
        cout << *it << " ";
    }

    sample.clear();

    cout << "\nSize of container after function call: " 
         << sample.size();

    return 0;
}
```

**Output:**

```cpp
Elements: 14 11 11 11 12 13 13 
Size of container after function call: 0

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multiset::clear() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<int> sample;

    // inserts element
    sample.insert(1);
    sample.insert(1);
    sample.insert(1);
    sample.insert(2);
    sample.insert(3);
    sample.insert(4);
    sample.insert(3);

    cout << "Elements: ";

    for (auto it = sample.begin(); it != sample.end(); it++) {
        cout << *it << " ";
    }

    sample.clear();

    cout << "\nSize of container after function call: " 
         << sample.size();

    return 0;
}
```

**Output:**

```cpp
Elements: 1 1 1 2 3 3 4 
Size of container after function call: 0

```