# c++ STL 中的 forward _ list::swap()

> 原文:[https://www.geeksforgeeks.org/forward_listswap-c-stl/](https://www.geeksforgeeks.org/forward_listswap-c-stl/)

[STL 中的正向列表](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/)实现单链表。前向列表是从 C++ 11 引入的，对于插入、移除和移动操作(如排序)比其他容器更有用，并且允许元素的时间常数插入和移除。它与列表的不同之处在于转发列表只跟踪下一个元素的位置，而列表同时跟踪下一个和上一个元素。

**forward_list::swap()**

此功能用于将一个转发列表的内容与另一个相同类型和大小的转发列表进行交换。

**语法:**

```cpp
*forwardlistname1*.swap(*forwardlistname2*)
Parameters :
The name of the forward lists with which
the contents have to be swapped.
Result :
All the elements of the 2 forward list are swapped.

```

示例:

```cpp
Input  : myflist1 = {1, 2, 3, 4}
         myflist2 = {3, 5, 7, 9}
         myflist1.swap(myflist2);
Output : myflist1 = {3, 5, 7, 9}
         myflist2 = {1, 2, 3, 4}

Input  : myflist1 = {1, 3, 5, 7}
         myflist2 = {2, 4, 6, 8}
         myflist1.swap(myflist2);
Output : myflist1 = {2, 4, 6, 8}
         myflist2 = {1, 3, 5, 7}

```

**错误和异常**

1.如果转发列表不是同一类型，它将抛出一个错误。
2。如果转发列表的大小不同，它会抛出一个错误。
2。否则它有一个基本的无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of swap() function
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    // forward list container declaration
    forward_list<int> myflist1{ 1, 2, 3, 4 };
    forward_list<int> myflist2{ 3, 5, 7, 9 };

    // using swap() function to
    // swap elements of forward lists
    myflist1.swap(myflist2);

    // printing the first forward list
    cout << "myflist1 = ";
    for (auto it = myflist1.begin();
         it != myflist1.end(); ++ it)
        cout << ' ' << *it;

    // printing the second forward list
    cout << endl
         << "myflist2 = ";
    for (auto it = myflist2.begin();
         it != myflist2.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
myflist1 = 3 5 7 9 
myflist2 = 1 2 3 4 

```