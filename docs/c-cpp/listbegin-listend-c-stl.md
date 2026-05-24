# c++ STL 中的 list::begin()和 list::end()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/listbegin-list-c-STL/

[列表](https://www.geeksforgeeks.org/list-cpp-stl/)是 C++ 中用于以非连续方式存储数据的容器，通常，数组和向量本质上是连续的，因此与列表中的插入和删除选项相比，插入和删除操作的成本更高。

**list::begin()**

begin()函数用于返回指向列表容器第一个元素的迭代器。它与 front()函数不同，因为 front 函数**返回对容器第一个元素的引用**，而 begin()函数**返回对容器第一个元素的双向迭代器**。
**语法:**

```cpp
***listname***.begin()
Parameters :
No parameters are passed.
Returns :
This function returns a bidirectional
iterator pointing to the first element.

```

示例:

```cpp
Input  : mylist{1, 2, 3, 4, 5};
         mylist.begin();
Output : *returns an iterator to the element 1*

Input  : mylist{8, 7};
         mylist.begin();
Output : *returns an iterator to the element 8*

```

**错误和异常**
1。它有一个无异常抛出保证。
2。传递参数时显示错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of begin() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    // declaration of list container
    list<int> mylist{ 1, 2, 3, 4, 5 };

    // using begin() to print list
    for (auto it = mylist.begin(); it != 
                            mylist.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
1 2 3 4 5

```

**时间复杂度:** O(1)

**list::end()**

end()函数用于返回指向列表容器最后一个元素的迭代器。它与 back()函数不同，因为 back()函数**返回容器最后一个元素的引用**，而 end()函数**返回容器过去最后一个元素的双向迭代器**。
**语法:**

```cpp
***listname***.end()
Parameters :
No parameters are passed.
Returns :
This function returns a bidirectional
iterator pointing to the past last element.

```

**错误和异常**
1。它有一个无异常抛出保证。
2。传递参数时显示错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of end() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    // declaration of list container
    list<int> mylist{ 1, 2, 3, 4, 5 };

    // using end() to print list
    for (auto it = mylist.begin(); it !=
                                mylist.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

**输出:**

```cpp
1 2 3 4 5

```

**时间复杂度:** O(1)