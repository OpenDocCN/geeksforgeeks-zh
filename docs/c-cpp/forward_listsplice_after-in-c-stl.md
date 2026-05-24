# c++ STL 中的 forward_list::splice_after()

> 原文:[https://www . geeksforgeeks . org/forward _ list splice _ after-in-c-STL/](https://www.geeksforgeeks.org/forward_listsplice_after-in-c-stl/)

**forward_list::splice _ after()**是 CPP STL 中的一个内置函数，它将第一个+1 到最后一个范围内的元素从一个给定的 forward_list 传输到另一个 forward _ list。元素被插入到参数中位置所指向的元素之后。

**语法:**

```cpp
forwardlist1_name.splice_after(position iterator, forwardlist2_name,
                                    first iterator, last iterator) 

```

**参数:**该函数接受如下指定的四个参数:

*   **位置**–指定前进列表中新元素要插入的位置。
*   **forward list 2 _ name**–指定要从中插入元素的列表。
*   **第一个**–指定迭代器，之后要进行插入。
*   **最后一个**–指定要完成插入的迭代器。

**返回值:**函数没有返回值。

下面的程序演示了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate
// splice_after() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialising the forward lists
    forward_list<int> list1 = { 10, 20, 30, 40 };
    forward_list<int> list2 = { 4, 9 };

    // splice_after operation performed
    // all elements except the first element in list1 is
    // inserted in list 2 between 4 and 9
    list2.splice_after(list2.begin(), list1,  
                  list1.begin(), list1.end());

    cout << "Elements are: " << endl;

    // loop to print the elements of second list
    for (auto it = list2.begin(); it != list2.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
Elements are: 
4 20 30 40 9

```

**程序 2:**

```cpp
// C++ program to illustrate
// splice_after() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialising the forward lists
    forward_list<int> list1 = { 10, 20, 30, 40 };
    forward_list<int> list2 = { 4, 9 };

    // splice_after operation performed
    // all elements of list1 are inserted
    // in list2 between 4 and 9
    list2.splice_after(list2.begin(), list1,
           list1.before_begin(), list1.end());

    cout << "Elements are: " << endl;

    // loop to print the elements of second list
    for (auto it = list2.begin(); it != list2.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
Elements are: 
4 10 20 30 40 9

```