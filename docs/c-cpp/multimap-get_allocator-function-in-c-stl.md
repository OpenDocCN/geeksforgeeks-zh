# c++ STL 中的 multimap get _ 分配器()函数

> 原文:[https://www . geesforgeks . org/multimap-get _ 分配器-function-in-c-stl/](https://www.geeksforgeeks.org/multimap-get_allocator-function-in-c-stl/)

**多映射::get _ 分配器()**是 C++ 中 STL 中的一个函数，它返回与这个多映射相关联的分配器对象的副本。

**语法:**

```cpp
multimap.get_allocator()

```

**返回值:**这个函数返回与这个多映射相关的分配器对象的副本。

下面的例子说明 get _ 分配器()方法:

**示例:**

```cpp
// C++ program demonstrate
// multimap::get_allocator()

#include <iostream>
#include <map>
using namespace std;

int main()
{
    int psize;
    multimap<char, int> mm;
    pair<const char, int>* p;

    // allocate an array of 5 elements
    // using mm's allocator:
    p = mm.get_allocator().allocate(5);

    // assign some values to array
    psize = sizeof(multimap<char, int>::value_type) * 5;

    cout << "The size of allocated array is "
         << psize << " bytes.\n";

    mm.get_allocator().deallocate(p, 5);

    return 0;
}
```

**Output:**

```cpp
The size of allocated array is 40 bytes.

```

**例 2:**

```cpp
// C++ program to demonstrate
// multimap::get_allocator()

#include <iostream>
#include <map>
using namespace std;

int main()
{
    int psize;

    multimap<char, int> mm;
    pair<const char, int>* p;

    // allocate an array of 10 elements
    // using mm's allocator:

    p = mm.get_allocator().allocate(10);

    // assign some values to array
    psize = sizeof(multimap<char, int>::value_type) * 10;

    cout << "The size of allocated array is "
         << psize << " bytes.\n";

    mm.get_allocator().deallocate(p, 10);

    return 0;
}
```

**Output:**

```cpp
The size of allocated array is 80 bytes.

```