# 在 C++ STL 中列出空()函数

> 原文:[https://www.geeksforgeeks.org/list-empty-function-in-c-stl/](https://www.geeksforgeeks.org/list-empty-function-in-c-stl/)

**list::empty()** 是 C++ STL 中的一个内置函数，用于检查特定的列表容器是否为空。这个函数不修改列表，它只是检查列表是否为空，即列表的大小是否为零。

**语法:**

```cpp
list_name.empty() 

```

**参数:**这个函数不接受任何参数，它只是检查一个列表容器是否为空。

**返回值:**该函数的返回类型为*布尔型*。它返回*真*是列表容器的大小为零，否则它返回*假*。

下面的程序说明了 list::empty()函数。

```cpp
// CPP program to illustrate the
// list::empty() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Creating a list
    list<int> demoList;

    // check if list is empty
    if (demoList.empty())
        cout << "Empty List\n";
    else
        cout << "Not Empty\n";

    // Add elements to the List
    demoList.push_back(10);
    demoList.push_back(20);
    demoList.push_back(30);
    demoList.push_back(40);

    // check again if list is empty
    if (demoList.empty())
        cout << "Empty List\n";
    else
        cout << "Not Empty\n";

    return 0;
}
```

**输出:**

```cpp
Empty List
Not Empty

```

**注**:该函数在恒定时间复杂度下工作。