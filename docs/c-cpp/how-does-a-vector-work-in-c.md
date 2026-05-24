# 向量在 C++ 中是如何工作的？

> 原文:[https://www.geeksforgeeks.org/how-does-a-vector-work-in-c/](https://www.geeksforgeeks.org/how-does-a-vector-work-in-c/)

C++ 中的一个[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)可以在添加更多元素时自行调整大小。它还允许删除元素。
下面是当数组变满，用户希望添加一个项目时的一个非常基本的想法。
1)在堆内存上创建更大的内存(例如两倍大小的内存)。
2)将当前内存元素复制到新内存中。
3)由于现在可用内存更大，现在添加了新项目。
4)删除旧记忆。
然而，实际的库实现可能更复杂。如果我们在当前数组变满(或即将变满)时创建一个新的双大小数组，并将当前元素复制到新的双大小数组中，我们得到的摊销时间复杂度为 O(1)。因此，特定的插入操作可能成本很高，但总的时间复杂度仍然是 0(1)。证明请参考[算法分析|第五集(摊销分析介绍)](https://www.geeksforgeeks.org/analysis-algorithm-set-5-amortized-analysis-introduction/)。所以 push_back()的时间复杂度为 O(1)。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate push_back()
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector{ 1, 2, 3, 4, 5 };

    myvector.push_back(6);

    // Vector becomes 1, 2, 3, 4, 5, 6

    for (auto x : myvector)
        cout << x << " ";
}
```

输出:

```cpp
1 2 3 4 5 6 
```

**vector()中 erase()的时间复杂度是多少？**
由于擦除一个元素需要移动其他元素(以确保随机存取)，因此擦除的时间复杂度为 O(n)。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// working of erase() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector{ 1, 2, 3, 4, 5 };

    auto it = myvector.begin();
    myvector.erase(it);

    // Printing the Vector
    for (auto x : myvector)
        cout << x << " ";
    return 0;
}
```

输出:

```cpp
2 3 4 5 
```