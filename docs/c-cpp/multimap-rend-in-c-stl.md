# multi AP 渲染为 C++ STL

> 原文:[https://www.geeksforgeeks.org/multimap-rend-in-c-stl/](https://www.geeksforgeeks.org/multimap-rend-in-c-stl/)

[multimap](https://www.geeksforgeeks.org/multimap-associative-containers-the-c-standard-template-library-stl/):rend()是 C++ STL 中的内置函数，它返回一个反向迭代器，指向 multimap 容器第一个元素之前的理论元素。

**语法**

```cpp
multimap_name.rend()
```

**参数:**函数不取任何参数。

**返回值**该函数返回一个指向多 map 容器反向端的反向迭代器，即指向多 map 第一个元素正前方位置的反向迭代器。

multimap::rend()返回的迭代器不能被取消引用。

以下两个程序说明了该功能

```cpp
// CPP program to illustrate
// multimap::rend()
#include <iostream>
#include <map>
using namespace std;

int main()
{
    multimap<char, int> sample;

    // Insert pairs in the multimap
    sample.insert(make_pair('a', 10));
    sample.insert(make_pair('b', 20));
    sample.insert(make_pair('c', 30));
    sample.insert(make_pair('c', 40));

    // Show content
    for (auto it = sample.rbegin(); it != sample.rend(); it++)
        cout << it->first << " = " << it->second << endl;
}
```

**输出**

```cpp
c = 40
c = 30
b = 20
a = 10
```

**程序 2**

```cpp
// CPP program to illustrate
// multimap::rend()

#include <iostream>
#include <map>
using namespace std;

int main()
{
    multimap<char, int> sample;

    // Insert pairs in the multimap
    sample.insert(make_pair('a', 10));
    sample.insert(make_pair('b', 20));
    sample.insert(make_pair('c', 30));
    sample.insert(make_pair('c', 40));

    // Get the iterator pointing to
    // the preceding position of 1st element of the multimap
    auto it = sample.rend();

    // Get the iterator pointing to
    // the 1st element of the multimap
    it--;
    cout << it->first << " = " << it->second;
}
```

**输出**

```cpp
a = 10

```