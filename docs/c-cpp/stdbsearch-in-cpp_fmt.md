# std::bsearch in C++

> 原文: [https://www.geeksforgeeks.org/stdbsearch-in-cpp/](https://www.geeksforgeeks.org/stdbsearch-in-cpp/)

[二分搜索法基础](https://www.geeksforgeeks.org/binary-search/)

`std::bsearch` 在排序数组中搜索元素。在 `ptr` 所指向的数组中查找与 `key` 所指向的元素相等的元素。
如果数组包含多个元素，`comp` 将表示等于搜索到的元素，则未指定函数将返回哪个元素作为结果。

## 语法

```cpp
void* bsearch( const void* key, const void* ptr, std::size_t count,
               std::size_t size, int (*comp)(const void*, const void*) );
```

## 参数

- `key` - 要查找的元素
- `ptr` - 指向待检查数组的指针
- `count` - 数组中的元素数量
- `size` - 数组中每个元素的大小（以字节为单位）
- `comp` - 比较函数，如果第一个参数小于第二个，返回负整数值；如果第一个参数大于第二个，返回正整数值；如果参数相等，则返回零。

## 返回值

指向找到元素的指针，如果未找到元素，则返回空指针。

## 实现二元谓词 `comp`

```cpp
// 二元谓词，如果找到的数字相等则返回 0
int comp(int* a, int* b)
{
    if (*a < *b)
        return -1;
    else if (*a > *b)
        return 1;
    // 元素相等
    else
        return 0;
}
```

## 实现示例

```cpp
// CPP program to implement
// std::bsearch
#include <bits/stdc++.h>

// 二元谓词
int compare(const void* ap, const void* bp)
{
    // 类型转换
    const int* a = (int*)ap;
    const int* b = (int*)bp;

    if (*a < *b)
        return -1;
    else if (*a > *b)
        return 1;
    else
        return 0;
}

// 驱动代码
int main()
{
    // 给定数组
    int arr[] = { 1, 2, 3, 4, 5, 6, 7, 8 };

    // 数组大小
    int ARR_SIZE = sizeof(arr) / sizeof(arr[0]);

    // 要查找的元素
    int key1 = 4;

    // 调用 std::bsearch
    // 将返回的指针类型转换为 int
    int* p1 = (int*)std::bsearch(&key1, arr, ARR_SIZE, sizeof(arr[0]), compare);

    // 如果返回非零值，则找到 key
    if (p1)
        std::cout << key1 << " found at position " << (p1 - arr) << '\n';
    else
        std::cout << key1 << " not found\n";

    // 要查找的元素
    int key2 = 9;

    // 调用 std::bsearch
    // 将返回的指针类型转换为 int
    int* p2 = (int*)std::bsearch(&key2, arr, ARR_SIZE, sizeof(arr[0]), compare);

    // 如果返回非零值，则找到 key
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

## 在哪里使用

二分搜索法可以用在排序的数据上，在那里可以找到一个关键字。它可以用于计算排序列表中某个键的频率。

## 为什么是二分搜索法？

二分搜索法比线性搜索有效得多，因为它在每一步都将搜索空间减半。这对于我们的长度为 9 的数组来说并不重要。这里，线性搜索最多需要 9 步，二分搜索法最多需要 4 步。但是考虑一个有 1000 个元素的数组，这里线性搜索最多需要 1000 步，而二分搜索法最多需要 10 步。
对于 10 亿元素，二分搜索法最多 30 步就能找到我们的关键。

## 相关文章

[std::binary_search](https://www.geeksforgeeks.org/binary-search-algorithms-the-c-standard-template-library-stl/)

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。