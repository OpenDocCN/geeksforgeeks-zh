# c++ 中的上限

> 原文:[https://www.geeksforgeeks.org/upper_bound-in-cpp/](https://www.geeksforgeeks.org/upper_bound-in-cpp/)

upper_bound()是标题<algorithm>中定义的 C++ 中的标准库函数。它返回一个迭代器，指向大于值的范围[第一个，最后一个]中的第一个元素，如果找不到这样的元素，则返回最后一个。该范围内的元素应该已经相对于 val 进行了排序或至少进行了分区。</algorithm>

**模板:**

> **语法 1:
> ForwardIterator 上界(ForwardIterator 第一，ForwardIterator 最后，const T&val)；**
> **语法 2:
> ForwardIterator 上界(ForwardIterator 第一，ForwardIterator 最后，const T T&val，Compare comp)；**
> 
> **第一个，最后一个**:使用的范围是【第一个，最后一个】，包含第一个和最后一个之间的所有元素，包括第一个指向的元素，但不包括最后一个指向的元素。
> 
> **val:**范围内要搜索的上界值。
> 
> **comp:** 二元函数，接受两个参数(第一个是 ForwardIterator 指向的类型，第二个是 always val)，并返回一个可转换为 bool 的值。该函数不得修改其任何参数。这可以是函数指针
> 或函数对象。
> 
> **返回类型:**范围内 val 上限的迭代器。如果该范围内的所有元素都小于 val，则函数返回 last。

**示例:**

```cpp
Input : 10 20 30 30 40 50
Output : upper_bound for element 30 is at index 4

Input : 10 20 30 40 50
Output : upper_bound for element 45 is at index 4

Input : 10 20 30 40 50
Output : upper_bound for element 60 is at index 5

```

下面是一些 C++ 程序来说明 std::upper_bound 的用法:

```cpp
// CPP program to illustrate using 
// std :: upper_bound with vectors
#include <bits/stdc++.h>

// Driver code
int main()
{
    std::vector<int> v{ 10, 20, 30, 40, 50 };

    // Print vector
    std::cout << "Vector contains :";
    for (int i = 0; i < v.size(); i++)
        std::cout << " " << v[i];
    std::cout << "\n";

    std::vector<int>::iterator upper1, upper2;

    // std :: upper_bound
    upper1 = std::upper_bound(v.begin(), v.end(), 35);
    upper2 = std::upper_bound(v.begin(), v.end(), 45);

    std::cout << "\nupper_bound for element 35 is at position : " 
              << (upper1 - v.begin());
    std::cout << "\nupper_bound for element 45 is at position : "
              << (upper2 - v.begin());

    return 0;
}
```

输出:

```cpp
Vector contains : 10 20 30 40 50
upper_bound for element 35 is at position : 3
upper_bound for element 45 is at position : 4

```

```cpp
// CPP program to illustrate using 
// std :: upper_bound with arrays
#include <bits/stdc++.h>
using namespace std;

// Main Function
int main()
{
    int arr[] = { 10, 20, 30, 40, 50 };

    // Print elements of array
    cout << "Array contains :";
    for (int i = 0; i < 5; i++)
        cout << " " << arr[i];
    cout << "\n";

    // using upper_bound
    int upper1 = upper_bound(arr, arr+5, 35) - arr;
    int upper2 = upper_bound(arr, arr+5, 45) - arr;

    cout << "\nupper_bound for element 35 is at position : " 
              << (upper1);
    cout << "\nupper_bound for element 45 is at position : "
              << (upper2);

    return 0;
}
```

输出:

```cpp
Array contains : 10 20 30 40 50
upper_bound for element 35 is at position : 3
upper_bound for element 45 is at position : 4

```

**时间复杂度:**执行的比较次数是第一次和最后一次之间距离的对数。即，(最多 log2(倒数第一)+ O(1)比较)。

**重要点**

*   std::upper_bound()返回传递给它的值的上界的迭代器。
*   std::upper_bound()仅适用于排序的序列。即具有排序元素的向量或具有排序元素的数组。

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。