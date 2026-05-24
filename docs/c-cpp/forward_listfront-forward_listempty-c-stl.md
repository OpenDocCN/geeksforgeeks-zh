# c++ STL 中的 forward_list::front()和 forward_list::empty()

> 原文:[https://www . geeksforgeeks . org/forward _ list front-forward _ list empty-c-STL/](https://www.geeksforgeeks.org/forward_listfront-forward_listempty-c-stl/)

[STL 中的正向列表](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/)实现单链表。前向列表是从 C++ 11 引入的，在插入、移除和移动操作(如排序)方面比其他容器更有用，并且允许元素的时间常数插入和移除。它不同于列表，因为转发列表只跟踪下一个元素的位置，而列表跟踪下一个和上一个元素。

**forward_list::front()**

该函数用于引用转发列表容器的第一个元素。这个函数可以用来获取转发列表的第一个元素。

**语法:**

```cpp
***forwardlistname.front()***
Parameters :
No value is needed to pass as the parameter.
Returns :
Direct reference to the first element of the container.
```

示例:

```cpp
Input  : forward_list forwardlist{1, 2, 3, 4, 5};
         forwardlist.front();
Output : 1

Input  : forward_list forwardlist{0, 1, 2, 3, 4, 5};
         forwardlist.front();
Output : 0
```

**错误和异常**
1。如果转发列表容器为空，则会导致未定义的行为。
2。如果转发列表不是空的，它有一个无异常抛出保证。

## C++

```cpp
// CPP program to illustrate
// Implementation of front() function
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> myforwardlist{ 1, 2, 3, 4, 5 };
    cout << myforwardlist.front();
    return 0;
}
```

输出:

```cpp
1
```

**forward_list::empty()**

empty()函数用于检查转发列表容器是否为空。

**语法:**

```cpp
***forwardlistname.empty()***
Parameters :
No parameters are passed.
Returns :
True, if list is empty
False, Otherwise
```

示例:

```cpp
Input  : forward_list forwardlist{1, 2, 3, 4, 5};
         forwardlist.empty();
Output : False

Input  : forward_list forwardlist{};
         forwardlist.empty();
Output : True
```

**错误和异常**
1。它有一个无异常抛出保证。
2。传递参数时显示错误。

## C++

```cpp
// CPP program to illustrate
// Implementation of empty() function
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> myforwardlist{};
    if (myforwardlist.empty()) {
        cout << "True";
    }
    else {
        cout << "False";
    }
    return 0;
}
```

输出:

```cpp
True
```

**Application–front()和 empty() :** 给定一个整数列表，求所有整数的和。

```cpp
Input  : 1, 5, 6, 3, 9, 2
Output : 26
*Explanation -  1+5+6+3+9+2 = 26*
```

**算法:**
1。检查转发列表是否为空，如果不是，将 front 元素添加到初始化为 0 的变量中，并弹出 front 元素。
2。重复此步骤，直到转发列表为空。
3。打印变量的最终值。

## C++

```cpp
// CPP program to illustrate
// Application of empty() function
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    int sum = 0;
    forward_list<int> myforwardlist{ 1, 5, 6, 3, 9, 2 };
    while (!myforwardlist.empty()) {
        sum = sum + myforwardlist.front();
        myforwardlist.pop_front();
    }
    cout << sum;
    return 0;
}
```

输出

```cpp
26
```