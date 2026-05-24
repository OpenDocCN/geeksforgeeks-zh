# c++ STL 中的 list::炮位 _front()和 list::炮位 _back()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/listmplce _ front-listmplce _ back-c-STL/

[列表](https://www.geeksforgeeks.org/list-cpp-stl/)是 C++ 中用于以非连续方式存储数据的容器，通常，数组和向量本质上是连续的，因此与列表中的插入和删除选项相比，插入和删除操作的成本更高。

**list::emplace_front()**

该函数用于将新的元素插入列表容器，新的元素被添加到列表的开头。
**语法:**

```cpp
*listname*.emplace_front(*value*)
Parameters :
The element to be inserted into the list
is passed as the parameter.
Result :
The parameter is added to the
list at the beginning.

```

示例:

```cpp
Input  : mylist{1, 2, 3, 4, 5};
         mylist.emplace_front(6);
Output : mylist = 6, 1, 2, 3, 4, 5

Input  : mylist{};
         mylist.emplace_front(4);
Output : mylist = 4

```

**错误和异常**
1。它有很强的异常保证，因此，如果抛出异常，不会进行任何更改。
2。参数应该与容器的类型相同，否则会引发错误。

```cpp
// CPP program to illustrate
// Implementation of emplace_front() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist;
    mylist.emplace_front(1);
    mylist.emplace_front(2);
    mylist.emplace_front(3);
    mylist.emplace_front(4);
    mylist.emplace_front(5);
    mylist.emplace_front(6);
    // list becomes 6, 5, 4, 3, 2, 1

    // printing the list
    for (auto it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;

    return 0;
}
```

输出:

```cpp
6 5 4 3 2 1

```

**时间复杂度:** O(1)

**list::emplace_back()**

该函数用于将新的元素插入列表容器，新元素被添加到列表的末尾。
**语法:**

```cpp
*listname*.emplace_back(*value*)
Parameters :
The element to be inserted into the list
is passed as the parameter.
Result :
The parameter is added to the
list at the end.

```

示例:

```cpp
Input  : mylist{1, 2, 3, 4, 5};
         mylist.emplace_back(6);
Output : mylist = 1, 2, 3, 4, 5, 6

Input  : mylist{};
         mylist.emplace_back(4);
Output : mylist = 4

```

**错误和异常**
1。它有很强的异常保证，因此，如果抛出异常，不会进行任何更改。
2。参数应该与容器的类型相同，否则会引发错误。

```cpp
// CPP program to illustrate
// Implementation of emplace_back() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist;
    mylist.emplace_back(1);
    mylist.emplace_back(2);
    mylist.emplace_back(3);
    mylist.emplace_back(4);
    mylist.emplace_back(5);
    mylist.emplace_back(6);
    // list becomes 1, 2, 3, 4, 5, 6

    // printing the list
    for (auto it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;

    return 0;
}
```

输出:

```cpp
1 2 3 4 5 6

```

**时间复杂度:** O(1)