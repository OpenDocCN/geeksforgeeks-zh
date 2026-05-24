# c++ STL 中的无序 _set max_size()

> 原文:[https://www . geesforgeks . org/unordered _ set-max _ size-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-max_size-in-c-stl/)

**无序 _ 集合::max_size()** 是 C++ STL 中的内置函数，在 **<无序 _ 集合. h >** 中定义，它返回由于系统约束或内部实现，无序 _ 集合容器可以容纳的最大元素数量(即无序 _ 集合的最大大小)。

**语法** :

```cpp
map_name.max_size()

```

**参数:**该功能不接受任何参数。它只是返回容器的最大大小。

**返回值:**此函数返回无序 _ 集合可以容纳的最大元素数。

**异常**:该函数不抛出任何一种异常。

下面的程序举例说明了 C++ 中的无序 _set::max_size()函数:

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

**输出**

```cpp
1152921504606846975

```

**时间复杂度** : O(1)