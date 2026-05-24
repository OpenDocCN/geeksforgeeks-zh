# 在 C++ STL 中设置 get _ 分配器()

> 原文:[https://www.geeksforgeeks.org/set-get_allocator-in-c-stl/](https://www.geeksforgeeks.org/set-get_allocator-in-c-stl/)

**C++ STL** 中的**集合::get _ 分配器()**是一个内置函数，它返回与集合相关联的分配器对象的副本。

**语法:**

```cpp
mulset.get_allocator();
```

**参数:**此功能不接受任何参数。

**返回值:**该函数返回与集合相关联的分配器。

**时间复杂度:** O(1)。

下面是说明 set::get _ 分配器()方法的示例:

**示例 1:** 下面的程序展示了如何使用集合的分配器来分配 7 个元素的数组。

```cpp
// C++ program to demonstrate
// std::set::get_allocator

#include <iostream>
#include <set>

using namespace std;

void input(int* a)
{

    for (int i = 0; i < 7; i++)
        a[i] = i;
}

void output(int* a)
{

    for (int i = 0; i < 7; i++)
        cout << a[i] << " ";

    cout << endl;
}

int main()
{

    // declare set
    set<int> mset;

    // declare int pointer
    int* arr;

    cout << "size of int pointer is: "
         << sizeof(arr) << endl;

    // use allocator of set to allocate array arr.
    arr = mset.get_allocator()
              .allocate(7);

    // insert elements(numbers from 0-6)
    // in the array
    input(arr);

    // produce output from the array
    output(arr);

    // deallocate the memory allotted previously
    mset.get_allocator()
        .deallocate(arr, 7);

    return 0;
}
```

**Output:**

```cpp
size of int pointer is: 8
0 1 2 3 4 5 6

```