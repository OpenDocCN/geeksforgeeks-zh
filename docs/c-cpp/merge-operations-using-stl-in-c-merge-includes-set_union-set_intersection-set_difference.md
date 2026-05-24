# 在 C++ 中使用 STL 的合并操作| merge()，包括()，set_union()，set _ 交集()，set _ difference()，。，inplace_merge，

> 原文:[https://www . geesforgeks . org/merge-operations-using-STL-in-c-merge-includes-set _ union-set _ intersection-set _ difference/](https://www.geeksforgeeks.org/merge-operations-using-stl-in-c-merge-includes-set_union-set_intersection-set_difference/)

一些合并操作类是在头文件“算法”下用 C++ STL 提供的，它以一种简单的方式方便了几个合并操作。
下面提到其中一些。

1.  **合并(beg1，end1，beg2，end2，beg3)** :-此函数合并两个已排序的容器，并按排序顺序存储在新容器中(合并排序)。它需要 5 个参数，第一个容器的第一个和最后一个迭代器，第二个容器的第一个和最后一个迭代器，以及结果容器的第一个迭代器。
2.  **includes(beg1, end1, beg2, end2)** :- This function is used to check whether one sorted container elements are including other sorted container elements or not. Returns true if 1st container includes 2nd container else returns false.

    ```cpp
    // C++ code to demonstrate the working of 
    // merge() and include()
    #include<iostream>
    #include<algorithm> // merge operations
    #include<vector> // for vector
    using namespace std;
    int main()
    {
     // Initializing 1st vector
     vector<int> v1 = {1, 3, 4, 5, 20, 30};

     // Initializing 2nd vector
     vector<int> v2 = {1, 5, 6, 7, 25, 30};

     // Declaring resultant vector
     // for mergeing
     vector<int> v3(12);

     // Using merge() to merge vectors v1 and v2
     // and storing result in v3
     merge(v1.begin(), v1.end(), v2.begin(), 
                       v2.end(), v3.begin());

     // Displaying resultant container
     cout << "The new container after merging is :\n";
     for (int &x : v3) 
         cout << x << " ";
     cout << endl;

     // Initializing new vector
     vector<int> v4 = {1, 3, 4, 5, 6, 20, 25, 30};

     // Using include() to check if v4 contains v1
     includes(v4.begin(), v4.end(), v1.begin(), v1.end())?
            cout << "v4 includes v1":
            cout << "v4 does'nt include v1";

     return 0;    
    }
    ```

    输出

    ```cpp
    The new container after merging is :
    1 1 3 4 5 5 6 7 20 25 30 30 
    v4 includes v1

    ```

3.  **inplace_merge(beg1, beg2, end) :-** This function is used to sort two consecutively placed sorted ranges in a single container. It takes 3 arguments, iterator to beginning of 1st sorted range, iterator to beginning of 2nd sorted range, and iterator to last position.

    ```cpp
    // C++ code to demonstrate the working of 
    // inplace_merge()
    #include<iostream>
    #include<algorithm> // merge operations
    #include<vector> // for vector
    using namespace std;
    int main()
    {

     // Initializing 1st vector
     vector<int> v1 = {1, 3, 4, 5, 20, 30};

     // Initializing 2nd vector
     vector<int> v2 = {1, 5, 6, 7, 25, 30};

     // Declaring resultant vector
     // for inplace_merge()
     vector<int> v3(12);

     // using copy to copy both vectors into 
     // one container
     auto it = copy(v1.begin(), v1.end(), v3.begin());
     copy(v2.begin(), v2.end(), it);

     // Using inplace_merge() to sort the container
     inplace_merge(v3.begin(),it,v3.end());

     // Displaying resultant container
     cout << "The new container after inplace_merging is :\n";
     for (int &x : v3) 
         cout << x << " ";
     cout << endl;

     return 0;

    }
    ```

    输出:

    ```cpp
    The new container after inplace_merging is :
    1 1 3 4 5 5 6 7 20 25 30 30 

    ```

4.  **set_union(beg1，end1，beg2，end2，beg3)** :-该函数计算两个容器的集并集并存储在新容器中。它将迭代器返回到结果容器的最后一个元素。它需要 5 个参数，第一个容器的第一个和最后一个迭代器，第二个容器的第一个和最后一个迭代器，以及结果容器的第一个迭代器。应该对容器进行分类，并且有必要将新容器的大小调整到合适的大小。
5.  **set _ 交集(beg1，end1，beg2，end2，beg3)** :-该函数计算两个容器的集合交集，并存储在新容器中。它将迭代器返回到结果容器的最后一个元素。它需要 5 个参数，第一个容器的第一个和最后一个迭代器，第二个容器的第一个和最后一个迭代器，以及结果容器的第一个迭代器。应该对容器进行分类，并且有必要将新容器的大小调整到合适的大小。
    在排序范围内实现集合并和集合交的一种方法可以在这里[找到](https://www.geeksforgeeks.org/union-and-intersection-of-two-sorted-arrays-2/)

```cpp
// C++ code to demonstrate the working of 
// set_union() and set_intersection()
#include<iostream>
#include<algorithm> // for merge operations
#include<vector> // for vector
using namespace std;
int main()
{
 // Initializing 1st vector
 vector<int> v1 = {1, 3, 4, 5, 20, 30};

 // Initializing 2nd vector
 vector<int> v2 = {1, 5, 6, 7, 25, 30};

 // Declaring resultant vector
 // for union
 vector<int> v3(10);

 // Declaring resultant vector
 // for intersection
 vector<int> v4(10);

 // using set_union() to compute union  of 2 
 // containers v1 and v2 and store result in v3
 auto it = set_union(v1.begin(), v1.end(), v2.begin(), 
                              v2.end(), v3.begin());

 // using set_intersection() to compute intersection
 // of 2 containers v1 and v2 and store result in v4
 auto it1 = set_intersection(v1.begin(),v1.end(), 
               v2.begin(), v2.end(), v4.begin());

 // resizing new container
 v3.resize(it - v3.begin());

 // resizing new container
 v4.resize(it1 - v4.begin());

 // Displaying set union
 cout << "Union of two containers is : ";
 for (int &x : v3) 
     cout << x << " ";
 cout << endl;

 // Displaying set intersection
 cout << "Intersection of two containers is : ";
 for (int &x : v4) 
     cout << x << " ";
 cout << endl;

 return 0;    
}
```

输出:

```cpp
Union of two containers is : 1 3 4 5 6 7 20 25 30 
Intersection of two containers is : 1 5 30 

```

11.  **set_difference(beg1，end1，beg2，end2，beg3)** :-该函数计算两个容器的集差并存储在新容器中。它将迭代器返回到结果容器的最后一个元素。它需要 5 个参数，第一个容器的第一个和最后一个迭代器，第二个容器的第一个和最后一个迭代器，以及结果容器的第一个迭代器。应该对容器进行分类，并且有必要将新容器的大小调整到合适的大小。
12.  s**et_symmetric_difference(beg1, end1, beg2, end2, beg3)** :- This function computes the set symmetric difference of two containers and stores in new container .It returns the iterator to the last element of resultant container. It takes 5 arguments, first and last iterator of 1st container, first and last iterator of 2nd container and 1st iterator of resultant container . The containers should be sorted and it is necessary that new container is resized to suitable size.

    ```cpp
    // C++ code to demonstrate the working of 
    // set_difference() and set_symmetric_difference()
    #include<iostream>
    #include<algorithm> // for merge operations
    #include<vector> // for vector
    using namespace std;
    int main()
    {
     // Initializing 1st vector
     vector<int> v1 = {1, 3, 4, 5, 20, 30};

     // Initializing 2nd vector
     vector<int> v2 = {1, 5, 6, 7, 25, 30};

     // Declaring resultant vector
     // for difference
     vector<int> v3(10);

     // Declaring resultant vector
     // for symmetric_difference
     vector<int> v4(10);

     // using set_difference() to compute difference
     // of 2 containers v1 and v2.
     auto it = set_difference(v1.begin(), v1.end(),
                  v2.begin(), v2.end(), v3.begin());

     // using set_symmetric_difference() to compute 
     // symmetric_difference/ of 2 containers
     auto it1 = set_symmetric_difference(v1.begin(), 
           v1.end(), v2.begin(), v2.end(), v4.begin());

     // resizing new container
     v3.resize(it - v3.begin());

     // resizing new container
     v4.resize(it1 - v4.begin());

     // Displaying set difference
     cout << "Difference of two containers is : ";
     for (int &x : v3) 
         cout << x << " ";
     cout << endl;

     // Displaying set symmetric_difference
     cout << "symmetric_difference of two containers is : ";
     for (int &x : v4) 
         cout << x << " ";
     cout << endl;

     return 0;    
    }
    ```

    输出:

    ```cpp
    Difference of two containers is : 3 4 20 
    Symmetric difference of two containers is : 3 4 6 7 20 25 

    ```

本文由[曼吉特·辛格](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。