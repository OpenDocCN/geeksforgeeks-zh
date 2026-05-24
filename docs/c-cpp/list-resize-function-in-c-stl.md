# c++ STL 中的 list resize()函数

> 原文:[https://www . geesforgeks . org/list-resize-function-in-c-STL/](https://www.geeksforgeeks.org/list-resize-function-in-c-stl/)

**列表::resize()** 是 C++ STL 中的内置函数，用于调整列表容器的大小。它将数字 n 作为参数，并调整列表容器的大小，使其恰好包含 n 个元素。

*   如果列表已经有 n 个以上的元素，那么该函数将从列表中删除除前 n 个元素之外的元素。
*   如果列表包含的元素少于 n 个，则该函数会将元素的不同数量与其默认值相加。
*   该函数还接受参数*值*，如果指定了该参数，并且列表容器中的元素数量小于 n，则该函数将元素添加到列表中，并将它们的值分配给*值*。

**语法**:

```cpp
list_name.resize(int n, value_type val)

```

**参数**:该功能接受两个参数，如下所述。

*   **n** :此参数指定列表需要调整大小的元素数量。
*   **val** :这是一个可选参数，如果指定了该参数，并且列表包含的元素少于 n 个，则该函数会将元素添加到列表中，并将它们的值赋给 *val* 。

**返回值**:该功能不返回值。

下面的程序说明了 C++ STL 中的 list::resize()函数:

```cpp
// CPP program to illustrate the
// list::resize() function
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

    // Resize list to contain less elements
    demoList.resize(2);
    cout << "\n\nList after first resize: ";
    for (auto itr = demoList.begin(); itr != demoList.end(); itr++)
        cout << *itr << " ";

    // Resize list to contain more elements
    demoList.resize(4);
    cout << "\n\nList after second resize: ";
    for (auto itr = demoList.begin(); itr != demoList.end(); itr++)
        cout << *itr << " ";

    // resize list to contain more elements
    // with a specified value
    demoList.resize(5, 50);
    cout << "\n\nList after third resize: ";
    for (auto itr = demoList.begin(); itr != demoList.end(); itr++)
        cout << *itr << " ";

    return 0;
}
```

**Output:**

```cpp
Initial List: 10 20 30 40 

List after first resize: 10 20 

List after second resize: 10 20 0 0 

List after third resize: 10 20 0 0 50

```