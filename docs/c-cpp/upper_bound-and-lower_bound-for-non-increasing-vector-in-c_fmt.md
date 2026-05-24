# C++ 中非递增向量的上界和下界

> 原文：[https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-non-increasing-vector-in-c/](https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-non-increasing-vector-in-c/)

[`lower_bound()`](https://www.geeksforgeeks.org/set-lower_bound-function-in-c-stl/) 和 [`upper_bound()`](https://www.geeksforgeeks.org/stdupper_bound-in-cpp/) 函数默认作用于非递减数组。`lower_bound()` 函数查找第一个元素的迭代器，该迭代器与给定元素相比并不逊色。`upper_bound()` 函数将迭代器返回到第一个更大的元素。

给定一个将此转换为非递增向量的数组，对向量应用 `std::upper_bound` 和 `std::lower_bound` 函数。

对于在非递增数组中排序的数组，`lower_bound()` 查找第一个元素的迭代器，该元素与给定元素的比较结果不大于。`upper_bound()` 查找小于给定元素的第一个元素的迭代器。为此，我们使用了 `greater()`。

```cpp
// C++ program to demonstrate the working of lower_bound()
// and upper_bound() for array sorted in non-decreasing
// array,
#include <algorithm>
#include <iostream>
#include <vector>

int main()
{
    int unsorted[10] = { 3, 3, 2, 1, 5, 5, 4, 3, 7, 8 };
    std::vector<int> v(unsorted, unsorted + 10);

    // sorting vector in non increasing order. Vector
    // becomes {8, 7, 5, 5, 4, 3, 3, 3, 2, 1}
    std::sort(v.begin(), v.end(), std::greater<int>());

    std::vector<int>::iterator low, up;
    low = std::lower_bound(v.begin(), v.end(), 3, std::greater<int>());         
    up = std::upper_bound(v.begin(), v.end(), 5, std::greater<int>());

    std::cout << "lower_bound at position " << (low - v.begin()) << '\n';
    std::cout << "upper_bound at position " << (up - v.begin()) << '\n';

    return 0;
}
```

输出：

```cpp
lower_bound at position 5
upper_bound at position 4
```