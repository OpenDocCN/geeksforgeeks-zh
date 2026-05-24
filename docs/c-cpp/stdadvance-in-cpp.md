# STD::c++ 中的高级功能

> 原文:[https://www.geeksforgeeks.org/stdadvance-in-cpp/](https://www.geeksforgeeks.org/stdadvance-in-cpp/)

std::advance 使迭代器“it”前进 n 个元素位置。

**语法:**

```cpp
template 
    void advance (InputIterator& it, Distance n);

it : Iterator to be advanced
n : Number of element positions to advance.
This shall only be negative for random-access and bidirectional iterators.

Return type :
None.

```

**动机问题:**给出了一个向量容器。任务是打印替代元素。

**示例:**

```cpp
Input : 10 40 20 50 80 70
Output : 10 20 80

```

```cpp
// C++ program to illustrate
// using std::advance
#include <bits/stdc++.h>

// Driver code
int main()
{
    // Vector container
    std::vector<int> vec;

    // Initialising vector
    for (int i = 0; i < 10; i++)
        vec.push_back(i * 10);

    // Printing the vector elements
    for (int i = 0; i < 10; i++) {
        std::cout << vec[i] << " ";
    }

    std::cout << std::endl;

    // Declaring the vector iterator
    std::vector<int>::iterator it = vec.begin();

    // Printing alternate elements
    while (it < vec.end()) {
        std::cout << *it << " ";
        std::advance(it, 2);
    }
}
```

输出:

```cpp
0 10 20 30 40 50 60 70 80 90 
0 20 40 60 80

```

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。