# c++ STL 中的 list::pop_front()和 list::pop_back()

> 原文:[https://www . geesforgeks . org/listpop _ front-listpop _ back-c-STL/](https://www.geeksforgeeks.org/listpop_front-listpop_back-c-stl/)

[列表](https://www.geeksforgeeks.org/list-cpp-stl/)是 C++ 中用于以非连续方式存储数据的容器，通常，数组和向量本质上是连续的，因此与列表中的插入和删除选项相比，插入和删除操作的成本更高。

**list::pop_front()**

pop_front()函数用于从前面弹出或移除列表中的元素。该值将从列表的开头移除，容器大小将减少 1。

**语法:**

```cpp
*listname*.pop_front()
Parameters :
No argument is passed as parameter.
Result :
Removes the value present at the front 
of the given list named as *listname*

```

示例:

```cpp
Input :  list list{1, 2, 3, 4, 5};
         list.pop_front();
Output : 2, 3, 4, 5

Input :  list list{5, 4, 3, 2, 1};
         list.pop_front();
Output : 4, 3, 2, 1

```

**错误和异常**

1.  不抛出-保证-如果抛出异常，容器中没有变化。
2.  如果列表为空，则显示未定义的行为。

```cpp
// CPP program to illustrate
// pop_front() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{ 1, 2, 3, 4, 5 };
    mylist.pop_front();

    // list becomes 2, 3, 4, 5

    for (auto it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
2, 3, 4, 5

```

**应用:**使用 push_front()函数输入一个空列表，列表中有以下数字和顺序，打印列表的反面。

```cpp
Input : 1, 2, 3, 4, 5, 6, 7, 8
Output: 8, 7, 6, 5, 4, 3, 2, 1

```

```cpp
// CPP program to illustrate
// application Of pop_front() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{}, newlist{};
    mylist.push_front(8);
    mylist.push_front(7);
    mylist.push_front(6);
    mylist.push_front(5);
    mylist.push_front(4);
    mylist.push_front(3);
    mylist.push_front(2);
    mylist.push_front(1);

    // list becomes 1, 2, 3, 4, 5, 6, 7, 8

    while (!mylist.empty()) {
        newlist.push_front(mylist.front());
        mylist.pop_front();
    }
    for (auto it = newlist.begin(); it != newlist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
8, 7, 6, 5, 4, 3, 2, 1

```

**list::pop_back()**

pop_back()函数用于从后面弹出或移除列表中的元素。该值从列表的末尾移除，容器大小减少 1。

**语法:**

```cpp
*listname*.pop_back()
Parameters :
No argument is passed as parameter.
Result :
Removes the value present at the end or back 
of the given list named as *listname*

```

示例:

```cpp
Input :  list list{1, 2, 3, 4, 5};
         list.pop_back();
Output : 1, 2, 3, 4

Input :  list list{5, 4, 3, 2, 1};
         list.pop_back();
Output : 5, 4, 3, 2

```

**错误和异常**

1.  不抛出-保证-如果抛出异常，容器中没有变化。
2.  如果列表为空，则显示未定义的行为。

```cpp
// CPP program to illustrate
// pop_back() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{ 1, 2, 3, 4, 5 };
    mylist.pop_back();

    // list becomes 1, 2, 3, 4

    for (auto it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
1, 2, 3, 4

```

**应用:**使用 push_front()函数输入一个空列表，列表中有以下数字和顺序，打印列表的反面。

```cpp
Input : 1, 20, 39, 43, 57, 64, 73, 82
Output: 82, 73, 64, 57, 43, 39, 20, 1

```

```cpp
// CPP program to illustrate
// application Of pop_back() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{}, newlist{};
    mylist.push_front(82);
    mylist.push_front(73);
    mylist.push_front(64);
    mylist.push_front(57);
    mylist.push_front(43);
    mylist.push_front(39);
    mylist.push_front(20);
    mylist.push_front(1);

    // list becomes 1, 20, 39, 43, 57, 64, 73, 82

    while (!mylist.empty()) {
        newlist.push_back(mylist.back());
        mylist.pop_back();
    }
    for (auto it = newlist.begin(); it != newlist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
82, 73, 64, 57, 43, 39, 20, 1

```