# 如何在 C++ STL 中用构造函数创建列表

> 原文:[https://www . geesforgeks . org/如何使用 c-stl 中的构造函数创建列表/](https://www.geeksforgeeks.org/how-to-create-a-list-with-constructor-in-c-stl/)

[列表](https://www.geeksforgeeks.org/list-cpp-stl/)是允许非连续内存分配的序列容器。与向量相比，列表遍历速度慢，但是一旦找到位置，插入和删除就很快。通常，当我们说一个列表时，我们说的是双链表。为了实现单链表，我们使用正向链表。

在 C++ 中，可以借助构造函数创建一个列表。做这件事的语法是:
**语法:**

```cpp
list<type> list_name(size_of_list, value_to_be_inserted);
```

下面的程序展示了如何在 C++ 中用构造函数创建一个列表。

**程序 1:**

```cpp
#include <iostream>
#include <list>
using namespace std;

// Function to print the list
void printList(list<int> mylist)
{

    // Get the iterator
    list<int>::iterator it;

    // printing all the elements of the list
    for (it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;
    cout << '\n';
}

int main()
{
    // Create a list with the help of constructor
    // This will insert 100 10 times in the list
    list<int> myList(10, 100);

    printList(myList);

    return 0;
}
```

**Output:**

```cpp
100 100 100 100 100 100 100 100 100 100

```

**程序 2:**

```cpp
#include <bits/stdc++.h>
using namespace std;

// Function to print the list
void printList(list<string> mylist)
{

    // Get the iterator
    list<string>::iterator it;

    // printing all the elements of the list
    for (it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;
    cout << '\n';
}

int main()
{
    // Create a list with the help of constructor
    // This will insert Geeks 5 times in the list
    list<string> myList(5, "Geeks");

    printList(myList);

    return 0;
}
```

**Output:**

```cpp
Geeks Geeks Geeks Geeks Geeks

```