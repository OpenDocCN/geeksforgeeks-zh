# 列表::运算符=在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/listoperator-c-stl/](https://www.geeksforgeeks.org/listoperator-c-stl/)

[列表](https://www.geeksforgeeks.org/list-cpp-stl/)是 C++ 中用于以非连续方式存储数据的容器，通常，数组和向量本质上是连续的，因此与列表中的插入和删除选项相比，插入和删除操作的成本更高。

**list::operator=**

该运算符用于通过替换现有内容向容器分配新内容。
还会根据新内容修改大小。

**语法:**

```cpp
*listname1* = (*listname2*)
Parameters :
Another container of the same type.
Result :
Assign the contents of the container passed as 
parameter to the container written on left side of the operator.

```

示例:

```cpp
Input  :  mylist1 = 1, 2, 3
          mylist2 = 3, 2, 1, 4
          mylist1 = mylist2;
Output :  mylist1 = 3, 2, 1, 4

Input  :  mylist1 = 2, 6, 1, 5
          mylist2 = 3, 2
          mylist1 = mylist2;
Output :  mylist1 = 3, 2

```

**错误和异常**

1.如果容器的类型不同，则会引发错误。
2。否则它有一个基本的无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of = operator
#include <iostream>
#include <list>
using namespace std;

int main()
{
    list<int> mylist1{ 1, 2, 3 };
    list<int> mylist2{ 3, 2, 1, 4 };
    mylist1 = mylist2;
    cout << "mylist1 = ";
    for (auto it = mylist1.begin();
              it != mylist1.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
mylist1 = 3 2 1 4

```