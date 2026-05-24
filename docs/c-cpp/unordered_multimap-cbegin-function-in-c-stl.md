# c++ STL 中无序 _ 多映射 cbegin()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-CBE gin-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-cbegin-function-in-c-stl/)

**无序 _ 多映射::cbegin()** 是 C++ STL 中的一个内置函数，它返回一个指向容器中第一个元素或其桶中第一个元素的*常量*迭代器。

**语法:**

```cpp
*unordered_multimap_name*.cbegin(n)
```

**参数:**函数接受一个参数。如果传递了一个参数，它会返回一个指向桶中第一个元素的常量迭代器。如果没有传递参数，那么它会返回一个常量迭代器，指向无序的 multimap 容器中的第一个元素。

**返回值:**返回一个*常量*迭代器。它不能用于更改无序的 multimap 元素的值。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::cbegin() 
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

    // prints all key and element
    cout << "Key and Elements : \n";
    for (auto it = sample.begin(); it != sample.end(); it++)
        cout << "   " << it->first << "\t      " 
             << it->second << endl;

    auto it = sample.begin();

    // print the first element
    cout << "\nThe first element and key: " 
         << it->first << " ";
    cout << it->second;

    return 0;
}
```

**Output:**

```cpp
Key and Elements : 
   2          3
   2          3
   1          2
   3          4
   3          4

The first element and key: 2 3

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::cbegin(bucket) 
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample;

    // inserts element
    sample.insert({ 1, 2 });
    sample.insert({ 3, 4 });
    sample.insert({ 3, 4 });
    sample.insert({ 2, 3 });
    sample.insert({ 2, 3 });

    // prints all element
    cout << "Key and Elements of first bucket: \n";
    for (auto it = sample.cbegin(1); it != sample.cend(1); it++)
        cout << "   " << it->first << "\t      " 
             << it->second << endl;

    auto it = sample.cbegin(1);

    // print the first element
    cout << "\nThe first element and key in first bucket: "
         << it->first << " ";
    cout << it->second;

    return 0;
}
```

**Output:**

```cpp
Key and Elements of first bucket: 
   1          2

The first element and key in first bucket: 1 2

```