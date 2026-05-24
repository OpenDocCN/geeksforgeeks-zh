# std::count()在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/std-count-cpp-stl/](https://www.geeksforgeeks.org/std-count-cpp-stl/)

std::count()返回给定范围内元素出现的次数。返回范围[第一个，最后一个]中比较等于 val 的元素数。

> //返回值在
> //范围【开始，结束】
> 内出现的次数(迭代器第一，迭代器最后，T &值)
> 
> **第一个，最后一个:**向元素序列的初始和最终位置输入迭代器。
> T3】val:值匹配

**复杂度**是复杂度 O(n)的顺序。将每个元素与特定值进行一次比较。

**计算数组中的出现次数。**

```cpp
// C++ program for count in C++ STL for
// array
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int arr[] = { 3, 2, 1, 3, 3, 5, 3 };
    int n = sizeof(arr) / sizeof(arr[0]);
    cout << "Number of times 3 appears : "
         << count(arr, arr + n, 3);

    return 0;
}
```

```cpp
Number of times 3 appears : 4

```

**计算向量中的出现次数。**

```cpp
// C++ program for count in C++ STL for
// a vector
#include <bits/stdc++.h>
using namespace std;

int main()
{
    vector<int> vect{ 3, 2, 1, 3, 3, 5, 3 };
    cout << "Number of times 3 appears : "
         << count(vect.begin(), vect.end(), 3);

    return 0;
}
```

```cpp
Number of times 3 appears : 4

```

**计算字符串中出现的次数。**

```cpp
// C++ program for the count in C++ STL
// for a string
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string str = "geeksforgeeks";

    cout << "Number of times 'e' appears : " 
         << count(str.begin(), str.end(), 'e');

    return 0;
}
```

```cpp
Number of times 'e' appears : 4

```

本文由 **Jatin Goyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。