# STD::list::c++ STL 中的排序

> [https://www.geeksforgeeks.org/stdlistsort-c-stl/](https://www.geeksforgeeks.org/stdlistsort-c-stl/)

[列表](https://www.geeksforgeeks.org/list-cpp-stl/)是 C++ 中用于以非连续方式存储数据的容器，通常，数组和向量本质上是连续的，因此与列表中的插入和删除选项相比，插入和删除操作的成本更高。

**list::sort()**

sort()函数用于通过改变容器元素的位置来对它们进行排序。

**语法:**

```cpp
*listname*.sort()
Parameters :
No parameters are passed.
Result :
The elements of the container
are sorted in ascending order.

```

示例:

```cpp
Input  : mylist{1, 5, 3, 2, 4};
         mylist.sort();
Output : 1, 2, 3, 4, 5

Input  : mylist{"hi", "bye", "thanks"};
         mylist.sort();
Output : bye, hi, thanks

```

**错误和异常**

1.它有一个基本的无异常抛出保证。
2。传递参数时显示错误。

```cpp
// SORTING INTEGERS
// CPP program to illustrate
// Implementation of sort() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    // list declaration of integer type
    list<int> mylist{ 1, 5, 3, 2, 4 };

    // sort function
    mylist.sort();

    // printing the list after sort
    for (auto it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
1 2 3 4 5
```

```cpp
// SORTING STRINGS
// CPP program to illustrate
// Implementation of sort() function
#include <iostream>
#include <list>
#include <string>
using namespace std;

int main()
{
    // list declaration of string type
    list<string> mylist{ "hi", "bye", "thanks" };

    // sort function
    mylist.sort();

    // printing the list after sort
    for (auto it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
bye hi thanks
```

**时间复杂度:** O(nlogn)

**类似功能:**[c++ STL 中的排序](https://www.geeksforgeeks.org/sort-c-stl/)