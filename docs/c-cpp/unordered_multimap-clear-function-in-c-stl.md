# c++ STL 中的无序 _multimap clear()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-clear-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-clear-function-in-c-stl/)

**无序 _ 多 map::clear()** 是 C++ STL 中的内置函数，用于清除无序 _ 多 map 容器的内容。调用函数后，容器的最终大小为 0。

**语法:**

```cpp
*unordered_multimap_name*.clear()
```

**参数:**函数不接受任何参数。

**返回值:**不返回任何内容。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::clear()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample;

    // inserts key an delement
    sample.insert({ 10, 100 });
    sample.insert({ 10, 100 });
    sample.insert({ 20, 200 });
    sample.insert({ 30, 300 });
    sample.insert({ 15, 150 });

    cout << "Key and Elements of multimap are:";

    for (auto it = sample.begin(); it != sample.end(); it++) {
        cout << "\n{" << it->first << ", " << it->second << "}";
    }

    sample.clear();

    cout << "\nSize of container after function call: "
         << sample.size();

    return 0;
}
```

**Output:**

```cpp
Key and Elements of multimap are:
{15, 150}
{30, 300}
{20, 200}
{10, 100}
{10, 100}
Size of container after function call: 0

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::clear()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<char, char> sample;

    // inserts element
    sample.insert({ 'a', 'b' });
    sample.insert({ 'a', 'b' });
    sample.insert({ 'b', 'c' });
    sample.insert({ 'r', 'a' });
    sample.insert({ 'c', 'b' });

    cout << "Key and Elements of multimap are:";

    for (auto it = sample.begin(); it != sample.end(); it++) {
        cout << "\n{" << it->first << ", " << it->second << "}";
    }

    sample.clear();

    cout << "\nSize of container after function call: "
         << sample.size();
    return 0;
}
```

**Output:**

```cpp
Key and Elements of multimap are:
{c, b}
{r, a}
{b, c}
{a, b}
{a, b}
Size of container after function call: 0

```