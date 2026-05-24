# c++ STL 中的 forward_list::begin()和 forward_list::end()

> 原文:[https://www . geesforgeks . org/forward _ list begin-forward _ list end-c-STL/](https://www.geeksforgeeks.org/forward_listbegin-forward_listend-c-stl/)

[STL 中的正向列表](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/)实现单链表。前向列表是从 C++ 11 引入的，在插入、移除和移动操作(如排序)方面比其他容器更有用，并且允许元素的时间常数插入和移除。它不同于列表，因为转发列表只跟踪下一个元素的位置，而列表跟踪下一个和上一个元素。

**forward_list::begin()**

begin()函数用于返回指向转发列表容器第一个元素的迭代器。begin()函数**返回一个双向迭代器**到容器的第一个元素。

**语法:**

```cpp
*forwardlistname*.begin()
Parameters :
No parameters are passed.
Returns :
This function returns a bidirectional
iterator pointing to the first element.

```

示例:

```cpp
Input  : myflist{1, 2, 3, 4, 5};
         myflist.begin();
Output : *returns an iterator to the element 1*

Input  : myflist{8, 7};
         myflist.begin();
Output : *returns an iterator to the element 8*

```

**错误和异常**

1.它有一个无异常抛出保证。
2。传递参数时显示错误。

```cpp
// CPP program to illustrate
// Implementation of begin() function
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    // declaration of forward list container
    forward_list<int> myflist{ 1, 2, 3, 4, 5 };

    // using begin() to print list
    for (auto it = myflist.begin(); it != myflist.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
1 2 3 4 5

```

**时间复杂度:** O(1)

**forward_list::end()**

end()函数用于返回指向列表容器最后一个元素的迭代器。end()函数**返回一个双向迭代器**到容器的最后一个元素。

**语法:**

```cpp
*forwardlistname*.end()
Parameters :
No parameters are passed.
Returns :
This function returns a bidirectional
iterator pointing to the last element.

```

示例:

```cpp
Input  : myflist{1, 2, 3, 4, 5};
         myflist.end();
Output : *returns an iterator to the element 5*

Input  : myflist{8, 7};
         myflist.end();
Output : *returns an iterator to the element 7*

```

**错误和异常**

1.它有一个无异常抛出保证。
2。传递参数时显示错误。

```cpp
// CPP program to illustrate
// Implementation of end() function
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    // declaration of forward list container
    forward_list<int> myflist{ 1, 2, 3, 4, 5 };

    // using end() to print forward list
    for (auto it = myflist.begin(); it != myflist.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
1 2 3 4 5

```

**时间复杂度:** O(1)