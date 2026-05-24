# STD::b c++ 中的搜索

> 原文:[https://www.geeksforgeeks.org/stdbsearch-in-cpp/](https://www.geeksforgeeks.org/stdbsearch-in-cpp/)

[二分搜索法基础](https://www.geeksforgeeks.org/binary-search/)

STD::b 搜索在排序数组中搜索元素。在 ptr 所指向的数组中查找与键所指向的元素相等的元素。
如果数组包含几个元素，comp 将表示等于搜索到的元素，则未指定函数将返回哪个元素作为结果。
**语法:**

```cpp
void* bsearch( const void* key, const void* ptr, std::size_t count,
               std::size_t size, * comp );

Parameters :
key     -    element to be found
ptr     -    pointer to the array to examine
count    -    number of element in the array
size    -    size of each element in the array in bytes
comp    -    comparison function which returns ?a negative integer value if 
             the first argument is less than the second,
             a positive integer value if the first argument is greater than the second
             and zero if the arguments are equal.

Return value :
Pointer to the found element or null pointer if the element has not been found.

```

**实现二元谓词 comp :**

```cpp
// Binary predicate which returns 0 if numbers found equal
int comp(int* a, int* b)
{

    if (*a < *b)
        return -1;

    else if (*a > *b)
        return 1;

    // elements found equal
    else
        return 0;
}
```

**实施**

```cpp
// CPP program to implement
// std::bsearch
#include <bits/stdc++.h>

// Binary predicate
int compare(const void* ap, const void* bp)
{
    // Typecasting
    const int* a = (int*)ap;
    const int* b = (int*)bp;

    if (*a < *b)
        return -1;
    else if (*a > *b)
        return 1;
    else
        return 0;
}

// Driver code
int main()
{
    // Given array
    int arr[] = { 1, 2, 3, 4, 5, 6, 7, 8 };

    // Size of array
    int ARR_SIZE = sizeof(arr) / sizeof(arr[0]);

    // Element to be found
    int key1 = 4;

    // Calling std::bsearch
    // Typecasting the returned pointer to int
    int* p1 = (int*)std::bsearch(&key1, arr, ARR_SIZE, sizeof(arr[0]), compare);

    // If non-zero value is returned, key is found
    if (p1)
        std::cout << key1 << " found at position " << (p1 - arr) << '\n';
    else
        std::cout << key1 << " not found\n";

    // Element to be found
    int key2 = 9;

    // Calling std::bsearch
    // Typecasting the returned pointer to int
    int* p2 = (int*)std::bsearch(&key2, arr, ARR_SIZE, sizeof(arr[0]), compare);

    // If non-zero value is returned, key is found
    if (p2)
        std::cout << key2 << " found at position " << (p2 - arr) << '\n';
    else
        std::cout << key2 << " not found\n";
}
```

输出:

```cpp
4 found at position 3
9 not found

```

**在哪里使用:**二分搜索法可以用在排序的数据上，在那里可以找到一个关键字。它可以用于计算排序列表中某个键的频率。

**为什么是二分搜索法？**
二分搜索法比线性搜索有效得多，因为它在每一步都将搜索空间减半。这对于我们的长度为 9 的数组来说并不重要。这里，线性搜索最多需要 9 步，二分搜索法最多需要 4 步。但是考虑一个有 1000 个元素的数组，这里线性搜索最多需要 1000 步，而二分搜索法最多需要 10 步。
对于 10 亿元素，二分搜索法最多 30 步就能找到我们的关键。

**相关文章:**[STD::binary _ search](https://www.geeksforgeeks.org/binary-search-algorithms-the-c-standard-template-library-stl/)
本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。