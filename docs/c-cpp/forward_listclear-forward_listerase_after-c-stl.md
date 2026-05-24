# c++ STL 中的 forward_list::clear()和 forward_list::erase_after()

> 原文:[https://www . geeksforgeeks . org/forward _ list clear-forward _ listerase _ after-c-STL/](https://www.geeksforgeeks.org/forward_listclear-forward_listerase_after-c-stl/)

[STL 中的正向列表](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/)实现单链表。前向列表是从 C++ 11 引入的，在插入、移除和移动操作(如排序)方面比其他容器更有用，并且允许元素的时间常数插入和移除。它不同于列表，因为转发列表只跟踪下一个元素的位置，而列表跟踪下一个和上一个元素。

**forward_list::clear()**

clear()函数用于移除 forward list 容器的所有元素，从而使其大小为 0。
**语法:**

```cpp
***forwardlistname.clear()***
Parameters :
No parameters are passed.
Result :
All the elements of the forward list are
removed ( or destroyed )
```

示例:

```cpp
Input  : flist{1, 2, 3, 4, 5};
         flist.clear();
Output : flist{}

Input  : flist{};
         flist.clear();
Output : flist{}
```

**错误和异常**
1。它有一个无异常抛出保证。
2。传递参数时显示错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of clear() function
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> myflist{ 1, 2, 3, 4, 5 };

    myflist.clear();
    // Forward List becomes empty

    // Printing the Forward list
    for (auto it = myflist.begin(); it != myflist.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
*No Output*
```

**forward_list::erase_after()**

erase-after()函数用于从指定位置旁边的容器或范围中移除元素。
**语法:**

```cpp
1\. ***flistname.erase_after(position)***
2\. ***flistname.erase_after(startingposition, endingposition)***
Parameters :
Position previous of the element to be removed in the form of iterator.
or the range specified using start and end iterator.
Result :
Elements are removed from the next
position of the container.
```

示例:

```cpp
Input  : flist{1, 2, 3, 4, 5}, iterator= 2 i.e.,iterator is pointing to element with index 2.
         flist.erase_after(iterator);
Output : 1, 2, 3, 5

Input  : flist{1, 2, 3, 4, 5, 6, 7, 8}, iterator1= 3, iterator2= 6\. i.e., iterator1 is pointing
         to element with index 3 and iterator2 is pointing to element with index 6.
         flist.erase_after(iterator1, iterator2);
Output : 1, 2, 3, 4, 7, 8
```

**错误和异常**
1。如果位置有效，它有一个无异常抛出保证。
2。否则显示未定义的行为。
**从特定位置移除元素**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of erase_after() function
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> myflist{ 1, 2, 3, 4, 5 };
    forward_list<int>::iterator it;

    it = myflist.begin();
    myflist.erase_after(it);

    // Printing the forward list
    for (auto it = myflist.begin(); it != myflist.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
1 3 4 5
```

**移除范围内的元素**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of erase_after() function
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> myflist{ 1, 2, 3, 4, 5 };
    forward_list<int>::iterator it1, it2;

    it1 = myflist.begin();
    it2 = myflist.end();

    myflist.erase_after(it1, it2);

    // Printing the forward list
    for (auto it = myflist.begin(); it != myflist.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
1
```