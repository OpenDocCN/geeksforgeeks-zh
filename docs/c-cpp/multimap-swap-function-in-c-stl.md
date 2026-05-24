# c++ STL 中的 multimap swap()函数

> 原文:[https://www . geesforgeks . org/multimap-swap-function-in-c-STL/](https://www.geeksforgeeks.org/multimap-swap-function-in-c-stl/)

**multimap::swap()** 是 C++ STL 中的一个内置函数，它交换两个 multimap 容器。调用 swap()函数后，multimap1 的内容在 multimap2 中，multimap2 的内容在 multimap1 中。

**语法:**

```cpp
multimap1_name.swap(multimap2_name)
```

**参数:**该函数接受一个要与 multimap1_name 交换的参数，

**返回值:**函数不返回任何内容。

```cpp
// C++ function for illustration
// multimap::swap() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    multimap<int, int> mp1, mp2;

    // insert elements in random order
    mp1.insert({ 2, 30 });
    mp1.insert({ 1, 40 });

    mp2.insert({ 10, 60 });
    mp2.insert({ 9, 20 });

    cout << "\nThe multimap1 before applying swap() is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp1.begin(); itr != mp1.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }

    cout << "\nThe multimap2 before applying swap() is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp2.begin(); itr != mp2.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }

    // performs swap operation of two multimap
    mp1.swap(mp2);

    cout << "\nThe multimap1 after applying swap() is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp1.begin(); itr != mp1.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }

    cout << "\nThe multimap2 after applying swap() is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp2.begin(); itr != mp2.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }

    return 0;
}
```