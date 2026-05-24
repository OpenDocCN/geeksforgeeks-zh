# 如何在 C++ 中将数据三元组存储在一个向量中？

> 原文:[https://www.geeksforgeeks.org/store-data-triplet-vector-c/](https://www.geeksforgeeks.org/store-data-triplet-vector-c/)

给定一个向量，我们如何在向量的一个单元中存储 3 个元素。

示例:

```cpp
Input : 2 5 10
        3 6 15
Output : (2, 5, 10)  // In first cell of vector
         (3, 6, 15)  // In second cell of vector

```

一种解决方案是创建一个**用户定义的类或结构**。我们创建一个有三个成员的结构，然后创建这个结构的向量。

```cpp
// C++ program to store data triplet in a vector
// using user defined structure.
#include<bits/stdc++.h>
using namespace std;

struct Test
{
   int x, y, z;
};

int main()
{
    // Creating a vector of Test
    vector<Test> myvec;

    // Inserting elements into vector. First
    // value is assigned to x, second to y
    // and third to z.
    myvec.push_back({2, 31, 102});
    myvec.push_back({5, 23, 114});
    myvec.push_back({9, 10, 158});

    int s = myvec.size();
    for (int i=0;i<s;i++)
    {
        // Accessing structure members using their
        // names.
        cout << myvec[i].x << ", " << myvec[i].y
             << ", " << myvec[i].z << endl;
    }
    return 0;
}
```

输出:

```cpp
2, 31, 102
5, 23, 114
9, 10, 158

```

另一种解决方案是在 C++ STL 中使用 **[对类](https://www.geeksforgeeks.org/pair-simple-containers-the-c-standard-template-library-stl/)** 。我们将第一个元素作为普通元素，第二个元素作为另一个元素对，因此同时存储 3 个元素。

```cpp
// C++ program to store data triplet in a vector
// using pair class
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // We make a pair with first element as normal
    // element and second element as another pair.
    // therefore 3 elements simultaneously.
    vector< pair<int, pair<int, int> > > myvec;

    // For inserting element in pair use
    // make_pair().
    myvec.push_back(make_pair(2, make_pair(31, 102)));
    myvec.push_back(make_pair(5, make_pair(23, 114)));
    myvec.push_back(make_pair(9, make_pair(10, 158)));

    int s = myvec.size();
    for (int i=0; i<s; i++)
    {
        // The elements can be directly accessed
        // according to first or second element
        // of the pair.
        cout << myvec[i].first << ", " << myvec[i].second.first
              << ", " << myvec[i].second.second << endl;
    }
    return 0;
} 
```

输出:

```cpp
2, 31, 102
5, 23, 114
9, 10, 158

```

本文由 **Jatin Goyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。