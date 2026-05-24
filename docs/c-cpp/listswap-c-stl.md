# 列表::C++ STL 中的 swap()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/listswap-c-STL/

[列表](https://www.geeksforgeeks.org/list-cpp-stl/)是 C++ 中用来以非连续方式存储数据的容器。通常，数组和向量本质上是连续的，因此与列表中的插入和删除选项相比，插入和删除操作的成本更高。

**list::swap()**

此功能用于将一个列表的内容与另一个相同类型和大小的列表进行交换。

**语法:**

```cpp
*listname1*.swap(*listname2*)
Parameters :
The name of the lists with which
the contents have to be swapped.
Result :
All the elements of the 2 list are swapped.

```

示例:

```cpp
Input  : mylist1 = {1, 2, 3, 4}
         mylist2 = {3, 5, 7, 9}
         mylist1.swap(mylist2);
Output : mylist1 = {3, 5, 7, 9}
         mylist2 = {1, 2, 3, 4}

Input  : mylist1 = {1, 3, 5, 7}
         mylist2 = {2, 4, 6, 8}
         mylist1.swap(mylist2);
Output : mylist1 = {2, 4, 6, 8}
         mylist2 = {1, 3, 5, 7}

```

**错误和异常**

1.如果列表不是同一类型，它将引发错误。
2。如果列表大小不同，它会抛出一个错误。
2。否则它有一个基本的无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of swap() function
#include <iostream>
#include <list>
using namespace std;

int main()
{
    // list container declaration
    list<int> mylist1{ 1, 2, 3, 4 };
    list<int> mylist2{ 3, 5, 7, 9 };

    // using swap() function to 
    //swap elements of lists
    mylist1.swap(mylist2);

    // printing the first list
    cout << "mylist1 = ";
    for (auto it = mylist1.begin();
              it != mylist1.end(); ++ it)
        cout << ' ' << *it;

    // printing the second list
    cout << endl
        << "mylist2 = ";
    for (auto it = mylist2.begin();
              it != mylist2.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
mylist1 = 3 5 7 9 
mylist2 = 1 2 3 4 

```