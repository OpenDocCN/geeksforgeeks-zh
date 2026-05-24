# 在 C++ STL 中 `list::splice()` 函数

> 原文: [https://www.geeksforgeeks.org/list-splice-function-in-c-stl/](https://www.geeksforgeeks.org/list-splice-function-in-c-stl/)

`list::splice()` 是 C++ STL 中的内置函数，用于将元素从一个列表转移到另一个列表。`splice()` 功能有三种使用方式：

1.  将列表 `x` 的所有元素转移到某个 `position` 的另一个列表中。
2.  仅将列表 `x` 中的 `i` 指向的元素转移到某个 `position` 的列表中。
3.  将范围 `[first, last]` 从列表 `x` 转移到某个 `position` 的另一个列表中。

**语法:**

```cpp
list1_name.splice (iterator position, list2)
                or 
list1_name.splice (iterator position, list2, iterator i)
                or 
list1_name.splice (iterator position, list2, iterator first, iterator last)
```

**参数:** 该函数接受如下指定的四个参数：

*   `position` – 指定要传送元素的位置。
*   `list2` – 指定要传输的同类型列表对象。
*   `i` – 它指定一个迭代器，指向列表 2 中要传输的元素的位置。
*   `first`, `last` – 迭代器，指定列表 2 中要在列表 1 中传输的元素范围。范围包括 `first` 和 `last` 之间的所有元素，包括 `first` 指向的元素，但不包括 `last` 指向的元素。

**返回值:** 这个函数不返回任何东西。

以下程序说明了上述功能：

### 程序 1：转移列表的所有元素

```cpp
// CPP program to illustrate the
// list::splice() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initializing lists
    list<int> l1 = { 1, 2, 3 };
    list<int> l2 = { 4, 5 };
    list<int> l3 = { 6, 7, 8 };

    // transfer all the elements of l2
    // at the beginning of l1
    l1.splice(l1.begin(), l2);

    cout << "list l1 after splice operation" << endl;
    for (auto x : l1)
        cout << x << " ";

    // transfer all the elements of l1
    // at the end of l3
    l3.splice(l3.end(), l1);

    cout << "\nlist l3 after splice operation" << endl;
    for (auto x : l3)
        cout << x << " ";
    return 0;
}
```

**Output:**

```cpp
list l1 after splice operation
4 5 1 2 3 
list l3 after splice operation
6 7 8 4 5 1 2 3
```

### 程序 2：转移单个元素

```cpp
// CPP program to illustrate the
// list::splice() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initializing lists and iterator
    list<int> l1 = { 1, 2, 3 };
    list<int> l2 = { 4, 5 };
    list<int>::iterator it;

    // Iterator pointing to 4
    it = l2.begin();

    // transfer 4 at the end of l1
    l1.splice(l1.end(), l2, it);

    cout << "list l1 after splice operation" << endl;
    for (auto x : l1)
        cout << x << " ";
    return 0;
}
```

**Output:**

```cpp
list l1 after splice operation
1 2 3 4
```

### 程序 3：传送一系列元素

```cpp
// CPP program to illustrate the
// list::splice() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initializing lists and iterator
    list<int> l1 = { 1, 2, 3, 4, 5 };
    list<int> l2 = { 6, 7, 8 };
    list<int>::iterator it;

    // iterator pointing to 1
    it = l1.begin();

    // advance the iterator by 2 positions
    advance(it, 2);

    // transfer 3, 4 and 5 at the
    // beginning of l2
    l2.splice(l2.begin(), l1, it, l1.end());

    cout << "list l2 after splice operation" << endl;
    for (auto x : l2)
        cout << x << " ";
    return 0;
}
```

**Output:**

```cpp
list l2 after splice operation
3 4 5 6 7 8
```