# forward_list::unique()在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/forward_listunique-in-c-stl/](https://www.geeksforgeeks.org/forward_listunique-in-c-stl/)

**forward_list::unique()** 是 C++ STL 中的一个内置函数，用于从 forward_list 中移除所有连续的重复元素。它使用二元谓词进行比较。

**语法:**

```cpp
forwardlist_name.unique(BinaryPredicate name)
```

**参数:**该函数接受一个参数，该参数是一个*二元谓词*，如果元素应该被视为相等，则返回真。它有以下语法:

```cpp
bool name(data_type a, data_type a)
```

**返回值:**函数不返回任何内容。

```cpp
// C++ program to illustrate the
// unique() function
#include <bits/stdc++.h>
using namespace std;

// Function for binary_predicate
/*bool compare(int a, int b)
{
    return (abs(a) == abs(b));
}
// This function can also be used and passed inside
// unique(), to get the same result
*/

int main()
{

    forward_list<int> list = { 1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 2, 4, 4 };

    cout << "List of elements before unique operation is: ";

    // starts from the first element of the list to the last
    for (auto it = list.begin(); it != list.end(); ++ it)
        cout << *it << " ";

    // unique operation on forward list
    list.unique();
    cout << "\nList of elements after unique operation is: ";

    // starts from the first element of the list to the last
    for (auto it = list.begin(); it != list.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**输出:**

```cpp
List of elements before unique operation is: 1 1 1 1 2 2 2 2 3 3 3 2 4 4 
List of elements after unique operation is: 1 2 3 2 4

```