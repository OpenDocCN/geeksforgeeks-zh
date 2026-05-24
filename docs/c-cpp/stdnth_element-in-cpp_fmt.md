# std::nth_element in C++

> 原文: [https://www.geeksforgeeks.org/stdnth_element-in-cpp/](https://www.geeksforgeeks.org/stdnth_element-in-cpp/)

## 简介

``std::nth_element()`` 是一种 STL 算法，它以这样一种方式重新排列列表，即如果我们对列表进行排序，第 n 个位置的元素就是应该在该位置的元素。

它不会对列表进行排序，只是第 n 个元素之前的所有元素都不会大于它，之后的所有元素都不会小于它。

## 语法

有两个版本，定义如下：

### 1. 比较元素

```cpp
template <class RandomAccessIterator>
void nth_element (RandomAccessIterator first, RandomAccessIterator nth,
                  RandomAccessIterator last);
```

- ``first``: 指向列表中第一个元素的随机访问迭代器。
- ``last``: 指向列表中最后一个元素的随机访问迭代器。
- ``nth``: 指向列表中应被排序位置的随机访问迭代器。如果它指向 ``end``，那么这个函数将不做任何事。

**返回值**：由于返回类型是 ``void``，所以它不返回任何值。

```cpp
// C++ program to demonstrate the use of std::nth_element
#include <iostream>
#include <algorithm>
using namespace std;
int main()
{
    int v[] = { 3, 2, 10, 45, 33, 56, 23, 47 }, i;

    // Using std::nth_element with n as 5
    std::nth_element(v, v + 4, v + 8);

    // Since, n is 5 so 5th element should be sorted
    for (i = 0; i < 8; ++ i) {
        cout << v[i] << " ";
    }
    return 0;
}
```

**输出**:

```
3 2 10 23 33 56 45 47
```

在这里，第五个元素是 ``33``，它左边的所有元素都比它小，右边的所有元素都比它大。

### 2. 使用预定义函数进行比较

```cpp
template <class RandomAccessIterator, class Compare>
void nth_element (RandomAccessIterator first, RandomAccessIterator nth,
                  RandomAccessIterator last, Compare comp);
```

这里，``first``、``last`` 和 ``nth`` 参数与前一种情况相同。

- ``comp``: 二元函数，接受范围内的两个元素作为参数，并返回可转换为 ``bool`` 的值。返回的值表示作为第一个参数传递的元素是否被认为在它定义的特定严格弱排序中排在第二个参数之前。该函数不得修改其任何参数。这可以是函数指针或函数对象。

**返回值**：由于其返回类型是 ``void``，所以它不返回任何值。

```cpp
// C++ program to demonstrate the use of std::nth_element
#include <iostream>
#include <algorithm>
using namespace std;

// Defining the BinaryFunction
bool comp(int a, int b)
{
    return (a < b);
}
int main()
{
    int v[] = { 3, 2, 10, 45, 33, 56, 23, 47 }, i;

    // Using std::nth_element with n as 6
    std::nth_element(v, v + 5, v + 8, comp);

    // Since, n is 6 so 6th element should be the same
    // as the sixth element present if we sort this array
    // Sorted Array
    /* 2 3 10 23 33 45 47 56 */
    for (i = 0; i < 8; ++ i) {
        cout << v[i] << " ";
    }
    return 0;
}
```

**输出**:

```
33 2 10 23 3 45 47 56
```

在这段代码中，由于 ``std::nth_element`` 中第二个参数指向的第 n 个元素是数组 ``v`` 的第六个元素，这意味着应用 ``std::nth_element`` 后，数组中的第六个元素应该是整个数组排序后将出现在该位置的元素，即 ``45``。

它左边的所有元素都小于或等于它，右边的元素都大于它。

**二元函数 ``comp`` 的目的**：``std::nth_element`` 将范围 ``[first, last]`` 部分按升序排序，使得对于范围 ``[first, nth]`` 中的任意 ``i`` 和范围 ``[nth, last]`` 中的任意 ``j``，满足 ``!(*j < *i)``。因此，``comp()`` 用于确保第 n 个元素之前的所有元素都小于第 n 个元素之后的元素。

## 应用场景

1.  如果我们想找到**前 n 个最小的数**，但它们可以有序也可以无序，就可以使用它。

```cpp
// C++ program to find first n smallest numbers
#include <iostream>
#include <algorithm>
using namespace std;
int main()
{
    int v[] = { 30, 20, 10, 40, 60, 50, 70, 80 }, i;

    // Using std::nth_element with n as 3
    std::nth_element(v, v + 2, v + 8);

    // Since, n is 3 so now first three numbers will be the
    // three smallest numbers in the whole array
    // Displaying first three smallest number
    for (i = 0; i < 3; ++ i)
    {
        cout << v[i] << " ";
    }
    return 0;
}
```

**输出**:

```
20 10 30
```

2.  就像找前 n 个最小的数一样，我们也可以通过简单地更改传递给 ``std::nth_element`` 的二元函数来找到**前 n 个最大的数**。

```cpp
// C++ program to find first n largest numbers
#include <iostream>
#include <algorithm>
using namespace std;
int main()
{
    int v[] = { 30, 20, 50, 60, 70, 10, 80, 40 }, i;

    // Using std::nth_element with n as 2
    std::nth_element(v, v + 1, v + 8, std::greater<int>());

    // Since, n is 2 so first 2 elements will be the largest
    // among all the array elements
    // Displaying First 2 elements
    for (i = 0; i < 2; ++ i)
    {
        cout << v[i] << " ";
    }
    return 0;
}
```

**输出**:

```
80 70
```

在这里，我们传递了 ``std::greater<int>()`` 作为二元函数，所以现在第 n 个元素将是如果我们按降序对给定数组进行排序时应该在第 n 个位置的元素，那么前 n 个元素将是前 n 个最大的元素。

3.  可以用来求给定元素的**中值**。

```cpp
// C++ program to find the median of the vector
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
int main()
{
    vector<int> v = { 3, 2, 10, 45, 33, 56, 23, 47, 60 }, i;

    // Using std::nth_element with n as v.size()/2 + 1
    std::nth_element(v.begin(), v.begin() + v.size() / 2, v.end());

    cout << "The median of the array is " << v[v.size() / 2];

    return 0;
}
```

**输出**:

```
The median of the array is 33
```

这里排序后的数组将是 ``2 3 10 23 33 45 47 56 60``，因此有 9 个元素，中间值将是中间元素，即第 5 个元素：``33``。

## 时间复杂度

``std::nth_element()`` 的时间复杂度：``O(n)``，其中 ``n`` 是 ``first`` 和 ``last`` 之间的距离。

## 相关文章

- [std::search](https://www.geeksforgeeks.org/stdsearch-in-c/)
- [std::find](https://www.geeksforgeeks.org/stdfind-in-c/)
- [std::find_if, std::find_if_not](https://www.geeksforgeeks.org/stdfind_if-stdfind_if_not-in-c/)
- [std::find_end](https://www.geeksforgeeks.org/stdfind_end-in-cpp/)
- [std::sort](https://www.geeksforgeeks.org/sort-c-stl/)

本文由 **姆里根德拉·辛格** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。