# c++ STL 中的 map get _ 分配器

> 原文:[https://www.geeksforgeeks.org/map-get_allocator-in-c-stl/](https://www.geeksforgeeks.org/map-get_allocator-in-c-stl/)

**[映射](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/):get _ 分配器()**是 C++ STL 中的内置函数，用于获取容器映射的分配器。
**语法:**

```cpp
Allocator_type get_allocator()

```

**参数:**此功能不接受任何参数。
**返回值:**返回一个与地图关联的分配器。

下面的程序清楚地解释了**映射::get _ 分配器()**函数。
**例-1:**

```cpp
// CPP program to illustrate
// map get_allocator()
#include <bits/stdc++.h>
using namespace std;
int main()
{

    //'mp' is object of 'map'
    map<int, int> mp;

    //'allocator_type' is inherit in 'map'
    //'m' is object of 'allocator_type'
    map<int, int>::allocator_type m = mp.get_allocator();

    // Comparing the Allocator with Pair<int, int>
    cout << "Is allocator Pair<int, int> : "
         << boolalpha
         << (m == allocator<pair<int, int> >());

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
// map get_allocator()
#include <bits/stdc++.h>
using namespace std;

int main(void)
{
    map<char, int> m;
    pair<const char, int>* a;

    a = m.get_allocator().allocate(8);

    cout << "Allocated size = " << sizeof(*a) * 8 << endl;

    return 0;
}
```

**Output:**

```cpp
Allocated size = 64

```