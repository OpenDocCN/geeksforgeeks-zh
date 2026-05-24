# 如何在 C++ 中找到向量中给定元素的索引

> 原文:[https://www . geesforgeks . org/如何找到给定 cpp 中矢量元素的索引/](https://www.geeksforgeeks.org/how-to-find-index-of-a-given-element-in-a-vector-in-cpp/)

给定一个由 **N** 个整数和一个元素 **K** 组成的[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/) **V** ，任务是在向量 **V** 中找到元素 **K** 的索引。如果矢量中不存在该元素，则打印 **-1** 。
**示例:**

> **输入:** V = {1，45，54，71，76，17}，K = 54
> **输出:** 2
> **说明:**
> 54 的指数为 2，因此输出为 2。
> **输入:** V = {3，7，9，11，13}，K = 12
> **输出:** -1

**方法:**
按照以下步骤解决问题:

*   [**find():**](https://www.geeksforgeeks.org/std-find-in-cpp/) 用于查找元素在向量中的位置。
*   从 find 函数返回的迭代器中减去向量的基本迭代器。
*   最后返回减法返回的索引。

下面是上述方法的实现:

## C++

```cpp
// C++ program to find the index
// of an element in a vector
#include <bits/stdc++.h>
using namespace std;

// Function to print the
// index of an element
void getIndex(vector<int> v, int K)
{
    auto it = find(v.begin(), v.end(), K);

    // If element was found
    if (it != v.end())
    {

        // calculating the index
        // of K
        int index = it - v.begin();
        cout << index << endl;
    }
    else {
        // If the element is not
        // present in the vector
        cout << "-1" << endl;
    }
}
// Driver Code
int main()
{
    // Vector
    vector<int> v = { 1, 45, 54, 71, 76, 17 };
    // Value whose index
    // needs to be found
    int K = 54;
    getIndex(v, K);
    return 0;
}
```

**Output:** 

```cpp
2

```

**时间复杂度:**O(N)
T3】辅助空间: O(1)