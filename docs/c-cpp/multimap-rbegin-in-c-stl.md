# c++ STL 中的多映射 rbegin

> 原文:[https://www.geeksforgeeks.org/multimap-rbegin-in-c-stl/](https://www.geeksforgeeks.org/multimap-rbegin-in-c-stl/)

[multimap](https://www.geeksforgeeks.org/multimap-associative-containers-the-c-standard-template-library-stl/) ::rbegin()是 C++ STL 中的内置函数，它返回一个指向容器最后一个元素的迭代器。
**语法:**

```cpp
multimap_name.rbegiin()

```

**参数:**函数不取任何参数。
**返回值:**函数返回一个指向容器最后一个元素的反向迭代器。
( **注意:**反向迭代器向后迭代，即当它们增加时，它们向容器的开头移动)

以下两个程序说明了该功能。

**程序 1**

```cpp
// CPP program to illustrate
// multimap::rbegin()

#include <iostream>
#include <map>
using namespace std;

int main()
{
    multimap<char, int> sample;

    // Insert pairs in the multimap
    sample.insert(make_pair('a', 10));
    sample.insert(make_pair('b', 20));
    sample.insert(make_pair('b', 30));
    sample.insert(make_pair('c', 40));
    sample.insert(make_pair('c', 50));

    // Get the last element by
    // multimap::rbegin()
    cout << sample.rbegin()->first << " = " << sample.rbegin()->second;
}
```

**输出**

```cpp
c = 50

```

**程序 2**

```cpp
// CPP program to illustrate
// multimap::rbegin()

#include <iostream>
#include <map>
using namespace std;

int main()
{
    multimap<char, int> sample;

    // Insert pairs in the multimap
    sample.insert(make_pair('a', 10));
    sample.insert(make_pair('b', 20));
    sample.insert(make_pair('b', 30));
    sample.insert(make_pair('c', 40));
    sample.insert(make_pair('c', 50));

    // Show content of the multimap
    for (auto it = sample.rbegin(); it != sample.rend(); it++)
        cout << it->first << " = " << it->second << endl;
}
```

**输出**

```cpp
c = 50
c = 40
b = 30
b = 20
a = 10

```