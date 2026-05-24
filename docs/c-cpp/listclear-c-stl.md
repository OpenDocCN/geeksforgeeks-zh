# 列表::C++ STL 中的 clear()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/listclear-c-STL/

[列表](https://www.geeksforgeeks.org/list-cpp-stl/)是 C++ 中用来以非连续方式存储数据的容器。通常，数组和向量本质上是连续的，因此与列表中的插入和删除选项相比，插入和删除操作的成本更高。

**list::clear()**

clear()函数用于移除列表容器的所有元素，从而使其大小为 0。
**语法:**

```cpp
*listname*.clear()
Parameters :
No parameters are passed.
Result :
All the elements of the list are
removed ( or destroyed )

```

示例:

```cpp
Input  : list{1, 2, 3, 4, 5};
         list.clear();
Output : list{}

Input  : list{};
         list.clear();
Output : list{}

```

**错误和异常**

1.它有一个无异常抛出保证。
2。传递参数时显示错误。

```cpp
// CPP program to illustrate
// Implementation of clear() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist{ 1, 2, 3, 4, 5 };

    mylist.clear();
    // List becomes empty

    // Printing the list
    for (auto it = mylist.begin(); it != mylist.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
*No Output*

```

相关文章:[删除 C++ STL 列表中的元素](https://www.geeksforgeeks.org/delete-elements-c-stl-list/)