# c++ STL 中的 list::front()和 list::back()

> 原文:[https://www . geesforgeks . org/list front-and-listback-in-CPP-STL/](https://www.geeksforgeeks.org/listfront-and-listback-in-cpp-stl/)

[**列表**](https://www.geeksforgeeks.org/list-cpp-stl/) 是 C++ 中用于以非连续方式存储数据的容器，通常，数组和向量本质上是连续的，因此与列表中的插入和删除选项相比，插入和删除操作的成本更高。

**列表::正面()**

该函数用于引用列表容器的第一个元素。这个函数可以用来获取列表的第一个元素。

**语法:**

```cpp
***listname.front()***
Parameters :
No value is needed to pass as the parameter.
Returns :
Direct reference to the first element of the list container.
```

示例:

```cpp
Input  : list list{1, 2, 3, 4, 5};
         list.front();
Output : 1

Input  : list list{0, 1, 2, 3, 4, 5};
         list.front();
Output : 0
```

**错误和异常**

1.  如果列表容器为空，会导致未定义的行为
2.  如果列表不是空的，它有一个无异常抛出保证

## C++

```cpp
// CPP program to illustrate
// Implementation of front() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{ 1, 2, 3, 4, 5 };
    cout << mylist.front();
    return 0;
}
```

输出:

```cpp
1
```

**list::back()**

该函数用于引用列表容器的最后一个元素。此函数可用于从列表末尾获取第一个元素。

**语法:**

```cpp
***listname.back()***
Parameters :
No value is needed to pass as the parameter.
Returns :
Direct reference to the last element of the list container.
```

**示例:**

```cpp
Input  : list list{1, 2, 3, 4, 5};
         list.back();
Output : 5

Input  : list list{1, 2, 3, 4, 5, 6};
         list.back();
Output : 6
```

**错误和异常**

1.  如果列表容器为空，会导致未定义的行为
2.  如果列表不是空的，它有一个无异常抛出保证

## C++

```cpp
// CPP program to illustrate
// Implementation of back() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{ 1, 2, 3, 4, 5 };
    cout << mylist.back();
    return 0;
}
```

输出:

```cpp
5
```

**应用程序**
给定一个空的整数列表，在列表中添加数字，然后打印第一个和最后一个元素之间的差异。

```cpp
Input: 1, 2, 3, 4, 5, 6, 7, 8
Output:7
*Explanation:* Last element = 8, First element = 1, Difference = 7
```

**算法**
1。使用[向前推()或向后推()功能](https://www.geeksforgeeks.org/listpush_front-listpush_back-c-stl/)T5】2 向列表中添加号码。比较第一个和最后一个元素。
3。如果第一个元素较大，减去最后一个元素并打印出来。
4。否则从最后一个元素中减去第一个元素并打印出来。

## C++

```cpp
// CPP program to illustrate
// application Of front() and back() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{};
    mylist.push_front(8);
    mylist.push_front(7);
    mylist.push_front(6);
    mylist.push_front(5);
    mylist.push_front(4);
    mylist.push_front(3);
    mylist.push_front(2);
    mylist.push_front(1);

    // list becomes 1, 2, 3, 4, 5, 6, 7, 8

    if (mylist.front() > mylist.back()) {
        cout << mylist.front() - mylist.back();
    }
    else if (mylist.front() < mylist.back()) {
        cout << mylist.back() - mylist.front();
    }
    else
        cout << "0";
}
```

输出:

```cpp
7
```