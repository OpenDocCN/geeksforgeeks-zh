# c++ 中迭代器失效

> 原文:[https://www.geeksforgeeks.org/iterator-invalidation-cpp/](https://www.geeksforgeeks.org/iterator-invalidation-cpp/)

在 C++ 中使用迭代器时应该小心。当我们使用迭代器迭代容器时，迭代器可能会失效。这可能是由于迭代时容器的形状和大小发生了变化。让我们举个例子来理解这个-

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate iterator
// invalidations
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Creating a sample vector
    vector <int> v = {1, 5, 10, 15, 20};

    // Changing vector while iterating over it
    // (This causes iterator invalidation)
    for (auto it = v.begin(); it != v.end(); it++)
        if ((*it) == 5)
            v.push_back(-1);

    for (auto it = v.begin(); it != v.end(); it++)
        cout << (*it) << " ";

    return 0;   
}
```

在上面的示例代码中，当我们在迭代向量时添加一个元素-1 时，向量的大小可能会超过最大大小，因此会为向量分配一个新的内存，并将所有元素复制到那里。但是，我们的迭代器仍然指向以前的旧内存地址。所以，现在我们可以说迭代器失效了。这是无效的一个例子。下面给出了迭代器失效的一些规则。
**迭代器失效规则【来源:**[**stack overflow**](https://stackoverflow.com/questions/6438086/iterator-invalidation-rules/11336379#11336379) ****1。插入**
**a. Vector-** 所有指向插入点之前的元素的迭代器不受影响，但所有其他迭代器都无效。但是，在这种情况下，如果由于插入，向量的大小变得超过先前的容量，那么所有迭代器都会失效，如上面的例子中所讨论的。
**b. deque-** 所有迭代器和引用都是无效的，除非插入的成员在 deque 的末尾(前面或后面)(在这种情况下，所有迭代器都是无效的，但是对元素的引用不受影响)。
**c. List-** 所有迭代器和引用不受影响。
**d .集合、映射、多集合、多映射-** 所有迭代器和引用不受影响。
**2。擦除**
**a .向量-** 擦除点后的每个迭代器和引用都是无效的。
**b. deque-** 所有迭代器和引用都是无效的，除非被擦除的成员在 deque 的末端(前面或后面)(在这种情况下，只有迭代器和对被擦除成员的引用是无效的)
**c. list-** 只有对被擦除元素的迭代器和引用是无效的。
**d .集合、映射、多集合、多映射-** 只有迭代器和对被擦除元素的引用是无效的。
T42【3】。根据插入/擦除调整
**的大小。
**注释-** 迭代器失效并不总是意味着取消对这种迭代器的引用会导致程序崩溃。它还包括迭代器没有指向它应该指向的元素的可能性。
本文由 [**Ashish Sharma**](https://auth.geeksforgeeks.org/profile.php?user=ashish136) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。****