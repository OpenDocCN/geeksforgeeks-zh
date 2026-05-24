# c++ 中 2D 向量排序|集合 1(按行和列)

> 原文:[https://www . geesforgeks . org/sorting-2d-vector-in-c-set-逐行逐列/](https://www.geeksforgeeks.org/sorting-2d-vector-in-c-set-1-by-row-and-column/)

**什么是 2D 矢量？**
一个 2D 向量就是向量的向量。这是一个借助向量实现的矩阵。

```cpp
// C++ code to demonstrate 2D vector
#include<iostream>
#include<vector> // for 2D vector
using namespace std;

int main()
{
    // Initializing 2D vector "vect" with
    // values
    vector< vector<int> > vect{{1, 2, 3},
                              {4, 5, 6},
                              {7, 8, 9}};

    // Displaying the 2D vector
    for (int i=0; i<vect.size(); i++)
    {
        for (int j=0; j<vect[i].size() ;j++)
            cout << vect[i][j] << " ";
        cout << endl;
    }

    return 0;
}
```

输出:

```cpp
1 2 3
4 5 6
7 8 9

```

**情况 1:对 2D 向量的特定行进行排序。**
这种排序方式将 2D 向量的选定行按升序排列。这是通过使用“sort()”并传递 1D 向量的迭代器作为参数来实现的。

```cpp
// C++ code to demonstrate sorting of a
// row of 2D vector
#include<iostream>
#include<vector> // for 2D vector
#include<algorithm> // for sort()
using namespace std;

int main()
{
    // Initializing 2D vector "vect" with
    // values
    vector< vector<int> > vect{{3, 5, 1},
                               {4, 8, 6},
                               {7, 2, 9}};
    // Number of rows;
    int m = vect.size();

    // Number of columns (Assuming all rows
    // are of same size).  We can have different
    // sizes though (like Java).
    int n = vect[0].size();

    // Displaying the 2D vector before sorting
    cout << "The Matrix before sorting 1st row is:\n";
    for (int i=0; i<m; i++)
    {
        for (int j=0; j<n ;j++)
           cout << vect[i][j] << " ";
        cout << endl;
    }

    // Use of "sort()" for sorting first row
    sort(vect[0].begin(), vect[0].end());

    // Displaying the 2D vector after sorting
    cout << "The Matrix after sorting 1st row is:\n";
    for (int i=0; i<m; i++)
    {
        for (int j=0; j<n ;j++)
            cout << vect[i][j] << " ";
        cout << endl;
    }

    return 0;
}
```

输出:

```cpp
The Matrix before sorting 1st row is:
3 5 1 
4 8 6 
7 2 9 
The Matrix after sorting 1st row is:
1 3 5 
4 8 6 
7 2 9 

```

**情况 2:根据特定的列对整个 2D 向量进行排序。**
在这种类型的排序中，2D 向量完全是根据选定的列进行排序的。例如，如果选择的列是第二列，则第二列中具有最小值的行成为第一行，第二列中具有第二最小值的行成为第二行，依此类推。

{3，5，1}，
{4，8，6}，
{7，2，9 }；

将这个矩阵按第二列排序后，我们得到

{7，2，9} //第二列
中值最小的行{3，5，1} //第二列
中值最小的行{4，8，6}

这是通过在“sort()”中传递第三个参数作为对用户定义的显式函数的调用来实现的。

```cpp
// C++ code to demonstrate sorting of a
// 2D vector on basis of a column
#include<iostream>
#include<vector> // for 2D vector
#include<algorithm> // for sort()
using namespace std;

// Driver function to sort the 2D vector
// on basis of a particular column
bool sortcol( const vector<int>& v1,
               const vector<int>& v2 ) {
 return v1[1] < v2[1];
}

int main()
{
    // Initializing 2D vector "vect" with
    // values
    vector< vector<int> > vect{{3, 5, 1},
                                {4, 8, 6},
                                {7, 2, 9}};

    // Number of rows;
    int m = vect.size();

    // Number of columns (Assuming all rows
    // are of same size).  We can have different
    // sizes though (like Java).
    int n = vect[0].size();

    // Displaying the 2D vector before sorting
    cout << "The Matrix before sorting is:\n";
    for (int i=0; i<m; i++)
    {
        for (int j=0; j<n ;j++)
            cout << vect[i][j] << " ";
        cout << endl;
    }                               

    // Use of "sort()" for sorting on basis
    // of 2nd column
    sort(vect.begin(), vect.end(),sortcol);

    // Displaying the 2D vector after sorting
    cout << "The Matrix after sorting is:\n";
    for (int i=0; i<m; i++)
    {
        for (int j=0; j<n ;j++)
            cout << vect[i][j] << " ";
        cout << endl;
    }
    return 0;
}
```

输出:

```cpp
The Matrix before sorting is:
3 5 1 
4 8 6 
7 2 9 
The Matrix after sorting is:
7 2 9 
3 5 1 
4 8 6 

```

[c++ 中 2D 向量排序|集合 2(按行和列降序排列)](https://www.geeksforgeeks.org/sorting-2d-vector-in-c-set-2-in-descending-order-by-row-and-column/)

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。