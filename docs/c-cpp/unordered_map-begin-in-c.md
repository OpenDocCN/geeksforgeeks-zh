# c++ 中的无序 _map begin()

> 原文:[https://www.geeksforgeeks.org/unordered_map-begin-in-c/](https://www.geeksforgeeks.org/unordered_map-begin-in-c/)

**无序映射::begin()** 是 C++ STL 中的一个内置函数，它返回一个迭代器，指向无序映射容器或其任何桶中的第一个元素。

*   **无序 _ 映射容器中第一个元素的语法:**

```cpp
*unordered_map*.begin()
```

**参数:**此功能不接受任何参数。
**返回值:**函数返回一个迭代器，指向无序 _map 容器中的第一个元素。
**注意:**在无序地图中，没有特定的元素被认为是第一个元素。
以下程序说明上述功能。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate the
// unordered_map::begin() function
// when first element of the container
// is to be returned as iterator
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Declaration
    unordered_map<std::string, std::string> mymap;

    // Initialisation
    mymap = { { "Australia", "Canberra" },
              { "U.S.", "Washington" },
              { "France", "Paris" } };

    // Iterator pointing to the first element
    // in the unordered map
    auto it = mymap.begin();

    // Prints the elements of the first element in map
    cout << it->first << " " << it->second;

    return 0;
}
```

**Output:** 

```cpp
France Paris
```

*   **无序 _ 映射桶中第一个元素的语法:**

```cpp
*unordered_map*.begin( n )
```

**参数:**该函数接受一个强制参数 *n* ，该参数指定要返回其第一个元素的迭代器的桶号。
**返回值:**函数返回一个迭代器，指向第 n 个桶中的第一个元素。
以下程序说明上述功能。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate the
// unordered_map::begin() function
// when first element of n-th container
// is to be returned as iterator
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Declaration
    unordered_map<std::string, std::string> mymap;

    // Initialisation
    mymap = { { "Australia", "Canberra" },
            { "U.S.", "Washington" }, { "France", "Paris" } };

    // Iterator pointing to the first element
    // in the n-th bucket
    auto it = mymap.begin(0);

    // Prints the elements of the n-th bucket
    cout << it->first << " " << it->second;

    return 0;
}
```

**Output:** 

```cpp
U.S. Washington
```