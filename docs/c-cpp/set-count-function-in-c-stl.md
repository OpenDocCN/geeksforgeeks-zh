# 在 C++ STL 中设置 count()函数

> 原文:[https://www.geeksforgeeks.org/set-count-function-in-c-stl/](https://www.geeksforgeeks.org/set-count-function-in-c-stl/)

**集合::count()** 是 C++ STL 中的内置函数，它返回元素在集合中出现的次数。它只能返回 1 或 0，因为集合容器只包含唯一的元素。
**语法:**

```cpp
set_name.count(element) 
```

**参数:**该函数接受一个强制参数*元素*，该参数指定要返回其计数的元素。
**返回值:**函数返回 1 或 0，因为集合只包含唯一元素。如果集合容器中存在该值，则返回 1。如果它不在容器中，则返回 0。

**时间复杂度:**计数函数的时间复杂度为 O(log N)，其中 N 是集合中存在的元素数量

**集合中** ***计数*** **和** ***之间的差异是*** 计数分别返回 0 或 1，这取决于元素是不存在还是存在，而如果存在，则 find 函数返回指向集合中最后一个值旁边的值的迭代器。
以下是上述功能的说明。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate the
// set::count() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    int arr[] = { 14, 12, 15, 11, 10 };

    // initializes the set from an array
    set<int> s(arr, arr + 5);

    // check if 11 is present or not
    if (s.count(11))
        cout << "11 is present in the set\n";
    else
        cout << "11 is not present in the set\n";

    // checks if 18 is present or not
    if (s.count(18))
        cout << "18 is present in the set\n";
    else
        cout << "18 is not present in the set\n";

    return 0;
}
```

**Output:** 

```cpp
11 is present in the set
18 is not present in the set
```