# 在 C++ STL 中列出 max_size()函数

> 原文:[https://www . geesforgeks . org/list-max _ size-function-in-c-STL/](https://www.geeksforgeeks.org/list-max_size-function-in-c-stl/)

**list::max_size()** 是 C++ STL 中的内置函数，返回列表容器可以容纳的最大元素数。

**语法** :

```cpp
list_name.max_size()

```

**参数**:本功能不接受任何参数。

**返回值**:该函数返回列表容器可以容纳的最大元素数。

下面程序举例说明列表::max_size()函数在 C++ STL 中:

```cpp
// CPP program to illustrate the
// list::max_size() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Creating a list
    list<int> demoList;

    // checking the max size of the list
    cout << demoList.max_size();

    return 0;
}
```

**输出:**

```cpp
768614336404564650

```