# c++ STL 中无序 _ 多映射 cend()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-cend-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-cend-function-in-c-stl/)

**unordered _ multimap::cend()**是 C++ STL 中的一个内置函数，它返回一个常量迭代器，指向容器中最后一个元素之后的位置，或者指向它的一个桶中最后一个元素之后的位置。

**语法:**

```cpp
*unordered_multimap_name*.cend(n)
```

**参数:**函数接受一个参数。如果传递了一个参数，它将返回一个常量迭代器，指向其存储桶中最后一个元素之后的位置。如果没有传递参数，那么它返回一个常量迭代器，指向无序多映射容器中最后一个元素之后的位置。

**返回值:**返回常量迭代器。它不能用于修改 unordered_multimap 元素的键和元素。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::cend()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample;

    // inserts key and element
    sample.insert({ 1, 2 });
    sample.insert({ 3, 4 });
    sample.insert({ 3, 4 });
    sample.insert({ 2, 3 });
    sample.insert({ 2, 3 });

    // prints all element
    cout << "Key and Elements:";
    for (auto it = sample.cbegin(); it != sample.cend(); it++)
        cout << "\n   " << it->first << "\t      " 
             << it->second;

    return 0;
}
```

**Output:**

```cpp
Key and Elements:
   2          3
   2          3
   1          2
   3          4
   3          4

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::cend(bucket)
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample;

    // inserts key and element
    sample.insert({ 1, 2 });
    sample.insert({ 3, 4 });
    sample.insert({ 3, 4 });
    sample.insert({ 2, 3 });
    sample.insert({ 2, 3 });

    // prints all element
    cout << "Key and Elements of first bucket:";
    for (auto it = sample.cbegin(1); it != sample.cend(1); it++)
        cout << "\n   " << it->first << "\t      " 
             << it->second;

    return 0;
}
```

**Output:**

```cpp
Key and Elements of first bucket:
   1          2

```