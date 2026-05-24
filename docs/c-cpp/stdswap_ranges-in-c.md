# 标准::C++ 中的 swap _ ranges

> 原文:[https://www.geeksforgeeks.org/stdswap_ranges-in-c/](https://www.geeksforgeeks.org/stdswap_ranges-in-c/)

**std::swap** 用于两个容器之间的元素交换。它的一个变体是**标准::swap_ranges，**，顾名思义，它用于交换范围内的元素。

它只是将范围[first1，last1 中每个元素的值与从 first2 开始的范围中它们各自元素的值进行交换。如果我们看一下它的内部工作，我们会发现这个函数本身使用了 std::swap()。

语法:

```cpp
std::swap_ranges (ForwardIterator1 first1, ForwardIterator1 last1,
                  ForwardIterator2 first2);

Here, first1, last1 and first2 are forward iterators.
Returns: It returns an iterator to the last element swapped in the second sequence.

```

```cpp
// C++ program to demonstrate 
// the use of std::swap_ranges
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
int main()
{
    // Declaring first vector
    vector<int> v1;
    int i;

    // v1 contains 0 1 2 3 4 5 6 7 8 9
    for (i = 0; i < 10; ++ i) 
    {
        v1.push_back(i);
    }

    // Declaring second vector
    // v2 contains 100 100 100 100 100
    vector<int> v2(5, 100);

    // Performing swap
    std::swap_ranges(v1.begin() + 3, v1.begin() + 7, v2.begin());

    // Displaying v1 after swapping
    for (i = 0; i < 10; ++ i) 
    {
        cout << v1[i] << " ";
    }

    cout << "\n";

    // Displaying v2 after swapping
    for (i = 0; i < 5; ++ i) 
    {
        cout << v2[i] << " ";
    }

    return 0;
}
```

输出:

```cpp
0 1 2 100 100 100 100 7 8 9
3 4 5 6 100

```

这里，在这个程序中，我们交换了从 v1.begin()+3 开始到 v1.begin()+7 的元素，值从 v2.begin()开始，所以我们在一个范围内执行了交换，而不是交换整个向量。

**哪里可以用？**
当我们必须找出一个给定的容器在前半部分和后半部分是否包含相同的元素时，即**两个半部分是否相同时，可以使用它。**

```cpp
// C++ program to demonstrate 
// the use of std::swap_ranges
#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;
int main()
{
    // Here 5 is the central element and the two halves
    // on its either side contain the same elements 1 2 3 4
    vector<int> v1 = { 1, 2, 3, 4, 5, 1, 2, 3, 4 };

    int i;

    // Declaring second vector and making it equal to v1
    vector<int> v2 = v1;

    // Here there is no central element and the two halves
    // are 1 2 3 4 and 1 2 3 5 which are different
    vector<int> v3 = { 1, 2, 3, 4, 1, 2, 3, 5 };

    // Declaring fourth vector and making it equal to v3
    vector<int> v4 = v3;

    // Performing swap between two halves of vector v1
    if (v1.size() % 2 == 0)
        std::swap_ranges(v1.begin(), v1.begin() + (v1.size() / 2),
                        v1.begin() + v1.size() / 2);

    else
        std::swap_ranges(v1.begin(), v1.begin() + v1.size() / 2,
                        v1.begin() + (v1.size() / 2) + 1);

    if (v1 == v2) 
    {
        cout << "Yes";
    } else 
    {
        cout << "No";
    }

    // Now, Performing swap between two halves of vector v3
    if (v3.size() % 2 == 0)
        std::swap_ranges(v3.begin(), v3.begin() + (v3.size() / 2),
                        v3.begin() + v3.size() / 2);

    else
        std::swap_ranges(v3.begin(), v3.begin() + v3.size() / 2,
                        v3.begin() + (v3.size() / 2) + 1);

    cout << "\n";

    if (v3 == v4) 
    {
        cout << "Yes";
    } else 
    {
        cout << "No";
    }

    return 0;
}
```

输出:

```cpp
Yes
No

```

**代码说明:**这里，在这个代码中，我们已经声明了一个向量，然后将其分配给另一个向量，然后在第一个向量中，我们根据它是否包含奇数个元素来交换前半部分和后半部分的值。如果在交换值后，新的第一个向量与第二个向量(旧的第一个向量)相同，这意味着两个一半是相同的。

因此，在第一个向量 1 2 3 4 5 1 2 3 4 中，它在两个半部分中包含相同的元素，因此打印“是”，而在第二个向量 1 2 3 4 1 2 3 5 中，后半部分包含一个与前半部分不同的元素，即 4 代替 5，因此打印“否”。

**时间复杂度:**从第一个到最后一个的距离是线性的。

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。