# 在 C++ STL 中列出 push_front()函数

> 原文:[https://www . geesforgeks . org/list-push _ front-function-in-c-STL/](https://www.geeksforgeeks.org/list-push_front-function-in-c-stl/)

**list::push_front()** 是 C++ STL 中的一个内置函数，用于在列表容器的前部插入一个元素，就在当前顶部元素之前。该功能还将容器的大小增加了 1。

**语法** :

```cpp
list_name.push_front(dataType value)

```

**参数**:该功能接受单个参数*值*。此参数表示需要插入列表容器前面的元素。

**返回值**:该功能不返回任何内容。

下面程序举例说明列表::push_front()函数在 C++ STL 中:

```cpp
// CPP program to illustrate the
// list::push_front() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Creating a list
    list<int> demoList;

    // Adding elements to the list
    // using push_back()
    demoList.push_back(10);
    demoList.push_back(20);
    demoList.push_back(30);
    demoList.push_back(40);

    // Initial List:
    cout << "Initial List: ";
    for (auto itr = demoList.begin(); itr != demoList.end(); itr++)
        cout << *itr << " ";

    // Adding elements to the front of List
    // using push_front
    demoList.push_front(5);

    // List after adding elements to front
    cout << "\n\nList after adding elements to the front:\n";
    for (auto itr = demoList.begin(); itr != demoList.end(); itr++)
        cout << *itr << " ";

    return 0;
}
```

**输出:**

```cpp
Initial List: 10 20 30 40 

List after adding elements to the front:
5 10 20 30 40

```