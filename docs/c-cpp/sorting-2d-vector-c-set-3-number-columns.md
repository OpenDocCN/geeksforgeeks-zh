# c++ 中 2D 向量排序|集合 3(按列数)

> 原文:[https://www . geesforgeks . org/sorting-2d-vector-c-set-3-number-columns/](https://www.geeksforgeeks.org/sorting-2d-vector-c-set-3-number-columns/)

我们在下面的集合 1 和集合 2 中讨论了排序 2D 向量的一些情况。

[c++ 中 2D 向量排序|集合 1(按行和列)](https://www.geeksforgeeks.org/sorting-2d-vector-in-c-set-1-by-row-and-column/)
[c++ 中 2D 向量排序|集合 2(按行和列降序)](https://www.geeksforgeeks.org/sorting-2d-vector-in-c-set-2-in-descending-order-by-row-and-column/)

本文将讨论更多的案例

正如在这组文章中发表的一篇文章中提到的，2D 向量也可以有不同列数的行。此属性不同于 2D 数组，后者中所有行的列数都相同。

```cpp
// C++ code to demonstrate 2D Vector
// with different no. of columns
#include<iostream>
#include<vector> // for 2D vector
using namespace std;
int main()
{
    // Initializing 2D vector "vect" with
    // values
    vector< vector<int> > vect{{1, 2},
                               {3, 4, 5},
                               {6}};

    // Displaying the 2D vector
    for (int i=0; i<vect.size(); i++)
    {
        //loop till the size of particular
        //row
        for (int j=0; j<vect[i].size() ;j++)
            cout << vect[i][j] << " ";
        cout << endl;
    }

    return 0;

}
```

输出:

```cpp
1 2
3 4 5
6

```

**情况 5:根据行中的列数按升序对 2D 向量进行排序。**

在这种类型的排序中，2D 向量是根据列数以升序排序的。这是通过在“sort()”中传递第三个参数作为对用户定义的显式函数的调用来实现的。

```cpp
// C++ code to demonstrate sorting of
// 2D vector on basis of no. of columns
// in ascending order
#include<iostream>
#include<vector> // for 2D vector
#include<algorithm> // for sort()
using namespace std;

// Driver function to sort the 2D vector
// on basis of a no. of columns in 
// ascending order
bool sizecom(const vector<int>& v1, const vector<int>& v2)
{
    return v1.size() < v2.size();
}

int main()
{
    // Initializing 2D vector "vect" with
    // values
    vector< vector<int> > vect{{1, 2},
                               {3, 4, 5},
                               {6}};

    // Displaying the 2D vector before sorting
    cout << "The Matrix before sorting is:\n";
    for (int i=0; i<vect.size(); i++)
    {
        //loop till the size of particular
        //row
        for (int j=0; j<vect[i].size() ;j++)
            cout << vect[i][j] << " ";
        cout << endl;
    }

    //Use of "sort()" for sorting on
    //basis of no. of columns in
    //ascending order.
    sort(vect.begin(), vect.end(), sizecom);

    // Displaying the 2D vector after sorting
    cout << "The Matrix after sorting is:\n";
    for (int i=0; i<vect.size(); i++)
    {
        //loop till the size of particular
        //row
        for (int j=0; j<vect[i].size() ;j++)
            cout << vect[i][j] << " ";
        cout << endl;
    }

    return 0;

}
```

输出:

```cpp
The Matrix before sorting is:
1 2 
3 4 5 
6 
The Matrix after sorting is:
6 
1 2 
3 4 5 

```

**案例六:根据行中列数降序排列 2D 向量。**

在这种类型的排序中，2D 向量是根据列数以降序排序的。这是通过在“sort()”中传递第三个参数作为对用户定义的显式函数的调用来实现的。

```cpp
// C++ code to demonstrate sorting of
// 2D vector on basis of no. of columns
// in descending order
#include<iostream>
#include<vector> // for 2D vector
#include<algorithm> // for sort()
using namespace std;

// Driver function to sort the 2D vector
// on basis of a no. of columns in 
// descending order
bool sizecom(const vector<int>& v1, const vector<int>& v2)
{
    return v1.size() > v2.size();
}

int main()
{
    // Initializing 2D vector "vect" with
    // values
    vector< vector<int> > vect{{1, 2},
                      {3, 4, 5},
                  {6}};

    // Displaying the 2D vector before sorting
    cout << "The Matrix before sorting is:\n";
    for (int i=0; i<vect.size(); i++)
    {
        //loop till the size of particular
        //row
        for (int j=0; j<vect[i].size() ;j++)
            cout << vect[i][j] << " ";
        cout << endl;
    }

    //Use of "sort()" for sorting on
    //basis of no. of columns in
    //descending order.
    sort(vect.begin(), vect.end(), sizecom);

    // Displaying the 2D vector after sorting
    cout << "The Matrix after sorting is:\n";
    for (int i=0; i<vect.size(); i++)
    {
        //loop till the size of particular
        //row
        for (int j=0; j<vect[i].size() ;j++)
            cout << vect[i][j] << " ";
        cout << endl;
    }

    return 0;

}
```

输出:

```cpp
The Matrix before sorting is:
1 2 
3 4 5 
6 
The Matrix after sorting is:
3 4 5 
1 2 
6 

```

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。