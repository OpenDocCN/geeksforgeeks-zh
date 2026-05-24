# std::remove，std::remove_if 在 c++ 中

> 原文:[https://www.geeksforgeeks.org/stdremove-stdremove_if-c/](https://www.geeksforgeeks.org/stdremove-stdremove_if-c/)

**标准::移除**

在<algorithm>库中定义。它从范围中移除值。将范围[第一个，最后一个]转换为移除了所有与 val 比较相等的元素的范围，并返回一个迭代器到该范围的新端点。</algorithm>

*   该函数不能改变包含元素范围的对象的属性(即它**不能改变数组或容器**的大小)。
*   未移除元素的相对顺序被保留，而返回的迭代器和 last 之间的元素保持有效但未指定的状态。
*   该函数使用运算符==将单个元素与 val 进行比较。

**功能模板:**

```cpp
ForwardIterator remove  (ForwardIterator first,
ForwardIterator last, const T& val)

first,last :
  The range used is [first,last), which contains all the
elements between first and last, including the element
pointed by first but not the element pointed by last.

val :
Value to be removed.

Return value :
An iterator to the element that follows the last element not removed.
The range between first and this iterator includes all the elements
in the sequence that do not compare equal to val.
```

示例:

```cpp
Input : 10 20 30 30 20 10 10 20
Output : 10 30 30 10 10    // Value removed is 20.
```

**std :: remove_if**

将范围[第一个，最后一个]转换为一个范围，去掉 pred 返回 true 的所有元素，并返回一个迭代器到该范围的新端点。
**功能模板:**

```cpp
 ForwardIterator remove_if (ForwardIterator first,
 ForwardIterator last, UnaryPredicate pred);

pred
Unary function that accepts an element in the range as
argument, and returns a value convertible to bool. The
value returned indicates whether the element is to be
removed (if true, it is removed).
The function shall not modify its argument.
This can either be a function pointer or a function object.
```

示例:

```cpp
Input : 1 2 3 4 5 6 7 8 9 10
Output : 2 4 6 8 10    // Odd elements removed. 
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// std::remove and std::remove_if
// algorithm
#include <bits/stdc++.h>

// Function to check whether
// the element is odd or not.
bool IsOdd(int i) { return ((i % 2) == 1); }

// Driver code
int main()
{
    std ::vector<int> vec1{
        10, 20, 30, 30, 20, 10, 10, 20
    };
    std ::vector<int> vec2{ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

    // Print original vector
    std ::cout << "Original vector : ";
    for (int i = 0; i < vec1.size(); i++)
        std ::cout << " " << vec1[i];
    std ::cout << "\n";

    // Iterator that store the position of last element
    std ::vector<int>::iterator pend;

    // std ::remove function call
    pend = std ::remove(vec1.begin(), vec1.end(), 20);

    // Print the vector
    std ::cout << "After remove : ";
    for (std ::vector<int>::iterator p = vec1.begin();
         p != pend; ++ p)
        std ::cout << ' ' << *p;
    std ::cout << '\n';

    // Print original vector
    std ::cout << "\nOriginal vector : ";
    for (int i = 0; i < vec2.size(); i++)
        std ::cout << " " << vec2[i];
    std ::cout << "\n";

    // std ::remove_if function call
    pend = std ::remove_if(vec2.begin(), vec2.end(), IsOdd);

    // the same of the above can be done using lambda
    // function in 1 line
    pend = std ::remove_if(
        vec2.begin(), vec2.end(),
        [](int i) { return ((i % 2) == 1); });

    // Print the vector
    std ::cout << "After remove_if : ";
    for (std ::vector<int>::iterator q = vec2.begin();
         q != pend; ++ q)
        std ::cout << ' ' << *q;
    std ::cout << '\n';

    return 0;
}
```

**输出:**

```cpp
Original vector :  10 20 30 30 20 10 10 20
After remove :  10 30 30 10 10

Original vector :  1 2 3 4 5 6 7 8 9 10
After remove_if :  2 4 6 8 10
```

本文由 [**沙钦·毕斯特**](https://www.linkedin.com/in/sachin-bisht-984b5013a/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。