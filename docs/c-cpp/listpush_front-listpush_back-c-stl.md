# c++ STL 中的 list::push_front()和 list::push_back()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/listpush _ front-listpush _ back-c-STL/

[**列表**](https://www.geeksforgeeks.org/list-cpp-stl/) 是 C++ 中用于以非连续方式存储数据的容器，通常，数组和向量本质上是连续的，因此与列表中的插入和删除选项相比，插入和删除操作的成本更高。

**列表::push_front()**

push_front()函数用于将元素从前面推入列表。在当前第一个元素和容器大小增加 1 之前，新值被插入列表的开头。

**语法:**

```cpp
***listname.push_front(value)***
Parameters :
The value to be added in the front is 
passed as the parameter
Result :
Adds the *value* mentioned as the parameter 
to the front of the list named as *listname*
```

示例:

```cpp
Input : list list{1, 2, 3, 4, 5};
        list.push_front(6);
Output : 6, 1, 2, 3, 4, 5

Input : list list{5, 4, 3, 2, 1};
        list.push_front(6);
Output :6, 5, 4, 3, 2, 1
```

**错误和异常**

1.  Strong exception guarantee-If an exception is thrown, there is no change in the container.
2.  If the list does not support the values passed as parameters, the undefined behavior is displayed.

## c++

```cpp
// CPP program to illustrate
// push_front() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{ 1, 2, 3, 4, 5 };
    mylist.push_front(6);

    // list becomes 6, 1, 2, 3, 4, 5

    for (auto it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
6 1 2 3 4 5
```

**应用程序:**使用 push_front()函数输入一个空列表，该列表包含以下数字和顺序，并对给定列表进行排序。

```cpp
Input :  7, 89, 45, 6, 24, 58, 43
Output : 6, 7, 24, 43, 45, 58, 89
```

## c++

```cpp
// CPP program to illustrate
// application Of push_front() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{};
    mylist.push_front(43);
    mylist.push_front(58);
    mylist.push_front(24);
    mylist.push_front(6);
    mylist.push_front(45);
    mylist.push_front(89);
    mylist.push_front(7);

    // list becomes 7, 89, 45, 6, 24, 58, 43
    // Sorting function

    mylist.sort();

    for (auto it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
 6 7 24 43 45 58 89
```

**列表::push_back()**

push_back()函数用于将元素从后面推入列表。新值插入到列表的末尾，在当前最后一个元素之后，容器大小增加 1。

**语法:**

```cpp
***listname.push_back(value)***
Parameters :
The value to be added in the back is 
passed as the parameter
Result :
Adds the *value* mentioned as the parameter 
to the back of the list named as *listname*
```

示例:

```cpp
Input : list list{1, 2, 3, 4, 5};
        list.push_back(6);
Output :1, 2, 3, 4, 5, 6

Input : list list{5, 4, 3, 2, 1};
        list.push_front(0);
Output :5, 4, 3, 2, 1, 0
```

**错误和异常**

1.  Strong exception guarantee-If an exception is thrown, there is no change in the container.
2.  If the list does not support the values passed as parameters, the undefined behavior is displayed.

## c++

```cpp
// CPP program to illustrate
// push_back() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{ 1, 2, 3, 4, 5 };
    mylist.push_back(6);

    // list becomes 1, 2, 3, 4, 5, 6

    for (auto it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
1 2 3 4 5 6
```

**应用程序:**使用 push_back()函数输入一个空列表，该列表包含以下数字和顺序，并对给定列表进行排序。

```cpp
Input :  7, 89, 45, 6, 24, 58, 43
Output : 6, 7, 24, 43, 45, 58, 89
```

## c++

```cpp
// CPP program to illustrate
// application Of push_back() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{};
    mylist.push_back(7);
    mylist.push_back(89);
    mylist.push_back(45);
    mylist.push_back(6);
    mylist.push_back(24);
    mylist.push_back(58);
    mylist.push_back(43);

    // list becomes 7, 89, 45, 6, 24, 58, 43
    // Sorting function

    mylist.sort();

    for (auto it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
 6 7 24 43 45 58 89
```