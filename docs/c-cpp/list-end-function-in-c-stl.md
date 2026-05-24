# 在 C++ STL 中列出 end()函数

> 原文:[https://www.geeksforgeeks.org/list-end-function-in-c-stl/](https://www.geeksforgeeks.org/list-end-function-in-c-stl/)

**list::end()** 是 C++ STL 中的内置函数，用于让迭代器经过最后一个元素。通过最后一个元素，意味着 end()函数返回的迭代器将迭代器返回到列表容器中最后一个元素之后的元素。它不能用于修改元素或列表容器。

这个函数基本上是用来和 list::begin()函数一起设置一个范围。

**语法:**

```cpp
list_name.end() 

```

**参数:**这个函数不接受任何参数，它只是返回一个迭代器来越过最后一个元素。

**返回值:**这个函数返回列表最后一个元素之后的元素的迭代器。

下面的程序说明了 list::end()函数。

```cpp
// CPP program to illustrate the
// list::end() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Creating a list
    list<int> demoList;

    // Add elements to the List
    demoList.push_back(10);
    demoList.push_back(20);
    demoList.push_back(30);
    demoList.push_back(40);

    // using end() to get iterator 
    // to past the last element
    list<int>::iterator it = demoList.end();

    // This will not print the last element
    cout << "Returned iterator points to : " << *it << endl;

    // Using end() with begin() as a range to
    // print all of the list elements
    for (auto itr = demoList.begin();
         itr != demoList.end(); itr++) {
        cout << *itr << " ";
    }

    return 0;
}
```

**输出:**

```cpp
Returned iterator points to : 4
10 20 30 40

```

**注**:该函数在恒定时间复杂度下工作。