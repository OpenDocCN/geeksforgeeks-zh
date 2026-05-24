# std::forward_list::sort()在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/stdforward_listsort-c-stl/](https://www.geeksforgeeks.org/stdforward_listsort-c-stl/)

[STL 中的正向列表](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/)实现单链表。前向列表是从 C++ 11 引入的，在插入、移除和移动操作(如排序)方面比其他容器更有用，并且允许元素的时间常数插入和移除。它不同于列表，因为转发列表只跟踪下一个元素的位置，而列表跟踪下一个和上一个元素。

**forward_list::sort()**

sort()函数用于通过改变容器元素的位置来对它们进行排序。
**语法:**

```cpp
***1.***    ***forwardlistname.sort()***
    Parameters :
    No parameters are passed.
    Result :
    The elements of the container
    are sorted in ascending order.
***2.***    ***forwardlistname.sort(predicate)***
    Parameters :
    predicate is used to define your own custom sorting function,
    it will return boolean output
    Result :
    The elements of the container 
    sorted in the order as per predicate function
```

示例:

```cpp
Input  : myflist{1, 5, 3, 2, 4};
         myflist.sort();
Output : 1, 2, 3, 4, 5

Input  : myflist{"This","is","Geeksforgeeks"};
         myflist.sort();
Output : Geekforgeeks, This, is
```

**错误和异常**
1。它有一个基本的无异常抛出保证。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// SORTING INTEGERS
// CPP program to illustrate
// Implementation of sort() function
#include <iostream>
#include <forward_list>
using namespace std;

int main()
{
    // forward list declaration of integer type
    forward_list<int> myflist{1, 5, 3, 2, 4};

    // sort function
    myflist.sort();

    // printing the forward list after sort
    for (auto it = myflist.begin(); it != myflist.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
1 2 3 4 5
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// SORTING STRINGS
// CPP program to illustrate
// Implementation of sort() function
#include <iostream>
#include <forward_list>
#include <string>
using namespace std;

int main()
{
    // forward list declaration of string type
    forward_list<string> myflist{"This","is","Geeksforgeeks"};

    // sort function
    myflist.sort();

    // printing the forward list after sort
    for (auto it = myflist.begin(); it != myflist.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
Geeksforgeeks This is
```

**时间复杂度:** O(nlogn)

## C++

```cpp
// SORTING STRINGS USING CUSTOM COMPARATOR FUNCTION
// CPP program to illustrate
// Implementation of sort() function
#include <iostream>
#include <forward_list>
#include <string>
using namespace std;

bool comparator(string a, string b) {
    return a.length() <= b.length();
}

int main()
{
    // forward list declaration of string type
    forward_list<string> myflist{"This","is","Geeksforgeeks"};

    // sort function
    myflist.sort(comparator);

    // printing the forward list after sort
    for (auto it = myflist.begin(); it != myflist.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
is This Geeksforgeeks
```

时间复杂度–0(nlog(n))