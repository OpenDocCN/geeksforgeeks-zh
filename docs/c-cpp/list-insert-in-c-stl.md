# 列表在 C++ STL 中插入()

> 原文:[https://www.geeksforgeeks.org/list-insert-in-c-stl/](https://www.geeksforgeeks.org/list-insert-in-c-stl/)

**列表::insert()** 用于在列表的任意位置插入元素。这个函数需要 3 个元素，位置，要插入的元素数量和要插入的值。如果未提及，元素数量默认设置为 1。

**语法:**

```cpp
insert(pos_iter, ele_num, ele)

```

**参数:**该函数接受三个参数:

*   **pos_iter** :放置在新元素插入的容器中。
*   **ele_num** :要插入的元素数量。每个元素都被初始化为 val 的一个副本。
*   **元素**:要复制(或移动)到插入元素的值。

**返回值:**这个函数返回一个迭代器，指向第一个新插入的元素。

```cpp
// C++ code to demonstrate the working of
// insert() function

#include <iostream>
#include <list> // for list operations
using namespace std;

int main()
{
    // declaring list
    list<int> list1;

    // using assign() to insert multiple numbers
    // creates 3 occurrences of "2"
    list1.assign(3, 2);

    // initializing list iterator to beginning
    list<int>::iterator it = list1.begin();

    // iterator to point to 3rd position
    advance(it, 2);

    // using insert to insert 1 element at the 3rd position
    // inserts 5 at 3rd position
    list1.insert(it, 5);

    // Printing the new list
    cout << "The list after inserting"
         << " 1 element using insert() is : ";
    for (list<int>::iterator i = list1.begin();
         i != list1.end();
         i++)
        cout << *i << " ";

    cout << endl;

    // using insert to insert
    // 2 element at the 4th position
    // inserts 2 occurrences
    // of 7 at 4th position
    list1.insert(it, 2, 7);

    // Printing the new list
    cout << "The list after inserting"
         << " multiple elements "
         << "using insert() is : ";

    for (list<int>::iterator i = list1.begin();
         i != list1.end();
         i++)
        cout << *i << " ";

    cout << endl;
}
```

**Output:**

```cpp
The list after inserting 1 element using insert() is : 2 2 5 2 
The list after inserting multiple elements using insert() is : 2 2 5 7 7 2

```