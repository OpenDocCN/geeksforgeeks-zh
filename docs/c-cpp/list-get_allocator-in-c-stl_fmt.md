# 在 C++ STL 中使用 `list::get_allocator()`

> 原文：`https://www.geeksforgeeks.org/list-get_allocator-in-c-stl/`

`list::get_allocator()` 是 C++ STL 中的一个内置函数，用于获取容器 `list` 的分配器。

## 语法

```cpp
Allocator_type get_allocator()
```

## 参数

该函数不接受任何参数。

## 返回值

返回一个与列表关联的分配器。

下面的程序清楚地解释了 `list::get_allocator()` 函数。

## 示例

### 示例-1

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

**输出：**

```cpp
0 1 2
```

### 示例-2

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

**输出：**

```cpp
Geeks For Geeks
```