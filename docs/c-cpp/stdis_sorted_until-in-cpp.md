# STD::is _ sorted _ 直到在 C++ 中

> 原文:[https://www.geeksforgeeks.org/stdis_sorted_until-in-cpp/](https://www.geeksforgeeks.org/stdis_sorted_until-in-cpp/)

**STD::is _ sorted _ 直到**用于找出范围[第一个，最后一个]中第一个未排序的元素。它返回一个迭代器到范围中第一个未排序的元素，所以第一个和返回的迭代器之间的所有元素都被排序。
也可以用来统计范围内排序元素的总数。它是在头文件中定义的。在这种情况下，整个范围被排序，它将返回一个指向 last 的迭代器。
有两种使用方式，如下图:

**使用“<”比较元素:**
**语法:**

```cpp
template 
ForwardIterator is_sorted_until (ForwardIterator first, ForwardIterator last);

first: Forward iterator to the first element in the list.
last: forward iterator to the last element in the list.

Return Value: It returns an iterator to the first 
unsorted element in the list.
It returns last in case if there is only one element in 
the list or if all the elements are sorted.

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate the use of std::is_sorted_until
#include <iostream>
#include <algorithm>
using namespace std;
int main()
{
    int v[] = { 1, 2, 3, 4, 7, 10, 8, 9 }, i;

    int* ip;

    // Using std::is_sorted_until
    ip = std::is_sorted_until(v, v + 8);

    cout << "There are " << (ip - v) << " sorted elements in "
         << "the list and the first unsorted element is " << *ip;

    return 0;
}
```

**输出:**

```cpp
There are 6 sorted elements in the list and the first unsorted element is 8
```

**通过使用预定义函数进行比较:**
语法:

```cpp
template 
 ForwardIterator is_sorted_until (ForwardIterator first, ForwardIterator last,
 Compare comp);

Here, first and last are the same as previous case.

comp: Binary function that accepts two elements in the 
range as arguments, and returns a value convertible to bool.
The value returned indicates whether the element passed as
first argument is considered to go before the second in the specific
strict weak ordering it defines.

The function shall not modify any of its arguments.
This can either be a function pointer or a function object.

Return Value: It returns an iterator 
to the first unsorted element in the list.
It returns last in case if there is only one element in 
the list or if all the elements are sorted.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate
// the use of std::nth_element
// C++ program to demonstrate the
// use of std::nth_element
#include <algorithm>
#include <iostream>
using namespace std;

// Defining the BinaryFunction
bool comp(int a, int b) { return (a < b); }
int main()
{
    int v[] = { 1, 3, 20, 10, 45, 33, 56, 23, 47 }, i;
    int* ip;

    // Using std::is_sorted_until
    ip = std::is_sorted_until(v, v + 9, comp);

    cout << "There are " << (ip - v)
         << " sorted elements in "
         << "the list and the first unsorted element is "
         << *ip;

    return 0;
}
```

**输出:**

```cpp
There are 3 sorted elements in the list and the first unsorted element is 10
```

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。