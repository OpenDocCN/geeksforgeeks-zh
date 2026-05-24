# C++ STL 中的二分搜索法函数（二分查找，下界和上界）

> 原文：[https://www.geeksforgeeks.org/binary-search-functions-in-c-stl-binary_search-lower_bound-and-upper_bound/](https://www.geeksforgeeks.org/binary-search-functions-in-c-stl-binary_search-lower_bound-and-upper_bound/)

二分搜索法是竞争性编程或任何算法竞赛中的一个重要组成部分，掌握速记函数的知识可以减少编码时间。该搜索仅在容器被**排序**时有效。下面讨论相关功能。

## `binary_search(start_ptr, end_ptr, num)`

如果容器中存在元素，则此函数返回布尔值 `true`，否则返回 `false`。

```cpp
// C++ code to demonstrate the working of binary_search()

#include<bits/stdc++.h>
using namespace std;

int main()
{
    // initializing vector of integers
    vector<int> arr = {10, 15, 20, 25, 30, 35};

    // using binary_search to check if 15 exists
    if (binary_search(arr.begin(), arr.end(), 15))
       cout << "15 exists in vector";
    else
       cout << "15 does not exist";

    cout << endl;

    // using binary_search to check if 23 exists
    if (binary_search(arr.begin(), arr.end(), 23))
         cout << "23 exists in vector";
    else
         cout << "23 does not exist";

    cout << endl;   
}
```

输出：

```cpp
15 exists in vector
23 does not exist
```

## `lower_bound(start_ptr, end_ptr, num)`

如果容器包含 `num` 的 **1** 次出现，则返回指向 `num` 的“**位置**”指针。如果容器包含 `num` 的多次出现，则将指针返回到 `num` 的**第一个位置**。如果容器**不包含** `num` 的出现，则返回指针到比 `num` 高的下一个数字的**位置**。减去指向第一个位置的指针，即 `vect.begin()` 返回实际索引。

```cpp
// C++ code to demonstrate the working of lower_bound()
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // initializing vector of integers
    // for single occurrence
    vector<int> arr1 = {10, 15, 20, 25, 30, 35};

    // initializing vector of integers
    // for multiple occurrences
    vector<int> arr2 = {10, 15, 20, 20, 25, 30, 35};

    // initializing vector of integers
    // for no occurrence
    vector<int> arr3 = {10, 15, 25, 30, 35};

    // using lower_bound() to check if 20 exists
    // single occurrence
    // prints 2
    cout << "The position of 20 using lower_bound "
            " (in single occurrence case) : ";
    cout << lower_bound(arr1.begin(), arr1.end(), 20)
            - arr1.begin();

    cout << endl;

    // using lower_bound() to check if 20 exists
    // multiple occurrence
    // prints 2
    cout << "The position of 20 using lower_bound "
             "(in multiple occurrence case) : ";
    cout << lower_bound(arr2.begin(), arr2.end(), 20)
            - arr2.begin();

    cout << endl;

    // using lower_bound() to check if 20 exists
    // no occurrence
    // prints 2 ( index of next higher)
    cout << "The position of 20 using lower_bound "
             "(in no occurrence case) : ";
    cout << lower_bound(arr3.begin(), arr3.end(), 20)
            - arr3.begin();

    cout << endl;   
}
```

**输出：**

```cpp
The position of 20 using lower_bound (in single occurrence case) : 2
The position of 20 using lower_bound (in multiple occurrence case) : 2
The position of 20 using lower_bound (in no occurrence case) : 2
```

## `upper_bound(start_ptr, end_ptr, num)`

如果容器包含 `num` 的 **1** 次出现，则返回指向比 `num` 高的下一个数字的“**位置**”的指针。如果容器包含 `num` 的多次出现，则将指针返回到 `num` 的**第一个位置**，该位置比 `num` 的**最后一次出现**高。如果容器**不包含** `num` 的出现，则将指针返回到比 `num` 高的下一个数字的**位置**。减去指向第一个位置的指针，即 `vect.begin()` 返回实际的索引。

二分搜索法是最有效的搜索算法。

```cpp
// C++ code to demonstrate the working of upper_bound()
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // initializing vector of integers
    // for single occurrence
    vector<int> arr1 = {10, 15, 20, 25, 30, 35};

    // initializing vector of integers
    // for multiple occurrences
    vector<int> arr2 = {10, 15, 20, 20, 25, 30, 35};

    // initializing vector of integers
    // for no occurrence
    vector<int> arr3 = {10, 15, 25, 30, 35};

    // using upper_bound() to check if 20 exists
    // single occurrence
    // prints 3
    cout << "The position of 20 using upper_bound"
           " (in single occurrence case) : ";
    cout << upper_bound(arr1.begin(), arr1.end(), 20)
            - arr1.begin();

    cout << endl;

    // using upper_bound() to check if 20 exists
    // multiple occurrence
    // prints 4
    cout << "The position of 20 using upper_bound "
             "(in multiple occurrence case) : ";
    cout << upper_bound(arr2.begin(), arr2.end(), 20)
            - arr2.begin();

    cout << endl;

    // using upper_bound() to check if 20 exists
    // no occurrence
    // prints 2 ( index of next higher)
    cout << "The position of 20 using upper_bound"
            " (in no occurrence case) : ";
    cout << upper_bound(arr3.begin(), arr3.end(), 20)
           - arr3.begin();

    cout << endl;   
}
```

**输出：**

```cpp
The position of 20 using upper_bound (in single occurrence case) : 3
The position of 20 using upper_bound (in multiple occurrence case) : 4
The position of 20 using upper_bound (in no occurrence case) : 2
```

**时间复杂度：**`O(logN)` - 其中 `N` 是数组中元素的个数。

本文由 Manjeet Singh (HBD) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。