# 向量的 std::remove 和 vector::erase 之间的差异

> 原文:[https://www . geeksforgeeks . org/stdremove-和-vectororase-for-vector 之间的差异/](https://www.geeksforgeeks.org/difference-between-stdremove-and-vectorerase-for-vectors/)

**[std::remove](https://www.geeksforgeeks.org/stdremove-stdremove_if-c/) :** 它实际上并没有从容器中删除元素，而是在已删除元素的基础上向前分流未删除的元素。

**向量::擦除:**从向量中移除单个元素(位置)或一系列元素([第一个，最后一个])。

**标准::移除 vs 矢量::擦除**

1.  通过使用擦除，std::vector 中的所有元素都将移位 1，从而导致大量副本；std::remove 只执行“逻辑”删除，并通过移动对象来保持向量不变。
2.  如果需要从向量中移除多个元素，std::remove 会将每个未移除的元素仅复制一次到其最终位置，而 vector::erase 方法会将所有元素从该位置移动到末尾多次。
3.  For Example, Consider removing all elements < 5 in following vector.

    ```cpp
    std::vector v { 1, 2, 3, 4, 5 };
    // remove all elements < 5

    ```

    使用擦除，如果你一个接一个地删除向量元素，你会删除 1，导致剩余元素的副本移位(4)。然后移除 2，将所有剩余的元素移动 1(3)…如果你看到模式，这是一个 **O(N^2)算法**。

    在 **std::remove** 的情况下，算法保持一个头，并在容器上迭代。对于前 4 个元素，将移动头部并测试元素，但不复制任何元素。仅对于第五个元素，对象将从最后一个位置复制到第一个位置，算法将完成一次复制，并将迭代器返回到第二个位置。这是一个 O(N)算法。后面的 **std::vector::erase** 会破坏所有剩余元素并调整容器大小。

4.  因此，erase()是您可以对容器中的元素执行的操作，remove()是您可以对某个范围执行的操作，因为它会重新排列该范围，但不会擦除该范围内的任何内容..

```cpp
// CPP program to illustrate
// difference b/w std::remove
// and std::vector::erase algorithm
#include <bits/stdc++.h>

int main()
{
    std::vector<int> vec{ 10, 20, 30, 30, 20, 10, 10, 20 };
    std::vector<int> ve{ 10, 20, 30, 30, 20, 10, 10, 20 };

    // Print original vector
    std::cout << "Original vector :";
    for (int i = 0; i < vec.size(); i++)
        std::cout << " " << vec[i];
    std::cout << "\n";

    // Iterator that store the position of last element
    std::vector<int>::iterator pend;

    // std :: remove function call
    pend = std::remove(vec.begin(), vec.end(), 20);

    // Print the vector after std :: remove
    std::cout << "Range contains:";
    for (std::vector<int>::iterator p = vec.begin(); p != pend; ++ p)
        std::cout << ' ' << *p; std::cout << '\n';

            // Print original vector
            std::cout << "Original Vector :";
    for (int i = 0; i < ve.size(); i++)
        std::cout << " " << ve[i];
    std::cout << "\n";

    // std :: vector :: erase function call
    // erase the first 3 elements of vector vector
    ve.erase(ve.begin(), ve.begin() + 3);

    // Print the vector
    std::cout << "Vector contains :";
    for (int i = 0; i < ve.size(); i++)
        std::cout << " " << ve[i];
    std::cout << "\n";

    return 0;
}
```

输出:

```cpp
Original vector : 10 20 30 30 20 10 10 20
Range contains: 10 30 30 10 10

Original Vector : 10 20 30 30 20 10 10 20
Vector contains : 30 20 10 10 20

```

**参考:** [叠加溢出](https://stackoverflow.com/questions/19296958/difference-between-stdremove-and-erase-for-vector)

本文由 **[沙钦·毕斯特](https://www.linkedin.com/in/sachin-bisht-984b5013a/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。