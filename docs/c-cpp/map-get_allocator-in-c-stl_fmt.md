# map::get_allocator()

> 原文：[https://www.geeksforgeeks.org/map-get_allocator-in-c-stl/](https://www.geeksforgeeks.org/map-get_allocator-in-c-stl/)

`map::get_allocator()` 是 C++ STL 中的内置函数，用于获取容器 `map` 的分配器。

## 语法

```cpp
Allocator_type get_allocator()
```

## 参数

此函数不接受任何参数。

## 返回值

返回一个与 `map` 关联的分配器。

下面的程序清楚地解释了 `map::get_allocator()` 函数。

## 示例-1

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

**输出：**

```cpp
Is allocator Pair : true 
```

## 示例-2

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

**输出：**

```cpp
Allocated size = 64
```