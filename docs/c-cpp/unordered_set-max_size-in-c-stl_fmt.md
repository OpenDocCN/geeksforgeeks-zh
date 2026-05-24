# C++ STL 中的 `unordered_set::max_size()`

> 原文：[https://www.geeksforgeeks.org/unordered_set-max_size-in-c-stl/](https://www.geeksforgeeks.org/unordered_set-max_size-in-c-stl/)

`unordered_set::max_size()` 是 C++ STL 中的内置函数，在 `<unordered_set.h>` 中定义，它返回由于系统约束或内部实现，`unordered_set` 容器可以容纳的最大元素数量（即 `unordered_set` 的最大大小）。

## 语法

```cpp
map_name.max_size()
```

## 参数

该功能不接受任何参数。它只是返回容器的最大大小。

## 返回值

此函数返回 `unordered_set` 可以容纳的最大元素数。

## 异常

该函数不抛出任何一种异常。

## 示例

下面的程序举例说明了 C++ 中的 `unordered_set::max_size()` 函数：

```cpp
// C++ program to illustrate the
// unordered_set::max_size function
#include <iostream>
#include <unordered_set>
using namespace std;

int main()
{
    // declaration
    unordered_set<int> sample;

    // Get the maximum size of the unordered_set
    cout << sample.max_size();

    return 0;
}
```

## 输出

```cpp

```

## 时间复杂度

O(1)