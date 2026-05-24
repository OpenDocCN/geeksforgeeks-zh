# c++ 中的转发列表|集合 2(操纵函数)

> 原文:[https://www . geesforgeks . org/forward-list-c-set-2-operating-functions/](https://www.geeksforgeeks.org/forward-list-c-set-2-manipulating-functions/)

[c++ 中的转发列表|集 1(简介和重要功能)](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/)

本文将讨论更多的函数

除了插入和删除之外，可以在转发列表中使用的一些操作如下:

**1。[合并()](https://www.geeksforgeeks.org/forward_list-merge-in-c-stl/)** :-此功能用于合并一个转发列表和另一个转发列表。如果两个列表都被排序，那么返回的结果列表也被排序。

**2。[运算符“=”](https://www.geeksforgeeks.org/forward_listoperator-c-stl/)**:-该运算符将一个转发列表复制到另一个列表中。这种情况下的复制是深度复制。

```cpp
// C++ code to demonstrate the working of 
// merge() and operator=
#include<iostream>
#include<forward_list> 
using namespace std;

int main()
{     
     // Initializing 1st forward list
     forward_list<int> flist1 = {1, 2, 3};

     // Declaring 2nd forward list
     forward_list<int> flist2; 

     // Creating deep copy using "="
     flist2 = flist1;

     // Displaying flist2
     cout << "The contents of 2nd forward list"
             " after copy are : ";
     for (int &x : flist2) 
         cout << x << " ";
     cout << endl;

     // Using merge() to merge both list in 1
     flist1.merge(flist2);

     // Displaying merged forward list
     // Prints sorted list
     cout << "The contents of forward list "
             "after merge are : ";
     for (int &x : flist1) 
        cout << x << " ";
     cout << endl;

     return 0;    
}
```

输出:

```cpp
The contents of 2nd forward list after copy are : 1 2 3 
The contents of forward list after merge are : 1 1 2 2 3 3 

```

**3。[排序()](https://www.geeksforgeeks.org/stdforward_listsort-c-stl/)** :-该功能用于对转发列表进行排序。

**4。 [unique()](https://www.geeksforgeeks.org/forward_listunique-in-c-stl/)** :-该函数删除一个数字的多次出现，并返回一个包含唯一元素的正向列表。应该对转发列表进行排序，以便成功执行此功能。

```cpp
// C++ code to demonstrate the working of
// sort() and unique()
#include<iostream>
#include<forward_list> // for sort() and unique()
using namespace std;

int main()
{
     // Initializing 1st forward list
     forward_list<int> flist1 = {1, 2, 3, 2, 3, 3, 1};

     // Sorting the forward list using sort()
     flist1.sort();

     // Displaying sorted forward list
     cout << "The contents of forward list after "
             "sorting are : ";
     for (int &x : flist1)
         cout << x << " ";
     cout << endl;

     // Use of unique() to remove repeated occurrences
     flist1.unique();

     // Displaying forward list after using unique()
     cout << "The contents of forward list after "
             "unique operation are : ";
     for (int &x : flist1)
         cout << x << " ";
     cout << endl;

     return 0;
}
```

输出:

```cpp
The contents of forward list after sorting are : 1 1 2 2 3 3 3 
The contents of forward list after unique operation are : 1 2 3 

```

**5。[反向()](https://www.geeksforgeeks.org/forward_listreverse-in-c-stl/)** :-此功能用于反向正向列表。

**6。[交换()](https://www.geeksforgeeks.org/forward_listswap-c-stl/)** :-此功能将一个转发列表的内容与另一个进行交换。

```cpp
// C++ code to demonstrate the working of
// reverse() and swap()
#include<iostream>
#include<forward_list> // for reverse() and swap()
using namespace std;
int main()
{
     // Initializing 1st forward list
     forward_list<int> flist1 = {1, 2, 3,};

     // Initializing 2nd forward list
     forward_list<int> flist2 = {4, 5, 6};

     // Using reverse() to reverse 1st forward list
     flist1.reverse();

     // Displaying reversed forward list
     cout << "The contents of forward list after"
             " reversing are : ";
     for (int &x : flist1)
         cout << x << " ";
     cout << endl << endl;

     // Displaying forward list before swapping
     cout << "The contents of 1st forward list "
             "before swapping are : ";
     for (int &x : flist1)
         cout << x << " ";
     cout << endl;
     cout << "The contents of 2nd forward list "
             "before swapping are : ";
     for (int &x : flist2)
         cout << x << " ";
     cout << endl;

     // Use of swap() to swap the list
     flist1.swap(flist2);

     // Displaying forward list after swapping
     cout << "The contents of 1st forward list "
             "after swapping are : ";
     for (int &x : flist1)
         cout << x << " ";
     cout << endl;

     cout << "The contents of 2nd forward list "
             "after swapping are : ";
     for (int &x : flist2)
         cout << x << " ";
     cout << endl;

     return 0;
}
```

输出:

```cpp
The contents of forward list after reversing are : 3 2 1 

The contents of 1st forward list before swapping are : 3 2 1 
The contents of 2nd forward list before swapping are : 4 5 6 
The contents of 1st forward list after swapping are : 4 5 6 
The contents of 2nd forward list after swapping are : 3 2 1 

```

**7。[清除()](https://www.geeksforgeeks.org/forward_listclear-forward_listerase_after-c-stl/)** :-该功能清除转发列表的内容。执行此功能后，转发列表变为空。

**8。[空()](https://www.geeksforgeeks.org/forward_listfront-forward_listempty-c-stl/)** :-如果列表为空，该函数返回真，否则返回假。

```cpp
// C++ code to demonstrate the working of 
// clear() and empty()
#include<iostream>
#include<forward_list> // for clear() and empty()
using namespace std;
int main()
{     
     // Initializing  forward list
     forward_list<int> flist1 = {1, 2, 3,};

     // Displaying forward list before clearing
     cout << "The contents of forward list  are : ";
     for (int &x : flist1) 
         cout << x << " ";
     cout << endl;

     // Using clear() to clear the forward list 
     flist1.clear();

     // Displaying list after clear() performed
     cout << "The contents of forward list after "
          << "clearing are : ";
     for (int &x : flist1) 
         cout << x << " ";
     cout << endl;

     // Checking if list is empty
     flist1.empty() ? cout << "Forward list is empty" : 
                      cout << "Forward list is not empty";

     return 0;    
}
```

输出:

```cpp
The contents of forward list  are : 1 2 3 
The contents of forward list after clearing are : 
Forward list is empty

```

**[近期文章转发 _ 上榜](https://www.geeksforgeeks.org/tag/cpp-forward-list/)**

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。