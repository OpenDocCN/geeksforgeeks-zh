# c++ 中的下界

> 原文:[https://www.geeksforgeeks.org/lower_bound-in-cpp/](https://www.geeksforgeeks.org/lower_bound-in-cpp/)

C++ 中的**下界()**方法用于返回一个迭代器，该迭代器指向范围[第一个，最后一个]中值不小于 val 的第一个元素。这意味着该函数返回仅大于或等于下一个最小数字的索引。如果有多个值等于 val，lower_bound()将返回第一个值的索引。
该范围内的元素应已经根据 val 进行了排序或至少进行了分区。
**模板:**

> **语法 1:**
> ForwardIterator 下界(ForwardIterator 第一，ForwardIterator 最后，const T&val)；
> **语法 2:**
> ForwardIterator 下界(ForwardIterator 第一，ForwardIterator 最后，const T T&val，Compare comp)；

**参数:**以上方法接受以下参数。

*   **第一个，最后一个:**使用的范围是【第一个，最后一个】，包含第一个和最后一个之间的所有元素，包括第一个指向的元素，但不包括最后一个指向的元素。
*   **val:** 范围内要搜索的下限的值。
*   **comp:** 二元函数，接受两个参数(第一个是 ForwardIterator 指向的类型，第二个是 always val)，并返回一个可转换为 bool 的值。该函数不得修改其任何参数。这可以是函数指针，也可以是函数对象。

**返回值:**范围内 val 下限的迭代器。如果范围内的所有元素都小于 val，则函数返回最后一个。如果该范围内的所有元素都大于 val，函数将返回指向第一个元素的指针。
**例:**

```cpp
Input: 10 20 30 40 50
Output: lower_bound for element 30 at index 2

Input: 10 20 30 40 50
Output: lower_bound for element 35 at index 3

Input: 10 20 30 40 50
Output: lower_bound for element 55 at index 5

Input: 10 20 30 30 30 40 50
Output: lower_bound for element 30 at index 2

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// std :: lower_bound
#include <bits/stdc++.h>

// Driver code
int main()
{
    // Input vector
    std::vector<int> v{ 10, 20, 30, 30, 30, 40, 50 };

    // Print vector
    std::cout << "Vector contains :";
    for (unsigned int i = 0; i < v.size(); i++)
        std::cout << " " << v[i];
    std::cout << "\n";

    std::vector<int>::iterator low1, low2, low3;

    // std :: lower_bound
    low1 = std::lower_bound(v.begin(), v.end(), 30);
    low2 = std::lower_bound(v.begin(), v.end(), 35);
    low3 = std::lower_bound(v.begin(), v.end(), 55);

    // Printing the lower bounds
    std::cout
        << "\nlower_bound for element 30 at position : "
        << (low1 - v.begin());
    std::cout
        << "\nlower_bound for element 35 at position : "
        << (low2 - v.begin());
    std::cout
        << "\nlower_bound for element 55 at position : "
        << (low3 - v.begin());

    return 0;
}
```

**Output:** 

```cpp
Vector contains : 10 20 30 30 30 40 50

lower_bound for element 30 at position : 2
lower_bound for element 35 at position : 5
lower_bound for element 55 at position : 7

```

**时间复杂度:**进行比较的次数是对数的。因此，上述方法的时间复杂度为 **O(logN)** ，其中 N =大小。(倒数第一)

本文由 [**沙钦·毕斯特**](https://www.linkedin.com/in/sachin-bisht-984b5013a/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。