# 在 C++ STL 中设置 find()函数

> 原文:[https://www.geeksforgeeks.org/set-find-function-in-c-stl/](https://www.geeksforgeeks.org/set-find-function-in-c-stl/)

**集合::find** 是 C++ STL 中的内置函数，它向集合容器中搜索到的元素返回一个迭代器。如果没有找到元素，那么它将返回下一个更大的元素的位置，如果下一个更大的元素不存在，那么迭代器指向集合中最后一个元素之后的位置。

**语法:**

```cpp

set_name.find(element) 
```

**参数:**该函数接受一个强制参数*元素*，该参数指定要在集合容器中搜索的元素。
**返回值:**该函数返回一个迭代器，该迭代器指向在集合容器中搜索的元素。如果没有找到该元素，则迭代器指向集合中最后一个元素之后的位置。
下面的程序说明了上述功能。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate the
// set::find() function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    // Initialize set
    set<int> s;

    s.insert(1);
    s.insert(4);
    s.insert(2);
    s.insert(5);
    s.insert(3);

    // iterator pointing to
    // position where 3 is
    auto pos = s.find(3);

    // prints the set elements
    cout << "The set elements after 3 are: ";
    for (auto it = pos; it != s.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**Output:** 

```cpp
The set elements after 3 are: 3 4 5
```

**时间复杂度:**set _ name . find(key)的时间复杂度为 **O( log N )** 。因为默认情况下元素是以排序的方式存储的。