# c++ STL 中复制的不同方法| std::copy()，copy_n()，copy_if()，copy_backward()

> 原文:[https://www . geesforgeks . org/different-methods-copy-c-STL-STD copy-copy _ n-copy _ if-copy _ backward/](https://www.geeksforgeeks.org/different-methods-copy-c-stl-stdcopy-copy_n-copy_if-copy_backward/)

C++ STL 中存在各种各样的 copy()，允许以不同的方式执行复制操作，它们都有自己的用途。这些都在标题<algorithm>中定义。本文向每个人介绍这些在日常编程中使用的函数。
**1。复制(strt_iter1，end_iter1，strt_iter2) :** 用于将元素的一个**范围**从一个容器复制到另一个容器的通用复制功能。它需要 3 个参数:</algorithm>

*   **strt_iter1 :** 指向源容器开头的指针，元素必须从这里开始复制。
*   **end_iter1 :** 指向源容器末尾的指针，直到必须复制元素的地方。
*   **strt_iter2 :** 指向目标容器开始的指针，指向元素必须开始复制的位置。

**2。copy_n(strt_iter1，num，strt_iter2) :** 这个版本的 copy 可以自由选择在目标容器中需要复制多少元素。它还需要 3 个参数:

*   **strt_iter1 :** 指向源容器开头的指针，元素必须从这里开始复制。
*   **num :** 整数，指定从 strt_iter1 开始将多少个数字复制到目标容器。如果输入负数，则不执行任何操作。
*   **strt_iter2 :** 指向目标容器开始的指针，指向元素必须开始复制的位置。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of copy()
// and copy_n()

#include<iostream>
#include<algorithm> // for copy() and copy_n()
#include<vector>
using namespace std;

int main()
{

   // initializing source vector
   vector<int> v1 = { 1, 5, 7, 3, 8, 3 };

   // declaring destination vectors
   vector<int> v2(6);
   vector<int> v3(6);

   // using copy() to copy 1st 3 elements
   copy(v1.begin(), v1.begin()+3, v2.begin());

   // printing new vector
   cout << "The new vector elements entered using copy() : ";
   for(int i=0; i<v2.size(); i++)
   cout << v2[i] << " ";

   cout << endl;

   // using copy_n() to copy 1st 4 elements
   copy_n(v1.begin(), 4, v3.begin());

   // printing new vector
   cout << "The new vector elements entered using copy_n() : ";
   for(int i=0; i<v3.size(); i++)
   cout << v3[i] << " ";

}
```

**输出:**

```cpp
The new vector elements entered using copy() : 1 5 7 0 0 0 
The new vector elements entered using copy_n() : 1 5 7 3 0 0 
```

**3。copy_if():** 顾名思义，这个函数根据一个“**条件**的结果进行复制。这是在**第四个参数**的帮助下提供的，一个**函数返回一个布尔值**。
这个函数接受 4 个参数，其中 3 个类似于 copy()和一个附加函数，当返回 true 时，复制一个数字，否则不复制数字。
**4。copy_backward():** 该函数从向后开始将元素复制到目标容器**中，并继续复制，直到所有数字都没有被复制。复制从“ **strt_iter2** 开始，但方向相反。它也接受与 copy()类似的参数。**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate the working of copy_if()
// and copy_backward()

#include<iostream>
#include<algorithm> // for copy_if() and copy_backward()
#include<vector>
using namespace std;

int main()
{

    // initializing source vector
    vector<int> v1 = { 1, 5, 6, 3, 8, 3 };

    // declaring destination vectors
    vector<int> v2(6);
    vector<int> v3(6);

    // using copy_if() to copy odd elements
    copy_if(v1.begin(), v1.end(), v2.begin(), [](int i){return i%2!=0;});

    // printing new vector
    cout << "The new vector elements entered using copy_if() : ";
    for(int i=0; i<v2.size(); i++)
    cout << v2[i] << " ";

    cout << endl;

    // using copy_backward() to copy 1st 4 elements
    // ending at second last position
    copy_backward(v1.begin(), v1.begin() + 4, v3.begin()+ 5);

    // printing new vector
    cout << "The new vector elements entered using copy_backward() : ";
    for(int i=0; i<v3.size(); i++)
    cout << v3[i] << " ";

}
```

**输出:**

```cpp
The new vector elements entered using copy_if() : 1 5 3 3 0 0 
The new vector elements entered using copy_backward() : 0 1 5 6 3 0 
```

**5。使用插入器()复制:**

在 copy()操作之前，让我们了解一下 inserter()的语法。

inserter()用作我们想要复制容器元素的目标。

inserter()接受两个参数。第一个是任意类型的容器，第二个是容器的迭代器。

它返回一个在任意类型的容器上工作的 insert_iterator 的实例。这个包装函数有助于创建 insert_iterator 实例。键入%iterator 的名称需要知道容器的确切完整类型，这可能会很乏味，并且会妨碍泛型编程。使用这个函数可以让你利用自动模板参数推导，让编译器为你匹配正确的类型。

插入器()的语法:

```cpp
std::inserter(Container& x, typename Container::iterator it);

x: Destination container where the new elements will 
be inserted.
it: Iterator pointing to the insertion point.

Returns: An insert_iterator that inserts elements into 
x at the position indicated by it.
```

使用插入器()复制的语法:

```cpp
copy(strt_iter1, end_iter1, inserter(Container& x, typename Container::iterator it));
```

## C++

```cpp
// C++ code to demonstrate the working of copy() using inserter()

#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;

int main()
{

    vector<int> v1 = {1, 5, 7, 3, 8, 3};
    vector<int>::iterator itr;
    vector<int> v2;

    //using inserter()
    copy(v1.begin(), v1.end(), inserter(v2, itr));

    cout << "\nThe new vector elements entered using inserter: ";
    for (int i = 0; i < v2.size(); i++)
        cout << v2[i] << " ";

}
```

输出:

```cpp
The new vector elements entered using inserter: 1 5 7 3 8 3 
```

本文由 [**【曼吉特·辛格】**](https://www.facebook.com/manjeet.04.singh) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。