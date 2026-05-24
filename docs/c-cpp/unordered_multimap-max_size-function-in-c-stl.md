# c++ STL 中的无序 _ 多映射 max_size()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-max _ size-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-max_size-function-in-c-stl/)

**无序 _ 多 map::max_size()** 是 C++ STL 中的内置函数，返回无序 _ 多 map 容器可以容纳的最大元素数。

**语法:**

```cpp
*unordered_multimap_name*.max_size()
```

**参数:**函数不接受任何参数。

**返回值:**它返回一个整数值，表示容器可以容纳的元素的最大大小。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::max_size()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample1;

    // inserts key and element
    // in sample1
    sample1.insert({ 10, 100 });
    sample1.insert({ 50, 500 });

    cout << "The max number of elements that sample1 can hold: "
         << sample1.size();

    cout << "\nKey and Elements of Sample1 are:";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    return 0;
}
```

**Output:**

```cpp
The max number of elements that sample1 can hold: 2
Key and Elements of Sample1 are:{50, 500} {10, 100}

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::max_size()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<char, char> sample1, sample2;

    // inserts key and element
    // in sample1
    sample1.insert({ 'a', 'A' });
    sample1.insert({ 'g', 'G' });

    cout << "The max number of elements that sample1 can hold: "
         << sample1.size();

    cout << "\nKey and Elements of Sample1 are:";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    return 0;
}
```

**Output:**

```cpp
The max number of elements that sample1 can hold: 2
Key and Elements of Sample1 are:{g, G} {a, A}

```