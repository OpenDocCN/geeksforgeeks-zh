# 在 C++ STL 中旋转

> 原文:[https://www.geeksforgeeks.org/rotate-in-cpp-stl/](https://www.geeksforgeeks.org/rotate-in-cpp-stl/)

该功能在标题<algorithm>中定义。它旋转范围[第一个，最后一个]中元素的顺序，以这种方式，中间指向的元素成为新的第一个元素。
**功能模板:**</algorithm>

> **void rotate(forwarding Iterator first，ForwardIterator middle，forwarding Iterator last)**
> **first，last:**forwarding Iterators 到要旋转的序列的初始和最终位置**旋转**
> **middle:**forwarding Iterators 指向移动到范围中第一个位置的[first，last]范围内的元素。

**旋转类型**

1.  **向左旋转:**要向左旋转，我们需要添加矢量索引。例如，你必须向左旋转向量 3 次。向量的第三个索引成为第一个元素。 **vec.begin() + 3** 将向左旋转矢量 3 次。
2.  **Right Rotation :** To rotate right, we need to subtract the vector index. For example, you have to rotate vector right 3 times. The 3th last index of vector becomes first element. **vec.begin()+vec.size()-3** will rotate vector 3 times right.

    示例:

    > 输入:1 2 3 4 5 6 7 8 9
    > 输出:
    > 旧向量:1 2 3 4 5 6 7 8 9
    > 新向量:4 5 6 7 8 9 1 2 3 //在第 3 个位置旋转，起始索引为 0。
    > 
    > 输入:8 2 4 6 11 0 15 8
    > 输出:
    > 旧向量:8 2 4 6 11 0 15 8
    > 新向量:0 15 8 2 4 6 11//在第 5 个位置旋转，起始索引为 0。

    ```cpp
    // CPP program to rotate vector
    // using std::rotate algorithm

    #include<bits/stdc++.h>

    int main () {
        std::vector<int> vec1{1,2,3,4,5,6,7,8,9};

        // Print old vector
        std::cout << "Old vector :";
        for(int i=0; i < vec1.size(); i++)
            std::cout << " " << vec1[i];
        std::cout << "\n";
        // Rotate vector left 3 times.
        int rotL=3;

        // std::rotate function
        std::rotate(vec1.begin(), vec1.begin()+rotL, vec1.end());

        // Print new vector
        std::cout << "New vector after left rotation :";
        for (int i=0; i < vec1.size(); i++)
            std::cout<<" "<<vec1[i];
        std::cout << "\n\n";

        std::vector <int> vec2{1,2,3,4,5,6,7,8,9};

        // Print old vector
        std::cout << "Old vector :";
        for (int i=0; i < vec2.size(); i++)
            std::cout << " " << vec2[i];
        std::cout << "\n";

        // Rotate vector right 4 times.
        int rotR = 4;

        // std::rotate function
        std::rotate(vec2.begin(), vec2.begin()+vec2.size()-rotR, vec2.end());

        // Print new vector
        std::cout << "New vector after right rotation :";
        for (int i=0; i < vec2.size(); i++)
            std::cout << " " << vec2[i];
        std::cout << "\n";

    return 0;
    }
    ```

    输出:

    ```cpp
    Old vector : 1 2 3 4 5 6 7 8 9
    New vector after left rotation : 4 5 6 7 8 9 1 2 3

    Old vector : 1 2 3 4 5 6 7 8 9
    New vector after right rotation: 6 7 8 9 1 2 3 4 5

    ```

    时间复杂度:θ(n)，其中 n 是给定范围内的元素个数。

    本文由**沙钦·毕斯特**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。