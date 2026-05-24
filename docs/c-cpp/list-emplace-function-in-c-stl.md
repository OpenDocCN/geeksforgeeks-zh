# 在 C++ STL 中列出侵位()函数

> 原文:[https://www . geesforgeks . org/list-侵位-function-in-c-stl/](https://www.geeksforgeeks.org/list-emplace-function-in-c-stl/)

**列表::侵位()**是 C++ STL 中的内置函数，通过在给定位置插入新元素来扩展列表。

**语法:**

```cpp
list_name.emplace(position, element)
```

**参数:**该功能接受两个强制参数，如下所述:

*   *位置*–它指定迭代器，该迭代器指向列表中要插入新元素的位置。
*   *参数*–指定要插入列表容器的元素。

**返回值:**返回一个随机访问迭代器，指向新插入的元素。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// list::emplace() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // declaration of list
    list<int> lis = { 5, 6, 7, 8, 9, 10 };

    auto it = lis.emplace(lis.begin(), 2);

    // inserts at the beginning of the list
    lis.emplace(it, 1);

    cout << "List: ";
    for (auto it = lis.begin(); it != lis.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output:**

```cpp
List: 1 2 5 6 7 8 9 10

```

**程序 2:**

```cpp
// C++ program to illustrate the
// list::emplace() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // declaration of list
    list<pair<int, char> > lis;

    // inserts at the beginning of the list
    auto it = lis.emplace(lis.begin(), 4, 'a');

    // inserts at the beginning of the list
    lis.emplace(it, 3, 'b');

    cout << "List: ";

    for (auto it : lis)
        cout << "(" << it.first << ", " << it.second << ") ";

    return 0;
}
```

**Output:**

```cpp
List: (3, b) (4, a)

```