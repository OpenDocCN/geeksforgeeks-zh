# 矢量 STLs 中的常见细微差别

> 原文:[https://www . geesforgeks . org/common-subtities-vector-stls/](https://www.geeksforgeeks.org/common-subtleties-vector-stls/)

先决条件–[矢量基础知识](http://geeksquiz.com/vector-sequence-containers-the-c-standard-template-library-stl-set-1/)

以下是一些重要的要点，可以在面试或重要的编码比赛中节省时间。

1.  **向量< int >向量(10) vs 向量< int >向量【10】**

    ```cpp
    // Creates a vector vect[] of size 10
    vector <int> vect(10) 

    // creates an array of vectors vect[] of size 
    // 10 where each vector has int members
    vector<int> vect[10]

    ```

2.  **resize()和 push_back():**
    在向量上使用 resize()函数后，如果在同一向量上使用 push_back()，则被推回的元素将被添加到调整大小的向量的末尾，而不是其中。

    ```cpp
    // A C++ program to demonstrate that push_back()
    // happens at the end of resized vector.
    #include<bits/stdc++.h>
    using namespace std;

    int main()
    {
        vector<int> vect;
        for (int i = 0; i < 5; i++)
            vect.push_back(i);

        // Resizing vector to size 10
        vect.resize(10);

        // Prints 0 1 2 3 4 0 0 0 0 0
        for (int i = 0; i < vect.size(); i++)
            cout << vect[i] << " ";
        cout << "\n";

        vect.push_back(50);

        // Prints 0 1 2 3 4 0 0 0 0 0 50
        for (int i = 0; i < vect.size(); i++)
            cout << vect[i] << " ";

        return 0;
    }
    ```

    ```cpp
    Output:
    0 1 2 3 4 0 0 0 0 0
    0 1 2 3 4 0 0 0 0 0 50
    ```

3.  **clear()函数**使向量有零个元素，即-无元素，不使元素全为 0。
4.  **Creating a two dimensional vector**

    ```cpp
    // This doesn't work
    vector<vector<int>> vect;

    // This works fine
    vector< vector <int> > vect; 
    ```

    这两个语句的区别在于，第一个语句在尖括号( > >)之间有一个空格。写的时候没有空格是不行的，因为>>是 C++ 中的一个运算符。

5.  **将向量传递给函数:**
    当向量被简单地传递给函数时，向量的副本就被创建了。在向量很大的情况下，这可能需要很多时间。

```cpp
// C++ program to demonstrate that when vectors
// are passed to functions without &, a copy is
// created.
#include<bits/stdc++.h>
using namespace std;

// The vect here is a copy of vect in main()
void func(vector<int> vect)
{
   vect.push_back(30);
}

int main()
{
    vector<int> vect;
    vect.push_back(10);
    vect.push_back(20);

    func(vect);

    // vect remains unchanged after function
    // call
    for (int i=0; i<vect.size(); i++)
       cout << vect[i] << " ";

    return 0;
}
```

输出:

```cpp
10 20
```

在我们实际上不需要向量副本的情况下，声明应该如下进行:

```cpp
// It is recommended to pass vectors by reference
// wherever possible.
int func(vector<int>& vect)
{

}

```

本文由**苏皮亚·施赖瓦塔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上述话题的信息，请写评论