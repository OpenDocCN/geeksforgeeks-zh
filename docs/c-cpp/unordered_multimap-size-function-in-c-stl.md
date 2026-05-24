# c++ STL 中无序 _ 多映射大小()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-size-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-size-function-in-c-stl/)

**无序 _ 多映射::size()** 是 C++ STL 中的内置函数，返回无序 _ 多映射的大小。它表示容器中元素的数量。

**语法:**

```cpp
*unordered_multimap_name*.size()
```

**参数:**函数不接受任何参数。

**返回值:**返回表示容器大小的整数值。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::size()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample1, sample2;

    // inserts key and element
    // in sample1
    sample1.insert({ 10, 100 });
    sample1.insert({ 50, 500 });

    // inserts key and element
    // in sample1
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
Key and Elements of Sample2 are:{20, 200} {30, 150} {30, 300}

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::size()
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

    // inserts key and element
    // in sample1
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
Key and Elements of Sample2 are:{d, D} {b, B} {c, C}

```