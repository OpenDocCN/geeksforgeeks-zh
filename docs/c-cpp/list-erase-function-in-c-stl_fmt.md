# C++ STL 中的 list::erase() 功能

> 原文: [https://www.geeksforgeeks.org/list-erase-function-in-c-stl/](https://www.geeksforgeeks.org/list-erase-function-in-c-stl/)

`list::erase()` 是 C++ STL 中的内置函数，用于从 `list` 容器中删除元素。此函数可用于从指定的列表容器中移除单个元素或一系列元素。

## 语法

```cpp
iterator list_name.erase(iterator position)

or,

iterator list_name.erase(iterator first, iterator last)
```

## 参数

该功能可以根据是用于从列表容器中擦除单个元素还是一个范围的元素，接受不同的参数。

*   `position`：此参数用于函数删除单个元素时。它指向需要从列表容器中删除的元素。
*   `first`，`last`：这两个参数用于擦除一个范围的元素。`first` 参数指向范围中的第一个元素，`last` 参数指向范围中要被擦除的最后一个元素（不包含此元素）。这将删除此范围内的所有元素，包括迭代器 `first` 指向的元素，但不包括迭代器 `last` 指向的元素。

## 返回值

该函数返回一个迭代器，指向列表容器中位于被删除的最后一个元素之后的元素。

下面程序说明了 `list::erase()` 函数。

## 程序 1：擦除单个元素

```cpp
// CPP program to illustrate the
// list::erase() function
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
    demoList.push_back(50);

    // Printing elements of list before deleting
    // first element
    cout << "List before deleting first element: ";
    for (auto itr = demoList.begin();
         itr != demoList.end(); itr++) {
        cout << *itr << " ";
    }

    // Creating iterator to point to first
    // element in the list
    list<int>::iterator itr = demoList.begin();

    // deleting the first element
    demoList.erase(itr);

    // Printing elements of list after deleting
    // first element
    cout << "\nList after deleting first element:";
    for (auto itr = demoList.begin();
         itr != demoList.end(); itr++) {
        cout << *itr << " ";
    }

    return 0;
}
```

**输出：**

```cpp
List before deleting first element: 10 20 30 40 50 
List after deleting first element:20 30 40 50
```

## 程序 2：清除一系列元素

```cpp
// CPP program to illustrate the
// list::erase() function
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
    demoList.push_back(50);

    // Printing elements of list before deleting
    // any element
    cout << "List before deleting any element: ";
    for (auto itr = demoList.begin();
         itr != demoList.end(); itr++) {
        cout << *itr << " ";
    }

    // Creating iterators of the list
    list<int>::iterator itr1, itr2;
    itr1 = demoList.begin();
    itr2 = demoList.begin();

    // Incrementing itr2 by 3 positions
    advance(itr2, 3);

    // deleting range of elements from index [0, 3)
    demoList.erase(itr1, itr2);

    // Printing elements of list after deleting
    // range of elements from [0, 3)
    cout << "\nList after deleting first three elements: ";
    for (auto itr = demoList.begin();
         itr != demoList.end(); itr++) {
        cout << *itr << " ";
    }

    return 0;
}
```

**输出：**

```cpp
List before deleting any element: 10 20 30 40 50 
List after deleting first three elements: 40 50
```

**注**：该函数以线性时间复杂度工作，即与从列表容器中擦除的元素数量成正比。