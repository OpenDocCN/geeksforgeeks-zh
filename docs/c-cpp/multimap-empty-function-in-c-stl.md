# c++ STL 中的 multimap empty()函数

> 原文:[https://www . geesforgeks . org/multimap-empty-function-in-c-STL/](https://www.geeksforgeeks.org/multimap-empty-function-in-c-stl/)

**multimap::empty()** 是 C++ STL 中的一个布尔类型观察器函数，它告诉容器是否为空。当 multimap 容器为空(即容器的大小为 0)时，此函数返回 true。作为一个观察函数，它不会以任何方式修改多重映射。

**语法:**

```cpp
multimap1.empty()
```

**返回值:**该方法返回一个**布尔**类型的值。当 multimap 为空时返回 true，否则返回 false。

下图程序说明了 multimap::empty()函数:

```cpp
// C++ program to demonstrate
// std::multimap::empty

#include <iostream>
#include <map>

using namespace std;

int main()
{

    // declaring multimap
    multimap<char, int> mmap;

    // checking if mmap is empty or not
    if (mmap.empty())
        cout << "multimap is empty\n";

    // inserting values to mmap
    // thus making it non empty
    mmap.insert(pair<char, int>('a', 26));
    mmap.insert(pair<char, int>('b', 30));
    mmap.insert(pair<char, int>('c', 44));

    // checking that mmap is now not empty
    if (mmap.empty())
        cout << "multimap is empty\n";
    else
        cout << "multimap is not empty\n";

    return 0;
}
```

**输出:**

```cpp
multimap is empty
multimap is not empty

```