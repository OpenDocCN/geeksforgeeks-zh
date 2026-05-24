# std::相邻 _ 在 C++ 中查找

> 原文:[https://www.geeksforgeeks.org/stdadjacent_find-in-c/](https://www.geeksforgeeks.org/stdadjacent_find-in-c/)

在范围[第一个，最后一个]中搜索匹配的两个连续元素的第一次出现，并返回这两个元素中第一个元素的迭代器，如果没有找到这样的对，则返回最后一个元素。使用给定的二进制谓词 p 或使用==，对元素进行比较。
该函数有两种可能的实现方式，如下所示:

**1。无二元谓词:**

```cpp
ForwardIt adjacent_find( ForwardIt first, ForwardIt last );
first, last : the range of elements to examine
```

**示例:**
给定包含除一个元素之外的所有唯一元素的 n 个元素的排序数组，任务是找到数组中的重复元素。

示例:

```cpp
Input :  arr[] = { 1, 2, 3, 4, 4}
Output :  4

Input :  arr[] = { 1, 1, 2, 3, 4}
Output :  1
```

我们已经用其他方法讨论了这个问题[这里](https://www.geeksforgeeks.org/find-repeating-element-sorted-array-size-n/)。

## C++

```cpp
// C++ Program to find the only
// repeating element in sorted array
// using std :: adjacent_find
// without predicate
#include <iostream>
#include <algorithm>

int main()
{
    // Sorted Array with a repeated element
    int A[] = { 10, 13, 16, 16, 18 };

    // Size of the array
    int n = sizeof(A) / sizeof(A[0]);

    // Iterator pointer which points to the address of the repeated element
    int* it = std::adjacent_find(A, A + n);

    // Printing the result
    std::cout << *it;
}
```

输出:

```cpp
16
```

**2。带二元谓词:**

```cpp
ForwardIt adjacent_find( ForwardIt first, ForwardIt last, BinaryPredicate p );
first, last : the range of elements to examine
p :  binary predicate which returns true 
if the elements should be treated as equal. 

Return value :
An iterator to the first of the first pair of identical elements, '
that is, the first iterator it such that *it == *(it+1) for the first 
version or p(*it, *(it + 1)) != false for the second version.
If no such elements are found, last is returned.
```

**示例:**
给定一个大小为 n 的容器，并且范围在[0 … n]之间，编写一个程序来检查它是否按升序排序。数组中允许相等的值，并且两个连续的相等值被视为已排序。

```cpp
Input : 2 5 9 4      // Range = 3
Output : Sorted in given range.

Input : 3 5 1 9     // Range = 3
Output : Not sorted in given range.
```

## C++

```cpp
// CPP program to illustrate
// std :: adjacent_find'
// with binary predicate
#include <algorithm>
#include <iostream>
#include <vector>

int main()
{
    std::vector<int> vec{ 0, 1, 2, 5, 40, 40, 41, 41, 5 };

    // Index 0 to 4
    int range1 = 5;

    // Index 0 to 8
    int range2 = 9;

    std::vector<int>::iterator it;

    // Iterating from 0 to range1,
    // till we get a decreasing element
    it = std::adjacent_find(vec.begin(),
                            vec.begin() + range1, std::greater<int>());

    if (it == vec.begin() + range1)
    {
        std::cout << "Sorted in the range : " << range1 << std::endl;
    }

    else
    {
        std::cout << "Not sorted in the range : " << range1 << std::endl;
    }

    // Iterating from 0 to range2,
    // till we get a decreasing element
    it = std::adjacent_find(vec.begin(),
                            vec.begin() + range2, std::greater<int>());

    if (it == vec.begin() + range2)
    {
        std::cout << "Sorted in the range : " << range2 << std::endl;
    }

    else
    {
        std::cout << "Not sorted in the range : " << range2 << std::endl;
    }
}
```

输出:

```cpp
Sorted in the range : 5
Not sorted in the range : 9
```

本文由 [**罗希特·塔普利亚尔**](https://www.linkedin.com/in/rohit-thapliyal-515b5913a/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。