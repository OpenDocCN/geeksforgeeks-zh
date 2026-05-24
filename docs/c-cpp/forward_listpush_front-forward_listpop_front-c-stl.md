# c++ STL 中的 forward_list::push_front()和 forward_list::pop_front()

> 原文:[https://www . geesforgeks . org/forward _ list push _ front-forward _ list pop _ front-c-STL/](https://www.geeksforgeeks.org/forward_listpush_front-forward_listpop_front-c-stl/)

[STL 中的正向列表](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/)实现单链表。前向列表是从 C++ 11 引入的，在插入、移除和移动操作(如排序)方面比其他容器更有用，并且允许元素的时间常数插入和移除。它不同于列表，因为转发列表只跟踪下一个元素的位置，而列表跟踪下一个和上一个元素。

**forward_list::push_front**

push_front()函数用于将元素从前面推入前进列表。在当前第一个元素和容器大小增加 1 之前，新值被插入到转发列表的开头。
**语法:**

```cpp
***forwardlistname.push_front(value)***
Parameters :
The value to be added in the front is 
passed as the parameter
Result :
Adds the value mentioned as the parameter to the
front of the forward list named as *forwardlistname*
```

示例:

```cpp
Input : forward_list forwardlist{1, 2, 3, 4, 5};
        forwardlist.push_front(6);
Output : 6, 1, 2, 3, 4, 5

Input : forward_list forwardlist{5, 4, 3, 2, 1};
        forwardlist.push_front(6);
Output :6, 5, 4, 3, 2, 1
```

**错误和异常**
1。强异常保证——如果抛出异常，容器中没有任何变化。
2。如果前向列表不支持作为参数传递的值，它将显示未定义的行为。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// push_front() function
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> myforwardlist{ 1, 2, 3, 4, 5 };
    myforwardlist.push_front(6);

    // Forward list becomes 6, 1, 2, 3, 4, 5

    for (auto it = myforwardlist.begin(); it != myforwardlist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
6 1 2 3 4 5
```

**应用:**使用 push_front()函数输入一个空的正向列表，该列表包含以下数字和顺序，并对给定的正向列表进行排序。

```cpp
Input :  7, 89, 45, 6, 24, 58, 43
Output : 6, 7, 24, 43, 45, 58, 89
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// application Of push_front() function
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> myforwardlist{};
    myforwardlist.push_front(43);
    myforwardlist.push_front(58);
    myforwardlist.push_front(24);
    myforwardlist.push_front(6);
    myforwardlist.push_front(45);
    myforwardlist.push_front(89);
    myforwardlist.push_front(7);

    // Forward list becomes 7, 89, 45, 6, 24, 58, 43
    // Sorting function

    myforwardlist.sort();

    for (auto it = myforwardlist.begin(); it != myforwardlist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出

```cpp
6 7 24 43 45 58 89
```

**forward_list::pop_front**

pop_front()函数用于从前面弹出或移除正向列表中的元素。该值将从列表的开头移除，容器大小将减少 1。
**语法:**

```cpp
***forwardlistname.pop_front()***
Parameters :
No parameter is passed as the parameter.
Result :
Removes the value present at the front 
of the given forward list named as *forwardlistname*
```

示例:

```cpp
Input : forward_list forwardlist{1, 2, 3, 4, 5};
        forwardlist.pop_front();
Output :2, 3, 4, 5

Input : forward_list forwardlist{5, 4, 3, 2, 1};
        forwardlist.pop_front();
Output :4, 3, 2, 1
```

**错误和异常**
1。不抛出-保证-如果抛出异常，容器中没有变化。
2。如果列表为空，则显示未定义的行为。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// pop_front() function
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> myforwardlist{ 1, 2, 3, 4, 5 };
    myforwardlist.pop_front();

    // forward list becomes 2, 3, 4, 5

    for (auto it = myforwardlist.begin(); it != myforwardlist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
2 3 4 5
```

**应用:**使用 push_front()功能，输入一个空的正向列表，列表的编号和顺序如下，打印列表的反面。

```cpp
Input : 1, 2, 3, 4, 5, 6, 7, 8
Output: 8, 7, 6, 5, 4, 3, 2, 1
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// application Of pop_front() function
#include <forward_list>
#include <iostream>
using namespace std;

int main()
{
    forward_list<int> myforwardlist{}, newforwardlist{};
    myforwardlist.push_front(8);
    myforwardlist.push_front(7);
    myforwardlist.push_front(6);
    myforwardlist.push_front(5);
    myforwardlist.push_front(4);
    myforwardlist.push_front(3);
    myforwardlist.push_front(2);
    myforwardlist.push_front(1);

    // Forward list becomes 1, 2, 3, 4, 5, 6, 7, 8

    while (!myforwardlist.empty()) {
        newforwardlist.push_front(myforwardlist.front());
        myforwardlist.pop_front();
    }
    for (auto it = newforwardlist.begin(); it != newforwardlist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出

```cpp
8 7 6 5 4 3 2 1
```