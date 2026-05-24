# 在 C++ STL 中列出反向函数

> 原文:[https://www . geesforgeks . org/list-reverse-function-in-c-STL/](https://www.geeksforgeeks.org/list-reverse-function-in-c-stl/)

**列表::reverse()** 是 C++ STL 中的内置函数，用于反转列表容器。它颠倒列表容器中元素的顺序。

**语法** :

```cpp
list_name.reverse()

```

**参数**:本功能不接受任何参数。

**返回值**:该功能不返回值。它只是颠倒了使用它的列表容器中元素的顺序。

下面程序举例说明列表::reverse()函数在 C++ STL 中:

```cpp
// CPP program to illustrate the
// list::reverse() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Creating a list
    list<int> demoList;

    // Adding elements to the list
    demoList.push_back(10);
    demoList.push_back(20);
    demoList.push_back(30);
    demoList.push_back(40);

    // Initial list:
    cout << "Initial List: ";
    for (auto itr = demoList.begin(); itr != demoList.end(); itr++)
        cout << *itr << " ";

    // reversing the list
    demoList.reverse();

    // List after reversing the order of elements
    cout << "\n\nList after reversing: ";
    for (auto itr = demoList.begin(); itr != demoList.end(); itr++)
        cout << *itr << " ";

    return 0;
}
```

**输出:**

```cpp
Initial List: 10 20 30 40 

List after reversing: 40 30 20 10

```