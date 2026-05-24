# 标准::C++ 中的 iota

> 原文:[https://www.geeksforgeeks.org/std-iota-in-cpp/](https://www.geeksforgeeks.org/std-iota-in-cpp/)

**存储递增序列**
为 val 的[第一个，最后一个]连续值范围内的每个元素赋值，就像每个元素写入后用++ val 递增一样。

**模板:**

```cpp
void iota (ForwardIterator first, ForwardIterator last, T val);

Parameters :

first, last
Forward iterators to the initial and final positions of the sequence
to be written. The range used is [first, last), which contains all the
elements between first and last, including the element pointed by
first but not the element pointed by last.

val
Initial value for the accumulator. 

Return Type :
None
```

## C++

```cpp
// C++ program to illustrate
// std :: iota
#include <iostream> // std::cout
#include <numeric> // std::iota

// Driver code
int main()
{
    int numbers[10];
    // Initialising starting value as 100
    int st = 100;

    std::iota(numbers, numbers + 10, st);

    std::cout << "Elements are :";
    for (auto i : numbers)
        std::cout << ' ' << i;
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
Elements are : 100 101 102 103 104 105 106 107 108 109
```

**应用:**
可以用来生成连续的数字序列。

## C++

```cpp
// C++ program to generate
// a sequence of numbers using std :: iota
#include <iostream> // std::cout
#include <numeric> // std::iota

// Driver code
int main()
{
    int numbers[11];
    // Initialising starting value as 10
    int st = 10;

    std::iota(numbers, numbers + 11, st);

    std::cout << "Elements are :";
    for (auto i : numbers)
        std::cout << ' ' << i;
    std::cout << '\n';

    return 0;
}
```

输出:

```cpp
Elements are : 10 11 12 13 14 15 16 17 18 19 20
```

本文由**沙钦·毕斯特**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。