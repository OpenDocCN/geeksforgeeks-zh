# 在 C++ STL 中合并()

> 原文:[https://www.geeksforgeeks.org/merge-in-cpp-stl/](https://www.geeksforgeeks.org/merge-in-cpp-stl/)

C++ 在其 STL 库中提供了一个 merge()，这对于将两个排序容器合并成一个**单个**容器非常有用。
在表头**算法**中定义。它有两种实现方式。

**语法 1:使用运算符“<”**

```cpp
Template :
template 
  outiter merge (initer1 beg1, initer1 end1,
                        initer2 beg2, initer2 end2,
                        outiter res)

Parameters :
beg1 :  Input iterator to initial position of first sequence.
end1 :  Input iterator to final position of first sequence.

beg2 :  Input iterator to initial position of second sequence.
end2 :  Input iterator to final position of second sequence.

res : Output Iterator to initial position of resultant container.
Return value : 
Iterator to last element of the resulting container.

```

```cpp
// C++ code to demonstrate the working of
// merge() implementation 1

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initializing 1st container
    vector<int> arr1 = { 1, 4, 6, 3, 2 };

    // initializing 2nd container
    vector<int> arr2 = { 6, 2, 5, 7, 1 };

    // declaring resultant container
    vector<int> arr3(10);

    // sorting initial containers
    sort(arr1.begin(), arr1.end());
    sort(arr2.begin(), arr2.end());

    // using merge() to merge the initial containers
    merge(arr1.begin(), arr1.end(), arr2.begin(), arr2.end(), arr3.begin());

    // printing the resultant merged container
    cout << "The container after merging initial containers is : ";

    for (int i = 0; i < arr3.size(); i++)
        cout << arr3[i] << " ";
    return 0;
}
```

输出:

```cpp
The container after merging initial containers is : 1 1 2 2 3 4 5 6 6 7 

```

**语法 2:使用比较器功能**

```cpp
Template :
template 
  outiter merge (initer1 beg1, initer1 end1,
                        initer2 beg2, initer2 end2,
                        outiter res, Compare comp)

Parameters :
beg1 :  Input iterator to initial position of first sequence.
end1 :  Input iterator to final position of first sequence.

beg2 :  Input iterator to initial position of second sequence.
end2 :  Input iterator to final position of second sequence.

res : Output Iterator to initial position of resultant container.
comp : The comparator function that returns a boolean
true/false of the each elements compared. This function 
accepts two arguments. This can be function pointer or 
function object and cannot change values.
Return value : 
Iterator to last element of the resulting container.

```

```cpp
// C++ code to demonstrate the working of
// merge() implementation 2

#include <bits/stdc++.h>
using namespace std;

// comparator function to reverse merge sort
struct greaters {
    bool operator()(const long& a, const long& b) const
    {
        return a > b;
    }
};

int main()
{
    // initializing 1st container
    vector<int> arr1 = { 1, 4, 6, 3, 2 };

    // initializing 2nd container
    vector<int> arr2 = { 6, 2, 5, 7, 1 };

    // declaring resultant container
    vector<int> arr3(10);

    // sorting initial containers
    // in descending order
    sort(arr1.rbegin(), arr1.rend());
    sort(arr2.rbegin(), arr2.rend());

    // using merge() to merge the initial containers
    // returns descended merged container
    merge(arr1.begin(), arr1.end(), arr2.begin(), arr2.end(), arr3.begin(), greaters());

    // printing the resultant merged container
    cout << "The container after reverse merging initial containers is : ";

    for (int i = 0; i < arr3.size(); i++)
        cout << arr3[i] << " ";
    return 0;
}
```

输出:

```cpp
The container after reverse merging initial containers is : 7 6 6 5 4 3 2 2 1 1 

```

**可能的应用:**合并功能可用于以**排序顺序**获得两个堆栈的**单个堆栈。这些可以是一叠书或笔记。让我们讨论一个简单的例子，它根据两叠钞票的价值，将两叠钞票按升序排列成一叠。**

```cpp
// C++ code to demonstrate the application of
// merge() stacking notes

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initializing 1st container
    // containing denominations
    vector<int> stack1 = { 50, 20, 10, 100, 2000 };

    // initializing 2nd container
    // containing demonitions
    vector<int> stack2 = { 500, 2000, 10, 100, 50 };

    // declaring resultant stack
    vector<int> stack3(10);

    cout << "The original 1st stack : ";
    for (int i = 0; i < 5; i++)
        cout << stack1[i] << " ";

    cout << endl;

    cout << "The original 2nd stack : ";
    for (int i = 0; i < 5; i++)
        cout << stack2[i] << " ";

    cout << endl;

    // sorting initial stacks of notes
    // in descending order
    sort(stack1.begin(), stack1.end());
    sort(stack2.begin(), stack2.end());

    // using merge() to merge the initial stacks
    // of notes
    merge(stack1.begin(), stack1.end(), stack2.begin(), stack2.end(), stack3.begin());

    // printing the resultant stack
    cout << "The resultant stack of notes is : ";

    for (int i = 0; i < stack3.size(); i++)
        cout << stack3[i] << " ";
    return 0;
}
```

输出:

```cpp
The original 1st stack : 50 20 10 100 2000 
The original 2nd stack : 500 2000 10 100 50 
The resultant stack of notes is : 10 10 20 50 50 100 100 500 2000 2000 

```

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。