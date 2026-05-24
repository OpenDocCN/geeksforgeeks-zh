# 在 C++ STL 中列出 get _ 分配器

> 原文:[https://www.geeksforgeeks.org/list-get_allocator-in-c-stl/](https://www.geeksforgeeks.org/list-get_allocator-in-c-stl/)

**[列表](https://www.geeksforgeeks.org/list-cpp-stl/):get _ 分配器()**是 C++ STL 中的一个内置函数，用于获取容器列表的分配器。
**语法:**

```cpp
Allocator_type get_allocator()

```

**参数:**该功能除任何参数外不存在。
**返回值:**返回一个与列表关联的分配器。

下面的程序清楚地解释了**list::get _ 分配器()**函数。
**例-1:**

```cpp
// C++ program to understand
// about list getallocator method
#include <bits/stdc++.h>

using namespace std;
int main(void)
{
    // Creating a container of type list
    list<int> mylist;

    // creating a pointer of type int
    int* array;

    // creating array using mylist get_allocator
    array = mylist.get_allocator().allocate(3);

    // inserting some data into the created array
    for (int i = 0; i < 3; i++)
        array[i] = i;

    // printing details of the created array
    for (int i = 0; i < 3; i++)
        cout << array[i] << " ";
}
```

**Output:**

```cpp
0 1 2

```

**示例-2:**

```cpp
// C++ program to understand
// about list getallocator method
#include <bits/stdc++.h>

using namespace std;
int main(void)
{
    // Creating a container of type list
    list<string> mylist;

    // creating a pointer of type int
    string* array;

    // creating array using mylist get_allocator
    array = mylist.get_allocator().allocate(3);

    // inserting some data into array
    array[0] = "Geeks";
    array[1] = "For";
    array[2] = "Geeks";

    // printing details of array
    for (int i = 0; i < 3; i++)
        cout << array[i] << " ";
}
```

**Output:**

```cpp
Geeks For Geeks

```