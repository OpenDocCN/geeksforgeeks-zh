# 标准::C++ 中的距离

> 原文:[https://www.geeksforgeeks.org/stddistance-in-c/](https://www.geeksforgeeks.org/stddistance-in-c/)

如果我们有两个迭代器，并且我们想要找到这两个迭代器之间的元素总数，那么这是由头文件中定义的 **std::distance()** 来实现的。
它有一个重要的特点，就像我们在科学中有矢量一样，既有大小也有方向，std::distance 也有与之相关的方向。这意味着计算第一个和最后一个之间的距离，然后计算最后一个和第一个之间的距离将不会相同，因为在第二种情况下，它将有一个负号与之相关联，因为我们正在向后移动。
**语法:**

```cpp
std::distance(InputIterator first, InputIterator last)
Here, first and last are input iterators between which we have to calculate distance.

Returns: The number of elements between first and last.
```

**例:**

```cpp
Input: v = 10 20 30 40 50
first pointing to v.begin() and last pointing to v.end()
Output: No. of elements: 5
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate std::distance()
#include <iostream>
#include <vector>
#include <iterator>
using namespace std;
int main()
{
    vector<int> v;
    int i;

    for (i = 0; i < 10; ++ i)
    {
        v.push_back(i);
    }

    /*v contains 0 1 2 3 4 5 6 7 8 9*/

    vector<int>::iterator first;
    vector<int>::iterator last;

    // first pointing to 0
    first = v.begin();

    // last pointing to 5
    last = v.begin() + 5;

    // Calculating no. of elements between first and last
    int num = std::distance(first, last);

    // Displaying num
    cout << num << "\n";
    return 0;
}
```

输出:

```cpp
5
```

这里，第一个(指向 0)和最后一个(指向 5)之间的元素总数是 5，即 0 1 2 3 4。所以最后指向的元素没有被距离()计数。

**当我们在计算距离时颠倒顺序会发生什么？**

因为它会计算两个输入迭代器之间的元素数量，所以需要记住的一点是，在计算距离时，它不会计算最后一个指向的元素(如果有)，而第一个指向的元素会被计算，即范围是[第一个，最后一个]。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate the use of std::distance
// with reverse order
#include <iostream>
#include <vector>
#include <iterator>
using namespace std;
int main()
{
    vector<int> v;
    int i;

    for (i = 0; i < 10; ++ i)
    {
        v.push_back(i);
    }

    // Calculating no. of elements in vector v
    int num = std::distance(v.begin(), v.end());

    // Displaying num
    cout << num << "\n";

    // Calculating in reverse order
    num = std::distance(v.end(), v.begin());

    // Displaying num
    cout << num << "\n";
    return 0;
}
```

输出:

```cpp
10
-10
```

**时间复杂度:**对于随机访问迭代器是常数，对于所有其他迭代器是 O(n)。
本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。