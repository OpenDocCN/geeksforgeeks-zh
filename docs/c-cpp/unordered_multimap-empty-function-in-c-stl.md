# c++ STL 中无序 _multimap 空()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-empty-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-empty-function-in-c-stl/)

**unordered _ multimap::empty()**是 C++ STL 中的一个内置函数，它返回一个布尔值。如果无序的 multimap 容器为空，则返回 true。否则，它返回 false。

**语法:**

```cpp
*unordered_multimap_name*.empty()
```

**参数:**函数不接受任何参数。

**返回值:**返回一个布尔值，表示无序多映射是否为空。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::empty() function
#include <iostream>
#include <unordered_map>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample;

    // inserts key and element
    sample.insert({ 1, 2 });
    sample.insert({ 1, 2 });
    sample.insert({ 2, 3 });
    sample.insert({ 3, 4 });
    sample.insert({ 5, 6 });

    // if not empty then print the elements
    if (sample.empty() == false) {
        cout << "Key and Elements: ";

        for (auto it = sample.begin(); it != sample.end(); it++) {
            cout << "{" << it->first << ":" << it->second << "} ";
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
Key and Elements: {5:6} {3:4} {2:3} {1:2} {1:2} 
Container is empty

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::empty()
#include <iostream>
#include <unordered_map>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<char, char> sample;

    // inserts element
    sample.insert({ 'a', 'b' });
    sample.insert({ 'a', 'b' });
    sample.insert({ 'g', 'd' });
    sample.insert({ 'r', 'e' });
    sample.insert({ 'g', 'd' });

    // if not empty then print the elements
    if (sample.empty() == false) {
        cout << "Key and elements: ";

        for (auto it = sample.begin(); it != sample.end(); it++) {
            cout << "{" << it->first << ":" << it->second << "} ";
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
Key and elements: {r:e} {g:d} {g:d} {a:b} {a:b} 
Container is empty

```