# c++ STL 中的无序 _multimap reserve()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-reserve-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-reserve-function-in-c-stl/)

**unordered _ multimap::reserve()**是 C++ STL 中的一个内置函数，它将容器( [bucket_count](https://www.geeksforgeeks.org/unordered_multimap-bucket_count-function-in-c-stl/) )中的 bucket 数量设置为最合适的数量，使其至少包含 n 个元素。如果 n 大于当前桶计数乘以**最大装载系数**，容器的桶计数将增加，并强制重新装载。通过调用**用无序 _ 多映射容器预期的大小保留**，可以避免多次重映射。多个重散列是由于容器大小的增加而产生的，这优化了散列表的大小。如果 n 低于该值，该函数可能不起作用。

**语法:**

```cpp
*unordered_multimap_name*.reserve(N)
```

**参数:**该函数接受单个强制参数 ***N*** ，该参数将请求的元素数量指定为最小容量。

**返回值:**函数不返回任何内容。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::reserve()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample1, sample2;

    // the sample1 size is reserved for
    // the bucket to contain a minimum of
    // one elements
    sample1.reserve(1);

    // inserts key and element
    // in sample1
    sample1.insert({ 10, 100 });
    sample1.insert({ 50, 500 });

    // inserts key and element
    // in sample1

    // the sample1 size is reserved for
    // the bucket to contain a minimum of
    // three elements
    sample2.reserve(3);

    sample2.insert({ 20, 200 });
    sample2.insert({ 30, 300 });
    sample2.insert({ 30, 150 });

    cout << "The size of Sample1 is: " << sample1.size();

    cout << "\nKey and Elements of Sample1 are:";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    cout << "\n\nThe size of Sample2 is: " << sample2.size();

    cout << "\nKey and Elements of Sample2 are:";
    for (auto it = sample2.begin(); it != sample2.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    return 0;
}
```

**Output:**

```cpp
The size of Sample1 is: 2
Key and Elements of Sample1 are:{50, 500} {10, 100} 

The size of Sample2 is: 3
Key and Elements of Sample2 are:{30, 150} {30, 300} {20, 200}

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::reserve()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<char, char> sample1, sample2;

    // the sample1 size is reserved for
    // the bucket to contain a minimum of
    // one elements
    sample1.reserve(1);

    // inserts key and element
    // in sample1
    sample1.insert({ 'a', 'A' });
    sample1.insert({ 'g', 'G' });

    // inserts key and element
    // in sample1

    // the sample1 size is reserved for
    // the bucket to contain a minimum of
    // three elements
    sample2.reserve(3);

    sample2.insert({ 'b', 'B' });
    sample2.insert({ 'c', 'C' });
    sample2.insert({ 'd', 'D' });

    cout << "The size of Sample1 is: " << sample1.size();

    cout << "\nKey and Elements of Sample1 are:";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    cout << "\n\nThe size of Sample2 is: " << sample2.size();

    cout << "\nKey and Elements of Sample2 are:";
    for (auto it = sample2.begin(); it != sample2.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    return 0;
}
```

**Output:**

```cpp
The size of Sample1 is: 2
Key and Elements of Sample1 are:{g, G} {a, A} 

The size of Sample2 is: 3
Key and Elements of Sample2 are:{d, D} {c, C} {b, B}

```