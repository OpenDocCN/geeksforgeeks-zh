# forward_list::operator=在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/forward_listoperator-c-stl/](https://www.geeksforgeeks.org/forward_listoperator-c-stl/)

[STL 中的正向列表](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/)实现单链表。前向列表是从 C++ 11 引入的，对于插入、移除和移动操作(如排序)比其他容器更有用，并且允许元素的时间常数插入和移除。它与列表的不同之处在于转发列表只跟踪下一个元素的位置，而列表同时跟踪下一个和上一个元素。

**forward_list::operator=**

该运算符用于通过替换现有内容向容器分配新内容。
还会根据新内容修改大小。

**语法:**

```cpp
*forwardlistname1* = (*forwardlistname2*)
Parameters :
Another container of the same type.
Result :
Assign the contents of the container passed as the 
parameter to the container written on left side of the operator.

```

示例:

```cpp
Input  :  myflist1 = 1, 2, 3
          myflist2 = 3, 2, 1, 4
          myflist1 = myflist2;
Output :  myflist1 = 3, 2, 1, 4

Input  :  myflist1 = 2, 6, 1, 5
          myflist2 = 3, 2
          myflist1 = myflist2;
Output :  myflist1 = 3, 2

```

**错误和异常**

1.如果容器的类型不同，则会引发错误。
2。否则它有一个基本的无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of = operator
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> myflist1{ 1, 2, 3 };
    forward_list<int> myflist2{ 3, 2, 1, 4 };
    myflist1 = myflist2;
    cout << "myflist1 = ";
    for (auto it = myflist1.begin(); it != myflist1.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
myflist1 = 3 2 1 4

```