# 列表大小()函数在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/list-size-function-in-c-stl/](https://www.geeksforgeeks.org/list-size-function-in-c-stl/)

**列表::size()** 是 C++ STL 中的内置函数，用于查找列表容器中存在的元素数量。也就是说，它用于查找列表容器的大小。

**语法** :

```cpp
list_name.size();

```

**参数**:本功能不接受任何参数。

**返回值**:该函数返回列表容器*列表名称*中存在的元素数量。

下面程序举例说明了 C++ STL 中的 list::size()函数:

```cpp
// CPP program to illustrate the
// list::size() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Creating a list
    list<int> demoList;

    // Add elements to the List
    demoList.push_back(10);
    demoList.push_back(20);
    demoList.push_back(30);
    demoList.push_back(40);

    // getting size of the list
    int size = demoList.size();

    cout << "The list contains " << size << " elements";

    return 0;
}
```