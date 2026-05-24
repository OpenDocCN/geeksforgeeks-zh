# 在 C++ STL 中列出 back()函数

> 原文:[https://www.geeksforgeeks.org/list-back-function-in-c-stl/](https://www.geeksforgeeks.org/list-back-function-in-c-stl/)

C++ STL 中的 **list::back()** 函数返回列表容器中最后一个元素的直接引用。这个函数不同于 list::end()函数，因为 end()函数只返回最后一个元素的迭代器。

**语法:**

```cpp
list_name.back() 

```

**参数:**该功能不接受任何参数。

**返回值:**该函数返回列表容器 *demo_list* 中最后一个元素的直接引用。

**异常**:这个函数中没有这样的异常，但是在空列表容器中调用这个函数会在 C++ 中产生一个未定义的行为。

下面的程序说明了 list::back()函数。

```cpp
// CPP program to illustrate the
// list::assign() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialization of list
    list<int> demo_list;

    // Adding elements to the list
    demo_list.push_back(10);
    demo_list.push_back(20);
    demo_list.push_back(30);

    // prints the last element of demo_list
    cout << demo_list.back();

    return 0;
}
```

**输出:**

```cpp
30

```