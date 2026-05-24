# 在 C++ STL 中列出 front()函数

> 原文:[https://www.geeksforgeeks.org/list-front-function-in-c-stl/](https://www.geeksforgeeks.org/list-front-function-in-c-stl/)

**list::front()** 是 C++ STL 中的内置函数，用于返回对列表容器中第一个元素的引用。与 list::begin()函数不同，该函数返回对列表容器中第一个元素的直接引用。

**语法:**

```cpp
list_name.front() 

```

**参数:**这个函数不接受任何参数，它只是返回对列表容器中第一个元素的引用。

**返回值:**该函数返回列表容器中第一个元素的直接引用。

**异常**:该函数在与空列表容器一起使用时会创建一个未定义的行为。

下面的程序说明了 list::front()函数。

```cpp
// CPP program to illustrate the
// list::front() function
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

    // get the first element using front()
    int ele = demoList.front();

    // Print the first element
    cout << ele;

    return 0;
}
```

**输出:**

```cpp
10

```

**注**:该函数在恒定时间复杂度下工作。