# c++ STL 中的 `unordered_map::get_allocator`

> 原文: [https://www.geeksforgeeks.org/unordered_map-get_allocator-in-c-stl/](https://www.geeksforgeeks.org/unordered_map-get_allocator-in-c-stl/)

[`unordered_map::get_allocator()`](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/) 是 C++ STL 中的内置函数，用于获取容器 `unordered_map` 的分配器。

## 语法

```cpp
Allocator_type get_allocator()
```

## 参数
此功能不接受任何参数。

## 返回值
返回一个与 `unordered_map` 关联的分配器。

下面的程序清楚地解释了 `unordered_map::get_allocator()` 函数。

## 示例-1

```cpp
// CPP program to illustrate
// unordered_map get_allocator()
#include <bits/stdc++.h>
using namespace std;

int main()
{

//'ump' is object of 'unordered_map'
    unordered_map<int, int> ump;

//'allocator_type' is inherit in 'unordered_map'
    //'u' is object of 'allocator_type'
    unordered_map<int, int>::allocator_type u = ump.get_allocator();

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

## 示例-2

```cpp
// CPP program to illustrate
// unordered_map get_allocator()
#include <bits/stdc++.h>
using namespace std;

int main(void)
{
    unordered_map<char, int> um;
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