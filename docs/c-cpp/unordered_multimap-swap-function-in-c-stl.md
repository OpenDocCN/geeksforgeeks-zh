# c++ STL 中无序 _ 多映射交换()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-swap-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-swap-function-in-c-stl/)

**无序 _ 多 map::swap()** 是 C++ STL 中的一个内置函数，它交换两个无序 _ 多 map 容器的内容。两个容器的尺寸可以不同。

**语法:**

```cpp
*unordered_multimap_name1*.swap(*unordered_multimap_name2*)
```

**参数:**该函数接受单个强制参数*无序 _ 多 map_name2* ，该参数指定了要与之交换*无序 _ 多 map_name1* 的无序 _ 多 map。

**返回值:**不返回任何东西。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::swap()
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

    cout << "Key and Elements of Sample1 before swap are:";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    cout << "\nKey and Elements of Sample2 before swap are:";
    for (auto it = sample2.begin(); it != sample2.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    // performs swap of two
    // unordered_multimaps
    sample1.swap(sample2);

    cout << "\n\nKey and Elements of Sample1 after swap are:";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    cout << "\nKey and Elements of Sample2 after swap are:";
    for (auto it = sample2.begin(); it != sample2.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    return 0;
}
```

**Output:**

```cpp
Key and Elements of Sample1 before swap are:{50, 500} {10, 100} 
Key and Elements of Sample2 before swap are:{20, 200} {30, 150} {30, 300} 

Key and Elements of Sample1 after swap are:{20, 200} {30, 150} {30, 300} 
Key and Elements of Sample2 after swap are:{50, 500} {10, 100}

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::swap()
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

    cout << "Key and Elements of Sample1 before swap are:";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    cout << "\nKey and Elements of Sample2 before swap are:";
    for (auto it = sample2.begin(); it != sample2.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    // performs swap of two
    // unordered_multimaps
    sample1.swap(sample2);

    cout << "\n\nKey and Elements of Sample1 after swap are:";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    cout << "\nKey and Elements of Sample2 after swap are:";
    for (auto it = sample2.begin(); it != sample2.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    return 0;
}
```

**Output:**

```cpp
Key and Elements of Sample1 before swap are:{g, G} {a, A} 
Key and Elements of Sample2 before swap are:{d, D} {b, B} {c, C} 

Key and Elements of Sample1 after swap are:{d, D} {b, B} {c, C} 
Key and Elements of Sample2 after swap are:{g, G} {a, A}

```