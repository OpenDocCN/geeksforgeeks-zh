# c++ 中的 partition _ point

> 原文:[https://www.geeksforgeeks.org/partition_point-in-cpp/](https://www.geeksforgeeks.org/partition_point-in-cpp/)

**partition_point()** 获取分区点:返回分区范围**【第一个，最后一个】**中 pred(谓词)不为真的第一个元素的迭代器，指示其分区点。

范围中的元素应该已经被分区，就好像分区是用相同的参数调用的一样。

该函数通过比较排序范围的非连续元素来优化比较的次数，这对于随机访问迭代器特别有效。

**语法:**

> ```cpp
>   ForwardIterator partition_point(ForwardIterator first, 
>                                   ForwardIterator last,
>                                   UnaryPredicate pred); 
> ```
> 
> **参数:**
> **第一个，最后一个:**
> 将迭代器转发到分区序列的初始和最终位置。检查的范围是[第一个，最后一个]，它包含第一个和最后一个之间的所有元素，包括第一个指向的元素，但不包括最后一个指向的元素。
> 
> **pred**
> 一元函数，接受范围内的一个元素作为参数，并返回一个可转换为 bool 的值。返回的值指示元素是否在分区点之前(如果为真，则在分区点之前；如果 false 出现在它的前面或后面)。函数不得修改其参数。这可以是函数指针，也可以是函数对象。
> 
> **返回值:**
> 分区范围内 pred 不为真的第一个元素(第一个，最后一个)的迭代器，如果任何元素都不为真，则为最后一个。

这个函数模板的定义相当于:

```cpp
template 
  ForwardIterator partition_point (ForwardIterator first, ForwardIterator last,
                                   UnaryPredicate pred)
{
  auto n = distance(first, last);
  while (n>0)
  {
    ForwardIterator it = first;
    auto step = n/2;
    std::advance (it, step);
    if (pred(*it)) { first=++ it; n-=step+1; }
    else n=step;
  }
  return first;
}

```

**例 1:**

```cpp
// C++ program to get odd elements
// and even elements
#include <iostream> // std::cout
#include <algorithm> // std::partition, std::partition_point
#include <vector> // std::vector

bool IsOdd(int i) { return (i % 2) == 1; }

int main()
{
    std::vector<int> data{ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
    std::vector<int> odd, even;

    // partition data on the basis of odd elements 
    // using pred IsOdd()
    std::stable_partition(data.begin(), data.end(), IsOdd);

    // gets the partition point based on odd elements
    auto it = std::partition_point(data.begin(), data.end(), 
                                                     IsOdd);

    // assign elements to odd from beginning till partition 
    // point.
    odd.assign(data.begin(), it);
    even.assign(it, data.end());

    // print contents of odd:
    std::cout << "odd:";
    for (int& x : odd)
        std::cout << ' ' << x;
    std::cout << '\n';

    // print contents of even:
    std::cout << "even:";
    for (int& x : even)
        std::cout << ' ' << x;
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
odd:  1 3 5 7 9
even: 2 4 6 8 10

```

**例 2:**

```cpp
// C++ program to get negative elements
// and positive elements using partition_point
#include <iostream> // std::cout
#include <algorithm> // std::partition, std::partition_point
#include <vector> // std::vector

bool IsNegative(int i) { return (i < 0); }

int main()
{
    std::vector<int> data{ 1, -1, 3, -4, 5, 2, -2, 4, 
                                             -5, -3 };
    std::vector<int> negative, positive;

    // partition data on the basis of odd elements using 
    // pred IsNegative()
    std::stable_partition(data.begin(), data.end(), 
                                       IsNegative);

    // gets the partition point based on odd elements
    auto it = std::partition_point(data.begin(), data.end(), 
                                                 IsNegative);

    // assign elements to odd from beginning till
    // partition point.
    negative.assign(data.begin(), it);
    positive.assign(it, data.end());

    // print contents of odd:
    std::cout << "Negative: ";
    for (int& x : negative)
        std::cout << ' ' << x;
    std::cout << '\n';

    // print contents of even:
    std::cout << "Positive: ";
    for (int& x : positive)
        std::cout << ' ' << x;
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
Negative:  -1 -4 -2 -5 -3
Positive:  1 3 5 2 4

```

**复杂度:**
执行大约 log2(N)+2 个元素的比较(其中 N 是这个距离)。在非随机访问迭代器上，迭代器的进步平均会产生额外的线性复杂度。

本文由 [**舒巴姆拉纳**](https://auth.geeksforgeeks.org/profile.php?user=shubham_rana_77&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。