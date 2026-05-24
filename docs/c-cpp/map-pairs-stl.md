# STL 中成对的映射

> 原文:[https://www.geeksforgeeks.org/map-pairs-stl/](https://www.geeksforgeeks.org/map-pairs-stl/)

[STL](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)中的映射用于散列键值。我们通常将 map 用于标准数据类型。我们也可以用地图来配对。

例如，考虑一个简单的问题，给定一个矩阵和访问的职位，打印哪些职位没有被访问。

```cpp
// C++ program to demonstrate use of map
// for pairs
#include <bits/stdc++.h>
using namespace std;

map<pair<int, int>, int> vis;

// Print positions that are not marked
// as visited
void printPositions(int a[3][3])
{
    for (int i = 0; i < 3; i++)
        for (int j = 0; j < 3; j++)
            if (vis[{ i, j }] == 0)
                cout << "(" << i << ", " << j << ")"
                     << "\n";
}

int main()
{
    int mat[3][3] = { { 0, 1, 2 }, { 3, 4, 5 }, { 6, 7, 8 } };

    // Marking some positions as visited
    vis[{ 0, 0 }] = 1; // visit (0, 0)
    vis[{ 1, 0 }] = 1; // visit (1, 0)
    vis[{ 1, 1 }] = 1; // visit (1, 1)
    vis[{ 2, 2 }] = 1; // visit (2, 2)

    // print which positions in matrix are not visited by rat
    printPositions(mat);
    return 0;
}
```

输出:

```cpp
(0, 1)
(0, 2)
(1, 2)
(2, 0)
(2, 1)

```

本文由 **Abhishek Rajput** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。