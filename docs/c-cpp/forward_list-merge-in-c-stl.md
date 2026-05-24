# c++ STL 中的 forward_list merge()

> 原文:[https://www.geeksforgeeks.org/forward_list-merge-in-c-stl/](https://www.geeksforgeeks.org/forward_list-merge-in-c-stl/)

**forward_list::merge()** 是 C++ STL 中的一个内置函数，将两个排序后的 forward_list 合并为一个。
merge()函数有两种用法:

1.  将两个按升序排序的正向列表合并为一个。
2.  使用比较函数将两个转发列表合并为一个。

**语法:**

```cpp
forwardlist_name1.merge(forward_list& forwardlist_name2)
                  or
forwardlist_name1.merge(forward_list& forwardlist_name2, Compare comp)

```

**参数:**该函数接受两个参数，如下所示:

1.  *转发列表 _ 名称 2*–另一个要合并的相同类型的转发列表
2.  *comp*–应该返回真或假的比较函数。

**返回值:**函数不返回任何内容。
以下程序说明上述功能:
**程序 1:**

```cpp
// CPP program to illustrate the
// forward_list::merge() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    forward_list<int> fl1 = { 12, 25, 31, 41 };
    forward_list<int> fl2 = { 10, 20, 30 };

    // merge two forward list
    fl1.merge(fl2);

    // print the contents of the forward list
    cout << "List contains following elements" << endl;
    for (auto it = fl1.begin(); it != fl1.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
List contains following elements
10 12 20 25 30 31 41

```

 **节目 2:**

```cpp
#include <bits/stdc++.h>
using namespace std;

// comparison function
bool cmp_fun(int a, int b)
{
    return a > b;
}

int main()
{
    forward_list<int> fl1 = { 41, 31, 25, 12 };
    forward_list<int> fl2 = { 30, 20, 10 };

    // merge two forward list
    fl1.merge(fl2, cmp_fun);

    // print the contents of the forward list
    cout << "List contains following elements" << endl;
    for (auto it = fl1.begin(); it != fl1.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
List contains following elements
41 31 30 25 20 12 10

```