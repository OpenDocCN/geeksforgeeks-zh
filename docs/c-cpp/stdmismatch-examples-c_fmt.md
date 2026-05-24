# std::mismatch() 在 C++ 中的示例

> 原文: [https://www.geeksforgeeks.org/stdmismatch-examples-c/](https://www.geeksforgeeks.org/stdmismatch-examples-c/)

C++ STL 有很多有用的功能，可以帮助我们完成各种编程任务。其中一个这样的函数是 `mismatch()`。该函数在 `<algorithm>` 头文件中定义，帮助比较两个容器的不匹配。该功能有两个版本。本文将讨论这两个问题。

## 1. mismatch( start_iter1, end_iter1, start_iter2 )

这个版本的 `mismatch()` 只测试不相等。
这里有 3 个参数：
- `start_iter1`: 第一个容器的起始迭代器
- `end_iter1`: 第一个容器的结束迭代器
- `start_iter2`: 第二个容器的起始迭代器，从这里开始比较

该函数返回第一个不匹配对指针，第一个元素指向第一个容器的第一个不匹配元素的位置，第二个元素指向第二个容器的第一个不匹配元素的位置。如果没有发现不匹配，第一个元素指向第一个容器的最后一个元素之后的位置，第二个元素指向第二个容器中的对应位置。

```cpp
// C++ code to demonstrate the working of 
// mismatch( start_iter1, end_iter1, start_iter2 )

#include<iostream>
#include<algorithm> 
#include<vector>
using namespace std;

int main()
{
    // initializing vectors
    vector<int> v1 = { 1, 10, 15, 20 };
    vector<int> v2 = { 1, 10, 25, 30, 45 };
    vector<int> v3 = { 1, 10, 15, 20 };
    vector<int> v4 = { 1, 10, 15, 20, 24 };

    // declaring pointer pair
    pair< vector<int>::iterator,
    vector<int>::iterator > mispair;

    // using mismatch() to search for 1st mismatch
    mispair = mismatch(v1.begin(), v1.end(), v2.begin());

    // printing the mismatch pair
    // 1st mismatch at 15 and 25
    cout << "The 1st mismatch element of 1st container : ";
    cout << *mispair.first << endl;

    cout << "The 1st mismatch element of 2nd container : ";
    cout << *mispair.second << endl;

    // using mismatch() to search for 1st mismatch
    mispair = mismatch(v3.begin(), v3.end(), v4.begin());

    // printing the mismatch pair
    // no mismatch
    // points to position after last 0 and corresponding 24
    cout << "The returned value from 1st container is : ";
    cout << *mispair.first << endl;

    cout << "The returned value from 2nd container is : ";
    cout << *mispair.second << endl;
}
```

输出:

```cpp
The 1st mismatch element of 1st container : 15
The 1st mismatch element of 2nd container : 25
The returned value from 1st container is  : 0
The returned value from 2nd container is  : 24
```

## 2. mismatch( start_iter1, end_iter1, start_iter2, comparator )

这个函数的工作原理与上述版本几乎相同，但它不仅可以找到相等性不匹配，还可以通过用户定义的比较器函数找到其他用户定义的、期望的不匹配，该函数作为第四个参数传入并返回布尔值 true 或 false。

```cpp
// C++ code to demonstrate the working of
// mismatch( start_iter1, end_iter1, start_iter2, comparator )

#include<iostream>
#include<algorithm> 
#include<vector>
using namespace std;

// comparator function
// returns true when element from 
// 1st element is greater than 2nd
bool compare(int a, int b)
{   
    return (a>b);
}

int main()
{
    // initializing vectors
    vector<int> v1 = { 23, 13, 15, 20 };
    vector<int> v2 = { 1, 10, 25, 30, 45 };
    vector<int> v3 = { 12, 100, 152, 204 };
    vector<int> v4 = { 1, 10, 15, 20, 24 };

    // declaring pointer pair
    pair< vector<int>::iterator,
    vector<int>::iterator > mispair;

    // using mismatch() to search for 1st mismatch
    mispair = mismatch(v1.begin(), v1.end(), v2.begin(), compare);

    // printing the mismatch pair
    // 1st mismatch at 15 and 25
    // 15 is 1st element less than 2nd at same position
    cout << "The 1st mismatch element of 1st container : ";
    cout << *mispair.first << endl;

    cout << "The 1st mismatch element of 2nd container : ";
    cout << *mispair.second << endl;

    // using mismatch() to search for 1st mismatch
    mispair = mismatch(v3.begin(), v3.end(), v4.begin(), compare);

    // printing the mismatch pair
    // no mismatch
    // all elements in 1st container are greater than 2nd
    // points to position after last 0 and corresponding 24
    cout << "The returned value from 1st container is  : ";
    cout << *mispair.first << endl;

    cout << "The returned value from 2nd container is  : ";
    cout << *mispair.second << endl;
}
```

输出:

```cpp
The 1st mismatch element of 1st container : 15
The 1st mismatch element of 2nd container : 25
The returned value from 1st container is  : 0
The returned value from 2nd container is  : 24
```

本文由 **[【曼吉特·辛格】](https://github.com/Manjeet04)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。