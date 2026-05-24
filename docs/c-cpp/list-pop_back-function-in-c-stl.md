# 在 C++ STL 中列出 pop_back()函数

> 原文:[https://www . geesforgeks . org/list-pop _ back-function-in-c-STL/](https://www.geeksforgeeks.org/list-pop_back-function-in-c-stl/)

**列表::pop_back()** 是 C++ STL 中的内置函数，用于从列表容器的后面移除元素。也就是说，这个函数删除列表容器的最后一个元素。该函数因此将容器的大小减少 1，因为它从列表末尾删除了一个元素。

**语法** :

```cpp
list_name.pop_back();

```

**参数**:该功能不接受任何参数。

**返回值**:这个函数不返回任何东西。

下面程序举例说明列表::pop_back()函数在 C++ STL 中:

```cpp
// CPP program to illustrate the
// list::pop_back() function
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

    // removing an element from the end of List
    // using pop_back
    demoList.pop_back();

    // List after removing element from end
    cout << "\n\nList after removing an element from end: ";
    for (auto itr = demoList.begin(); itr != demoList.end(); itr++)
        cout << *itr << " ";

    return 0;
}
```

**输出:**

```cpp
Initial List: 10 20 30 40 

List after removing an element from end: 10 20 30

```