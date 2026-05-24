# 在 C++ STL 中列出 remove()函数

> 原文:[https://www . geesforgeks . org/list-remove-function-in-c-STL/](https://www.geeksforgeeks.org/list-remove-function-in-c-stl/)

**列表::remove()** 是 C++ STL 中的内置函数，用于从列表容器中移除元素。它移除与值比较的元素。它将一个值作为参数，并从列表容器中移除所有元素，这些元素的值等于在函数的参数中传递的值。

**语法:**

```cpp
list_name.remove(val) 

```

**参数:**该函数接受单个参数*值*，该值是指需要从列表中删除的元素的值。remove()函数将从列表中删除所有值等于 val 的元素。

**返回值:**该函数不返回值。

下面的程序说明了 list::remove()函数。

```cpp
// CPP program to illustrate the
// list::remove() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Creating a list
    list<int> demoList;

    // Add elements to the List
    demoList.push_back(10);
    demoList.push_back(20);
    demoList.push_back(20);
    demoList.push_back(30);
    demoList.push_back(40);

    // List before removing elements
    cout << "List before removing elements: ";
    for (auto itr = demoList.begin();
         itr != demoList.end(); itr++) {
        cout << *itr << " ";
    }

    // delete all elements with value 20
    demoList.remove(20);

    // List after removing elements
    cout << "\nList after removing elements: ";
    for (auto itr = demoList.begin();
         itr != demoList.end(); itr++) {
        cout << *itr << " ";
    }

    return 0;
}
```

**输出:**

```cpp
List before removing elements: 10 20 20 30 40 
List after removing elements: 10 30 40

```

**注**:该函数以线性时间复杂度工作。