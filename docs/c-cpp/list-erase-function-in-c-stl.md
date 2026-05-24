# c++ STL 中的列表擦除()功能

> 原文:[https://www.geeksforgeeks.org/list-erase-function-in-c-stl/](https://www.geeksforgeeks.org/list-erase-function-in-c-stl/)

**列表::erase()** 是 C++ STL 中的内置函数，用于从列表容器中删除元素。此函数可用于从指定的列表容器中移除单个元素或一系列元素。

**语法:**

```cpp
iterator list_name.erase(iterator position)

or,

iterator list_name.erase(iterator first, iterator last)

```

**参数:**该功能可以根据是用于从列表容器中擦除单个元素还是一个范围的元素，接受不同的参数。

*   **Position** : this parameter is used when the function deletes a single element. This parameter refers to an iterator that points to the element that needs to be deleted from the list container.
*   **First** , **Last** : These two parameters are used when the list is used to erase elements from the range. The first of parameter *refers to the iterator pointing to the first element in the range, and the last* of parameter *refers to the iterator pointing to the last element in the range to be erased. This will delete all elements in this range, including the element* pointed by the iterator *first, but not the element* pointed by the iterator *last.*

**返回值:**该函数返回一个迭代器，指向列表容器中的元素，该元素位于从列表容器中删除的最后一个元素之后。

下面程序说明了 list::erase()函数。

**程序 1** :擦除单个元素。

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

**输出:**

```cpp
List before deleting first element: 10 20 30 40 50 
List after deleting first element:20 30 40 50

```

**程序 2** :清除一系列元素。

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

**输出:**

```cpp
List before deleting any element: 10 20 30 40 50 
List after deleting first three elements: 40 50

```

**注**:该函数以线性时间复杂度工作，即从列表容器中擦除的元素数量。