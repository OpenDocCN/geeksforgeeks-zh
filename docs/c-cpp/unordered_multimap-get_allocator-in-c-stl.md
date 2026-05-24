# c++ STL 中的无序 _ 多 get _ 分配器

> 原文:[https://www . geesforgeks . org/unordered _ multimap-get _ 分配器-in-c-stl/](https://www.geeksforgeeks.org/unordered_multimap-get_allocator-in-c-stl/)

**[无序 _ 多 map](https://www.geeksforgeeks.org/unordered_multimap-and-its-application/):get _ 分配器()**是 C++ STL 中的一个内置函数，用于获取容器无序 _ 多 map 的分配器。
**语法:**

```cpp
Allocator_type get_allocator()

```

**参数:**此功能不接受任何参数。
**返回值:**返回一个与无序 _ 多映射关联的分配器。

下面的程序说明了**无序 _ 多 map::get _ 分配器()**函数的工作原理。
**例-1:**

```cpp
// CPP program to illustrate
// unordered_multimap get_allocator()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    //'ump' is object of 'unordered_multimap'
    unordered_multimap<int, int> ump;

    //'allocator_type' is inherit in 'unordered_multimap'
    //'u' is object of 'allocator_type'
    unordered_multimap<int, int>::allocator_type u = ump.get_allocator();

    // Comparing the Allocator with Pair<int, int>
    cout << "Is allocator Pair<int, int> : "
         << boolalpha
         << (u == allocator<pair<int, int> >());

    return 0;
}
```

**Output:**

```cpp
Is allocator Pair : true 
```

**示例-2:**

```cpp
// CPP program to illustrate
// unordered_multimap get_allocator()
#include <bits/stdc++.h>
using namespace std;

int main(void)
{
    unordered_multimap<char, int> um;
    pair<const char, int>* a;

    a = um.get_allocator().allocate(8);

    cout << "Allocated size = " << sizeof(*a) * 8 << endl;

    return 0;
}
```

**Output:**

```cpp
Allocated size = 64

```