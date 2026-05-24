# c++ 中的列表|集合 2(一些有用的函数)

> 原文:[https://www . geesforgeks . org/list-in-c-set-2-某些有用的函数/](https://www.geeksforgeeks.org/list-in-c-set-2-some-useful-functions/)

我们在下面的文章中讨论了 List 及其一些功能:

[列表:序列容器](https://www.geeksforgeeks.org/list-cpp-stl/)

本文将讨论一些更有用的函数

**1。定位(位置，值)** :-该功能用于**在指定的**位置**插入**元素。

**2。炮台 _ 回(值)** :-该功能在列表的末尾添加**值。它与 push_back()的不同之处在于，它直接在位置创建元素，而 push_back()首先创建一个临时副本并从那里复制。在大多数情况下，retain _ back()在实现上比 push_back()更快。**

**3。炮台 _ 正面** :-该功能在列表的开始处增加**值。它与 push_front()的不同之处在于，它直接在位置创建元素，而 push_front()首先创建一个临时副本并从那里复制。在大多数情况下，push_front()在实现上比 push _ front()更快。**

```cpp
// C++ code to demonstrate the working of 
// emplace(), emplace_front() and emplace_back()
#include<iostream>
#include<list> // for list functions
using namespace std;
int main()
{
    // Declaring a list
    list<int> gqlist;

    // Initialising list iterator
    list<int>::iterator it= gqlist.begin();

    // Entering list element using emplace_back()
    for (int i=1; i<=5; i++)
    gqlist.emplace_back(i);

    // Displaying list elements 
    cout << "List after emplace_back operation is : ";
    for (int &x : gqlist) cout << x << " ";
    cout << endl;

    // Entering list element using emplace_front()
    for (int i=10; i<=50; i+=10)
    gqlist.emplace_front(i);

    // Displaying list elements 
    cout << "List after emplace_front operation is : ";
    for (int &x : gqlist) cout << x << " ";
    cout << endl;

    // using advance() to advance iterator position
    advance(it,2);

     // inserting element at 2nd position using emplace()
    gqlist.emplace(it,100);

     // Displaying list elements 
    cout << "List after emplace operation is : ";
    for (int &x : gqlist) cout << x << " ";
    cout << endl;

    return 0;

}
```

输出:

```cpp
List after emplace_back operation is : 1 2 3 4 5 
List after emplace_front operation is : 50 40 30 20 10 1 2 3 4 5 
List after emplace operation is : 50 100 40 30 20 10 1 2 3 4 5 

```

**4。合并(列表 2)** :-该功能用于**合并列表 2 和列表 1** 。如果两个列表都是按排序顺序排列的，那么结果列表也是按排序的。

**5。remove_if(条件)** :-该功能**根据其参数中给出的条件**从列表中删除元素。

```cpp
// C++ code to demonstrate the working of 
// merge() and remove_if()
#include<iostream>
#include<list> // for list functions
using namespace std;
int main()
{
    // Initializing list1
    list<int> gqlist1 = {1, 2, 3};

    // Initializing list2
    list<int> gqlist2 = {2, 4, 6};

    // using merge() to merge list1 with list2
    gqlist1.merge(gqlist2);

    // Displaying list elements 
    cout << "list1 after merge operation is : ";
    for (int &x : gqlist1) cout << x << " ";
    cout << endl;

    // using remove_if() to remove odd elements
    // removes 1 and 3
    gqlist1.remove_if([](int x){return x%2!=0;});

    // Displaying list elements 
    cout << "list1 after remove_if operation is : ";
    for (int &x : gqlist1) cout << x << " ";
    cout << endl;

    return 0;

}
```

输出:

```cpp
list1 after merge operation is : 1 2 2 3 4 6 
list1 after remove_if operation is : 2 2 4 6 

```

**6。unique()** :-该功能用于**删除重复出现的**号。列表必须经过**排序**才能执行该功能。

**7。拼接(位置，列表 2)** :-该功能用于将元素从一个列表转移到另一个列表。

```cpp
// C++ code to demonstrate the working of 
// unique() and splice()
#include<iostream>
#include<list> // for list functions
using namespace std;
int main()
{
    // Initializing list1
    list<int> gqlist1 = {1, 1, 1, 2, 2, 3, 3, 4};

    // Initializing list2
    list<int> gqlist2 = {2, 4, 6};

    // Initializing list1 iterator
    list<int>::iterator it = gqlist1.begin();

    // using advance() to increment iterator position
    advance(it, 3);

    // Displaying list elements 
    cout << "list1 before unique operation is : ";
    for (int &x : gqlist1) cout << x << " ";
    cout << endl;

    // using unique() to remove repeating elements
    gqlist1.unique();

    // Displaying list elements 
    cout << "list1 after unique operation is : ";
    for (int &x : gqlist1) cout << x << " ";
    cout << endl << endl;

    // using splice() to splice list2 in list1 at position it
    // inserts list2 after 2nd position
    gqlist1.splice(it, gqlist2);

    // Displaying list elements 
    cout << "list1 after splice operation is : ";
    for (int &x : gqlist1) cout << x << " ";
    cout << endl;

    return 0;

}
```

输出:

```cpp
list1 before unique operation is : 1 1 1 2 2 3 3 4 
list1 after unique operation is : 1 2 3 4 

list1 after splice operation is : 1 2 4 6 2 3 4 

```

**8。交换(列表 2)** :-该功能用于**将一个列表元素与其他**进行交换。

```cpp
// C++ code to demonstrate the working of 
// swap()
#include<iostream>
#include<list> // for list functions
using namespace std;
int main()
{
    // Initializing list1
    list<int> gqlist1 = {1, 2, 3, 4};

    // Initializing list1
    list<int> gqlist2 = {2, 4, 6};

     // Displaying list before swapping
     cout << "The contents of 1st list "
             "before swapping are : ";
     for (int &x : gqlist1)
         cout << x << " ";
     cout << endl;
     cout << "The contents of 2nd list "
             "before swapping are : ";
     for (int &x : gqlist2)
         cout << x << " ";
     cout << endl;

     // Use of swap() to swap the list
     gqlist1.swap(gqlist2);

     // Displaying list after swapping
     cout << "The contents of 1st list "
             "after swapping are : ";
     for (int &x : gqlist1)
         cout << x << " ";
     cout << endl;

     cout << "The contents of 2nd list "
             "after swapping are : ";
     for (int &x : gqlist2)
         cout << x << " ";
     cout << endl;

    return 0;

}
```

输出:

```cpp
The contents of 1st list before swapping are : 1 2 3 4 
The contents of 2nd list before swapping are : 2 4 6 
The contents of 1st list after swapping are : 2 4 6 
The contents of 2nd list after swapping are : 1 2 3 4 

```

本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。