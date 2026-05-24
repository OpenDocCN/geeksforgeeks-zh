# C++ STL 中无序多映射 `begin()` 和 `end()` 函数

> 原文: [https://www.geeksforgeeks.org/unordered_multimap-begin-and-end-function-in-c-stl/](https://www.geeksforgeeks.org/unordered_multimap-begin-and-end-function-in-c-stl/)

## 1. `unordered_multimap::begin()`

`unordered_multimap::begin()` 是 C++ STL 中的一个内置函数，它返回一个迭代器，指向容器中的第一个元素，或者指向其某个存储桶中的第一个元素。

**语法:**

```cpp
*unordered_multimap_name*.begin(n)
```

**参数:** 函数接受一个参数。如果传递了一个参数，它将返回一个指向桶中第一个元素的迭代器。如果没有传递参数，那么它会返回一个常量迭代器，指向无序的 multimap 容器中的第一个元素。

**返回值:** 返回一个迭代器。它不能用于更改无序的 multimap 元素的值。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::begin() function
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
    cout << "Key and Elements: \n";
    for (auto it = sample.begin(); it != sample.end(); it++)
        cout << "   " << it->first << "\t      "
             << it->second << endl;

    auto it = sample.begin();

    // print the first element
    cout << "\nThe first key and element: "
         << it->first << " ";
    cout << it->second;

    return 0;
}
```

**Output:**

```cpp
Key and Elements: 
   2          3
   2          3
   1          2
   3          4
   3          4

The first key and element: 2 3
```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::begin(bucket) function
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
    for (auto it = sample.begin(1); it != sample.end(1); it++)
        cout << "   " << it->first << "\t      "
             << it->second << endl;

    auto it = sample.begin(1);

    // print the first element
    cout << "\nThe first key and element in first bucket: "
         << it->first << " ";
    cout << it->second;

    return 0;
}
```

**Output:**

```cpp
Key and Elements of first bucket: 
   1          2

The first key and element in first bucket: 1 2
```

## 2. `unordered_multimap::end()`

`unordered_multimap::end()` 是 C++ STL 中的一个内置函数，它返回一个迭代器，指向容器中最后一个元素之后的位置，或者指向其某个存储桶中最后一个元素之后的位置。

**语法:**

```cpp
*unordered_multimap_name*.end(n)
```

**参数:** 函数接受一个参数。如果传递了一个参数，它将返回一个迭代器，指向其存储桶中最后一个元素之后的位置。如果没有传递参数，那么它返回一个迭代器，指向无序多映射容器中最后一个元素之后的位置。

**返回值:** 返回一个迭代器。它不能用于更改无序的 multimap 元素的值。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::end() function
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
    cout << "Key and Elements: \n";
    for (auto it = sample.begin(); it != sample.end(); it++)
        cout << "   " << it->first << "\t      "
             << it->second << endl;

    return 0;
}
```

**Output:**

```cpp
Key and Elements: 
   2          3
   2          3
   1          2
   3          4
   3          4
```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::end(bucket) function
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
    for (auto it = sample.begin(1); it != sample.end(1); it++)
        cout << "   " << it->first << "\t      "
             << it->second << endl;

    return 0;
}
```

**Output:**

```cpp
Key and Elements of first bucket: 
   1          2
```