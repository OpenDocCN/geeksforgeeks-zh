# STD::move _ back in c++

> 原文:[https://www.geeksforgeeks.org/stdmove_backward-in-c/](https://www.geeksforgeeks.org/stdmove_backward-in-c/)

将范围[第一个，最后一个]中的元素从末尾移动到结果处结束的范围。
该函数从将*(最后一个-1)移动到*(结果-1)开始，然后向后跟随这些元素之前的元素，直到到达第一个(并包括它)。
**模板:**

```cpp
BidirectionalIterator2 move_backward (BidirectionalIterator1 first,
                                      BidirectionalIterator1 last,
                                      BidirectionalIterator2 result);

result
Bidirectional iterator to the past-the-end position in the destination sequence.
This shall not point to any element in the range [first,last].

Return Type :
An iterator to the first element of the destination sequence where elements
have been moved.

```

示例:

```cpp
Input :
vec1 contains : 3 4 5 7 8
vec2 contains : 8 9 6 2 4 7
Output :
arr2 contains : 8 9 6 5 7 8
/*3 elements from 3rd position of vector vec1 moved to starting 4th position of vec2*/

```

```cpp
// CPP program to illustrate
// std::move and std::move_backward
// STL library functions
#include<bits/stdc++.h>

// Driver code
int main()
{
    std :: vector <int> vec1 {1, 2, 3, 4, 5};
    std :: vector <int> vec2 {7, 7, 7, 7, 7};

    // Print elements
    std :: cout << "Vector1 contains :";
    for(int i = 0; i < vec1.size(); i++)
        std :: cout << " " << vec1[i];
    std :: cout << "\n";

    // Print elements
    std :: cout << "Vector2 contains :";
    for(unsigned int i = 0; i < vec2.size(); i++)
        std :: cout << " " << vec2[i];
    std :: cout << "\n\n";

    // std :: move_backward function
    std :: move_backward (vec2.begin(), vec2.begin() + 3, vec1.begin() + 3);

    // Print elements
    std :: cout << "Vector1 contains after std::move_backward function:";
    for(unsigned int i = 0; i < vec1.size(); i++)
        std :: cout << " " << vec1[i];
    std :: cout << "\n";

    return 0;
}
```

输出:

```cpp
Vector1 contains : 1 2 3 4 5
Vector2 contains : 7 7 7 7 7

Vector1 contains after std::move_backward function: 7 7 7 4 5

```

本文由 **[沙钦·毕斯特](https://www.linkedin.com/in/sachin-bisht-984b5013a/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。