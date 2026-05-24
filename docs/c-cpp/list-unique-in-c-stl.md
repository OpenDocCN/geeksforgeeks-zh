# 在 C++ STL 中列出唯一的()

> 原文:[https://www.geeksforgeeks.org/list-unique-in-c-stl/](https://www.geeksforgeeks.org/list-unique-in-c-stl/)

**list::unique()** 是 C++ STL 中的一个内置函数，用于从列表中移除所有重复的连续元素。它只适用于**排序的**列表。

**语法:**

```cpp
list_name.unique(BinaryPredicate name)
```

**参数:**该函数接受一个可选参数，该参数是一个二元谓词，如果元素应该被视为相等，则返回 true。它有以下语法:

```cpp
bool name(data_type a, data_type b);
```

**返回值**:该功能不返回任何内容。

以下是上述功能的实现:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// unique() function
#include <bits/stdc++.h>
using namespace std;

// Function for binary_predicate
bool compare(double a, double b)
{
    return ((int)a == (int)b);
}

// Driver code
int main()
{
    list<double> list = { 2.55, 3.15, 4.16, 4.16,
                          4.77, 12.65, 12.65, 13.59 };

    cout << "List is: ";

    //sort the list
    list.sort();

    // unique operation on list with no parameters
    list.unique();

    // starts from the first element
    // of the list to the last
    for (auto it = list.begin(); it != list.end(); ++ it)
        cout << *it << " ";

    // unique operation on list with parameter
    list.unique(compare);

    cout << "\nList is: ";

    // starts from the first element
    // of the list to the last
    for (auto it = list.begin(); it != list.end(); ++ it)
        cout << *it << " ";

    return 0;
}
```

**Output**

```cpp
List is: 2.55 3.15 4.16 4.77 12.65 13.59 
List is: 2.55 3.15 4.16 12.65 13.59 
```