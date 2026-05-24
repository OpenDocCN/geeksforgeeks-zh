# c++ STL 中的 multimap::crbegin()和 multimap::crend()

> 原文:[https://www . geesforgeks . org/multimapcrbegin-and-multimapcrend-in-c-STL/](https://www.geeksforgeeks.org/multimapcrbegin-and-multimapcrend-in-c-stl/)

*   **multimap::crbegin()** 是 C++ STL 中的内置函数，返回一个引用 multimap 容器中最后一个元素的常量反向迭代器。由于 multimap 容器以有序的方式包含元素，crbegin()将根据容器的排序标准指向最后一个元素。

**语法:**

```cpp
multimap_name.crbegin()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回一个常量反向迭代器，引用 multimap 容器中的最后一个元素。

## c++

```cpp
// C++ program to illustrate
// multimap::crbegin() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    multimap<int, int> mp;

    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 3, 60 });
    mp.insert({ 4, 20 });
    mp.insert({ 5, 50 });

    auto ite = mp.crbegin();
    cout << "The last element is {" << ite->first
    << ", " << ite->second << "}\n";

    // prints the elements
    cout << "\nThe multimap in reverse order is: \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.crbegin(); itr != mp.crend(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }
    return 0;
}
```

**输出:**

```cpp
The last element is {5, 50}

The multimap in reverse order is: 
KEY    ELEMENT
5    50
4    20
3    60
2    30
1    40

```