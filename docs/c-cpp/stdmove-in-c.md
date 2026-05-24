# std::在 C++ 中移动

> 原文:[https://www.geeksforgeeks.org/stdmove-in-c/](https://www.geeksforgeeks.org/stdmove-in-c/)

**std :: move**
将范围[第一个，最后一个]中的元素移动到从结果开始的范围。
将【第一个，最后一个】中元素的值转移到结果指向的元素。调用后，范围[第一个，最后一个]中的元素保持未指定但有效的状态。
**模板:**

```cpp
OutputIterator move (InputIterator first, InputIterator last, OutputIterator result);

Parameters :

first, last
Input iterators to the initial and final positions in a sequence
to be moved. The range used is [first,last], which contains all
the elements between first and last, including the element pointed
by first but not the element pointed by last.

result
Output iterator to the initial position in the destination sequence.
This shall not point to any element in the range [first,last].

Return type :
An iterator to the end of the destination range where elements have been moved.

```

示例:

```cpp
Input :
vec1 contains : 1 2 3 4 5
vec2 contains : 7 7 7 7 7
Output :
arr2 contains : 7 1 2 3 4
/*First 4 elements of vector vec1 moved to vec2 starting second position*/

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

    // std :: move function
    // move first 4 element from vec1 to starting position of vec2
    std :: move (vec1.begin(), vec1.begin() + 4, vec2.begin() + 1);

    // Print elements
    std :: cout << "Vector2 contains after std::move function:";
    for(unsigned int i = 0; i < vec2.size(); i++)
        std :: cout << " " << vec2[i];
    std :: cout << "\n";

    return 0;
}
```

输出:

```cpp
Vector1 contains : 1 2 3 4 5
Vector2 contains : 7 7 7 7 7

Vector2 contains after std::move function: 7 1 2 3 4

```

本文由 **[沙钦·毕斯特](https://www.linkedin.com/in/sachin-bisht-984b5013a/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。