# STD::c++ STL 中的分区

> 原文:[https://www.geeksforgeeks.org/stdpartition-in-c-stl/](https://www.geeksforgeeks.org/stdpartition-in-c-stl/)

C++ 的 STL 算法库中有一个类，它允许我们使用某些内置函数轻松划分算法。划分是指根据给定的条件划分容器元素的行为。
**分区作战** **:**
**1。分区(beg，end，condition)** :-该函数用于根据其参数中提到的条件对元素进行**分区。
**2。is_partitioned(beg，end，condition)** :-如果容器已分区**则此函数返回布尔值 **true，否则返回 false。**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of
// partition() and is_partitioned()
#include<iostream>
#include<algorithm> // for partition algorithm
#include<vector> // for vector
using namespace std;
int main()
{
    // Initializing vector
    vector<int> vect = { 2, 1, 5, 6, 8, 7 };

    // Checking if vector is partitioned
    // using is_partitioned()
    is_partitioned(vect.begin(), vect.end(), [](int x)
    {
        return x%2==0;

    })?

    cout << "Vector is partitioned":
    cout << "Vector is not partitioned";
    cout << endl;

    // partitioning vector using partition()
    partition(vect.begin(), vect.end(), [](int x)
    {
        return x%2==0;

    });

    // Checking if vector is partitioned
    // using is_partitioned()
    is_partitioned(vect.begin(), vect.end(), [](int x)
    {
        return x%2==0;

    })?

    cout << "Now, vector is partitioned after partition operation":
    cout << "Vector is still not partitioned after partition operation";
    cout << endl;

    // Displaying partitioned Vector
    cout << "The partitioned vector is : ";
    for (int &x : vect) cout << x << " ";

    return 0;

}
```

**输出:**

```cpp
Vector is not partitioned
Now, vector is partitioned after partition operation
The partitioned vector is : 2 8 6 5 1 7
```

在上面的代码中，分区函数根据元素是偶数还是奇数对向量进行分区，偶数元素与奇数元素的分区没有特定的顺序。
**3。stable_partition(beg，end，condition)** :-该函数用于在**中的参数中提到的条件**的基础上**对元素**进行**分区，从而保持元素的相对顺序。**。
**4。partition_point(beg，end，condition)** :-该函数**返回一个迭代器，指向条件不成立的容器的分区点**，即分区范围【beg，end】中的第一个元素。应该已经对容器进行了分区，该函数才能工作。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of
// stable_partition() and partition_point()
#include<iostream>
#include<algorithm> // for partition algorithm
#include<vector> // for vector
using namespace std;
int main()
{
    // Initializing vector
    vector<int> vect = { 2, 1, 5, 6, 8, 7 };

    // partitioning vector using stable_partition()
    // in sorted order
    stable_partition(vect.begin(), vect.end(), [](int x)
    {
        return x%2 == 0;       
    });

    // Displaying partitioned Vector
    cout << "The partitioned vector is : ";
    for (int &x : vect) cout << x << " ";
    cout << endl;

    // Declaring iterator
    vector<int>::iterator it1;

    // using partition_point() to get ending position of partition
    auto it = partition_point(vect.begin(), vect.end(), [](int x)
    {
        return x%2==0;
    });

    // Displaying partitioned Vector
    cout << "The vector elements returning true for condition are : ";
    for ( it1= vect.begin(); it1!=it; it1++)
    cout << *it1 << " ";
    cout << endl;

    return 0;

}
```

**输出:**

```cpp
The partitioned vector is : 2 6 8 1 5 7 
The vector elements returning true for condition are : 2 6 8
```

在上面的代码中，偶数和奇数元素被分区并以递增的顺序(排序)排列。但并不总是以递增的顺序，这里的元素(偶数和奇数)以递增的顺序出现，分割后的结果也是如此。如果在 stable_partition()之后 vect 应该是{ 2，1，7，8，6，5 }，那么它应该是{ 2，8，6，1，7，5 }。外观的顺序保持不变。
**5。partition_copy(beg，end，beg1，beg2，condition)** :-此函数**将分区元素**复制到其参数中提到的不同容器中。需要 5 个参数。**容器的开始和结束位置，必须复制元素的新容器的开始位置(条件为 true 的元素)，必须复制其他元素的新容器的开始位置(条件为 false 的元素)和条件**。**调整**新容器的尺寸**是该功能所必需的**。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of
// partition_copy()
#include<iostream>
#include<algorithm> // for partition algorithm
#include<vector> // for vector
using namespace std;
int main()
{
    // Initializing vector
    vector<int> vect = { 2, 1, 5, 6, 8, 7 };

    // Declaring vector1
    vector<int> vect1;

    // Declaring vector1
    vector<int> vect2;

    // Resizing vectors to suitable size using count_if() and resize()
    int n = count_if (vect.begin(), vect.end(), [](int x)
    {
        return x%2==0;

    } );
    vect1.resize(n);
    vect2.resize(vect.size()-n);

    // Using partition_copy() to copy partitions
    partition_copy(vect.begin(), vect.end(), vect1.begin(),
                                     vect2.begin(), [](int x)
    {
        return x%2==0;
    });

    // Displaying partitioned Vector
    cout << "The elements that return true for condition are : ";
    for (int &x : vect1)
            cout << x << " ";
    cout << endl;

    // Displaying partitioned Vector
    cout << "The elements that return false for condition are : ";
    for (int &x : vect2)
            cout << x << " ";
    cout << endl;

    return 0;   
}
```

**输出:**

```cpp
The elements that return true for condition are : 2 6 8 
The elements that return false for condition are : 1 5 7
```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。