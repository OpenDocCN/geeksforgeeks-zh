# 在 C++ STL 中列出 push_back()函数

> 原文:[https://www . geesforgeks . org/list-push _ back-function-in-c-STL/](https://www.geeksforgeeks.org/list-push_back-function-in-c-stl/)

C++ STL 中的 **list:push_back()** 函数用于在现有列表容器中添加新元素。它将待添加的元素作为参数，并将其添加到列表容器中。

**语法:**

```cpp
list_name.push_back(value) 

```

**参数:**该功能接受单个参数，该参数为强制*值*。这是指需要添加到列表中的元素，list_name。

**返回值:**该函数的返回类型为 void，不返回任何值。

下面的程序说明了 list::push_back()函数。

```cpp
// CPP program to illustrate the
// list::push_back() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Initialization of list
    list<int> demo_list;

    // intital size of list
    cout << "Initial Size of the list: "
         << demo_list.size() << endl;

    // Adding elements to the list
    // using push_back function
    demo_list.push_back(10);
    demo_list.push_back(20);
    demo_list.push_back(30);

    // Size of list after adding
    // some elements
    cout << "Size of list after adding three "
         << "elements: " << demo_list.size();

    return 0;
}
```

**输出:**

```cpp
Initial Size of the list: 0
Size of list after adding three elements: 3

```