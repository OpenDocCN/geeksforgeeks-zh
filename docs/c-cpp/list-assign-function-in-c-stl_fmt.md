# 在 C++ STL 中列出 `assign()` 函数

> 原文：[https://www.geeksforgeeks.org/list-assign-function-in-c-stl/](https://www.geeksforgeeks.org/list-assign-function-in-c-stl/)

`list::assign()` 是 C++ STL 中的内置函数，用于为列表赋值。它还可以用来将元素从一个列表复制到另一个列表。

## 1. 为列表赋值

**语法：**

```cpp
list_name.assign(count, value)
```

**参数：** 该函数接受两个强制参数，如上语法所示，描述如下：

*   `count`：需要分配给名为 `list_name` 的列表的值的数量。
*   `value`：这是从第一个元素开始将被赋予 `count` 次数的值。如果列表已经包含一些元素，那么这些元素将被参数 `value` 中指定的元素替换。该参数的数据类型必须与 `list_name` 的数据类型相同。

**返回值：** 该函数从列表 `list_name` 中的第一个元素开始，分配 `value` 参数中指定的元素计数 `count` 的次数。这个函数的返回类型是 `void`，它不返回任何值。

下面的程序说明了 `list::assign()` 函数。

```cpp
// CPP program to illustrate the
// list::assign() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialization of list
    list<int> demo_list;

    // Assigning the value 100, 5 times
    // to the list, list_demo.
    demo_list.assign(5, 100);

    // Displaying the list
    for (int itr : demo_list) {
        cout << itr << " ";
    }

    return 0;
}
```

**输出：**

```cpp
100 100 100 100 100
```

## 2. 将现有列表的元素复制到新列表

**语法：**

```cpp
first_list.assign(second_list.begin(), second_list.end());
```

**参数：** 该函数接受两个参数，如上语法所示。第一个参数是第二个列表的开始迭代器，第二个参数是第二个列表的结束迭代器。

**返回值：** 该功能将 `second_list` 复制到 `first_list`。这个函数不返回值。

下面程序举例说明了 `list::assign()` 函数：

```cpp
// CPP program to illustrate the
// list::assign() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialization of list
    list<int> first_list;

    // Initializing second list
    list<int> second_list;

    // Assigning the value 100, 5 times
    // to the second_list.
    second_list.assign(5, 100);

    // Copying second_list to first_list
    first_list.assign(second_list.begin(),
                      second_list.end());

    for (int itr : first_list) {
        cout << itr << " ";
    }

    return 0;
}
```

**输出：**

```cpp
100 100 100 100 100
```