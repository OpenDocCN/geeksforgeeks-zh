# c++ STL 中的多映射::侵位()

> 原文:[https://www.geeksforgeeks.org/multimapemplace-in-c-stl/](https://www.geeksforgeeks.org/multimapemplace-in-c-stl/)

**多映射::侵位()**是 C++ STL 中的内置函数，它将键及其元素插入多映射容器中。它有效地将容器大小增加了一个，因为 multimap 是存储具有相同值的多个键的容器。

**语法:**

```cpp
multimap_name.emplace(key, element)

```

**参数:**该函数接受两个强制参数，如下所述:

*   **Key–** Specifies the key to insert the multi-mapping container.
*   **Element–** Specifies the element to insert the key of the multi-mapping container.

**返回值:**函数不返回任何内容。

```cpp
// C++ program for the illustration of
// multimap::emplace() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    multimap<int, int> mp;

    // insert elements in random order
    mp.emplace(2, 30);
    mp.emplace(1, 40);
    mp.emplace(2, 60);
    mp.emplace(2, 20);
    mp.emplace(1, 50);
    mp.emplace(4, 50);

    // prints the elements
    cout << "\nThe multimap is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); itr++)
        cout << itr->first << "\t" << itr->second << endl;

    return 0;
}
```

**输出:**

```cpp
The multimap is : 
KEY    ELEMENT
1    40
1    50
2    30
2    60
2    20
4    50

```