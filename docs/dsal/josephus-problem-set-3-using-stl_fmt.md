# 约瑟夫斯问题 | 第三集（使用STL）

> 原文：[https://www.geeksforgeeks.org/josephus-problem-set-3-using-stl/](https://www.geeksforgeeks.org/josephus-problem-set-3-using-stl/)

给定 `N` 个人站成一个圆和一个整数 `K`。如果最初从第一个位置开始，从当前位置顺时针方向的第 `K` 个活着的人被杀死，然后当前位置转移到第 `(K+1)` 个活着的人的位置，并执行相同的步骤，直到只剩下一个人，任务是打印最后一个活着的人的位置。

**示例：**

> **输入：** `N = 5`，`K = 2`
> **输出：** `3`
> **解释：**
> 执行操作的一种方式是：
> 1.  第一步：最初，计数从位置 1 开始。因此，位置 2 的第 `K` 个活着的人被杀死，所以剩余的活着的人在位置 `{1, 3, 4, 5}`。
> 2.  第二步：现在，从位置 3 开始计数。因此，4 号位的第 `K` 个活着的人被杀死，所以剩余的活着的人在 `{1, 3, 5}` 号位。
> 3.  第三步：现在，从位置 5 开始计数。因此，1 号位的第 `K` 个生还者被杀死，所以剩余的生还者在 `{3, 5}` 号位。
> 4.  第四步：现在，从位置 3 开始计数。因此，5 号位的第 `K` 个生还者被杀，所以最后一个生还者在 3 号位。
>
> 因此，最后一个活着的人在 3 号位置。
>
> **输入：** `N = 10`，`K = 4`
> **输出：** `5`

本文的[第 1 集](https://www.geeksforgeeks.org/josephus-problem-set-1-a-on-solution/)和[第 2 集](https://www.geeksforgeeks.org/josephus-problem-set-2-simple-solution-k-2/)讨论了解决这个问题的不同方法。

**方法 1（使用向量）：** 上面给出的问题被称为[约瑟夫斯的问题](https://www.geeksforgeeks.org/josephus-problem-set-1-a-on-solution/)。使用 STL 库中的[递归](https://www.geeksforgeeks.org/recursion/)和[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)数据结构可以解决这个问题。按照以下步骤解决问题：

*   初始化一个[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)，比如 `arr[]` 来存储所有人的位置。
*   [使用变量 `i` 在范围](https://www.geeksforgeeks.org/range-based-loop-c/) `[1, N]` 中迭代，并在每次迭代中将 `i` 追加到向量 `arr[]` 中。
*   定义一个[递归函数](https://www.geeksforgeeks.org/recursive-functions/)，比如 `RecursiveJosephus(vector<int>::iterator it, vector<int> arr)`，其中 `it` 指向当前活着的人，从这里 `K` 个元素将被计数。
    *   如果[向量](https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/) `arr` 的大小为 `1`，则返回 `arr[0]` 中的值。
    *   在范围 `[1, K-1]` 内迭代，然后在每次迭代中，将其 `it` 递增 `1`，如果相等 `arr.end()`，然后将 `arr.begin()` 分配给 `it`。
    *   现在如果 `it` 指向的是[向量的最后一个元素](https://www.geeksforgeeks.org/last-element-of-vector-in-cpp-accessing-and-updating/) `arr`，那么[弹出向量的最后一个元素](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/) `arr`，然后用第 `(K+1)` 个活着的人的位置更新 `it`，即 `arr.begin()`。
    *   否则，[抹去](https://www.geeksforgeeks.org/vectorclear-vectorerase-c-stl/) `it` 所指的人的位置。删除后，`it` 现在指向第 `(K+1)` 人的位置。
*   最后，完成上述步骤后，调用函数 `RecursiveJosephus(arr.begin(), arr)`，打印其返回的值作为最后一个活着的人的位置。

以下是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Recursive auxiliary function to find
// the position of the last alive person
int RecursiveJosephus(vector<int>& arr, int K,
                      vector<int>::iterator it)
{
    // If size of arr is 1
    if (arr.size() == 1) {
        return arr[0];
    }

    // Iterate over the range [1, K-1]
    for (int i = 1; i < K; i++) {

        // Increment it by 1
        it++;

        // If it is equal to arr.end()
        if (it == arr.end()) {

            // Assign arr.begin() to it
            it = arr.begin();
        }
    }

    // If it is equal to prev(arr.end())
    if (it == prev(arr.end())) {

        // Assign arr.begin() to it
        it = arr.begin();

        // Remove the last element
        arr.pop_back();
    }
    else {

        // Erase the element at it
        arr.erase(it);
    }

    // Return the last alive person
    return RecursiveJosephus(arr, K, it);
}

// Function to find the position of the
// last alive person
int Josephus(int N, int K)
{
    // Stores positions of every person
    vector<int> arr;
    for (int i = 1; i <= N; i++)
        arr.push_back(i);

    // Function call to find the position
    // of the last alive person
    return RecursiveJosephus(arr, K, arr.begin());
}

// Driver Code
int main()
{
    // Given Input
    int N = 5;
    int K = 2;

    // Function Call
    cout << Josephus(N, K);
}
```

**输出**

```
3
```

**时间复杂度：** `O(N^2)`
**辅助空间：** `O(N)`

**方法 2（使用 SET）：** 这个问题可以使用[递归](https://www.geeksforgeeks.org/recursion/)和来自 STL 库的一个[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)数据结构来解决。按照以下步骤解决问题：

*   初始化一个[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)，比如说 `arr` 来存储所有人的位置。
*   [使用变量 `i`，在范围](https://www.geeksforgeeks.org/range-based-loop-c/) `[1, N]` 中迭代，并在每次迭代中在集合 `arr` 中插入 `i`。
*   定义一个[递归函数](https://www.geeksforgeeks.org/recursive-functions/)，比如 `RecursiveJosephus(set<int>::iterator it, set<int> arr)`，其中 `it` 指向当前活着的人的位置，从这里 `K` 个元素将被计数。
    *   如果集合 `arr` 的[大小为 `1`](https://www.geeksforgeeks.org/setsize-c-stl/)，则返回迭代器指向的值，`*it`。
    *   在范围 `[1, K-1]` 内迭代，然后在每次迭代中，将其 `it` 增加 `1`，如果等于 `arr.end()`，然后将 `arr.begin()` 分配给 `it`。
    *   现在如果 `it` 是指向集合 `arr` 的最后一个元素[的位置](https://www.geeksforgeeks.org/setbegin-setend-c-stl/)，那么[删除集合的最后一个元素](https://www.geeksforgeeks.org/how-to-delete-last-element-from-a-set-in-c/) `arr`，然后用更新 `it` 的位置第 `(K+1)` 个人，即 `arr.begin()`。
    *   否则，将 `it` 的[下一个迭代器](https://www.geeksforgeeks.org/stdnext-in-cpp/)的值存储在一个变量中，比如 `val`，然后[删除](https://www.geeksforgeeks.org/vectorclear-vectorerase-c-stl/) `it` 指向的位置。
    *   删除后，`it` 变为无效。因此，现在在集合中找到 `val` 的值，`arr`，然后将其分配给 `it`。现在 `it` 指向第 `(K+1)` 个活人的位置。
*   最后，完成上述步骤后，调用函数 `RecursiveJosephus(arr.begin(), arr)`，打印其返回的值作为最后一个活人的位置。

以下是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Recursive auxiliary function to find
// the position of the last alive person
int RecursiveJosephus(set<int>& arr, int K,
                      set<int>::iterator it)
{

    // If size of arr is 1
    if (arr.size() == 1) {
        return *it;
    }

    // Iterate over the range [1, K-1]
    for (int i = 1; i < K; i++) {

        // Increment it by 1
        it++;

        // If it is equal to arr.end()
        if (it == arr.end()) {

            // Assign arr.begin() to it
            it = arr.begin();
        }
    }

    // If it is equal to prev(arr.end())
    if (it == prev(arr.end())) {

        // Assign arr.begin() to it
        it = arr.begin();

        // Remove the last element
        arr.erase(prev(arr.end()));
    }
    else {

        // Stores the value pointed
        // by next iterator of it
        int val = (*next(it));

        // Erase the element at it
        arr.erase(it);

        // Update it
        it = arr.find(val);
    }

    // Return the position of
    // the last alive person
    return RecursiveJosephus(arr, K, it);
}

// Function to find the position
// of the last alive person
int Josephus(int N, int K)
{
    // Stores all the persons
    set<int> arr;

    for (int i = 1; i <= N; i++)
        arr.insert(i);

    // Function call to find the position
    // of the last alive person
    return RecursiveJosephus(arr, K, arr.begin());
}

// Driver Code
int main()
{
    // Given Input
    int N = 5;
    int K = 2;

    // Function Call
    cout << Josephus(N, K);
}
```

**输出**

```
3
```

**时间复杂度：** `O(N * K + N * log(N))`
**辅助空间：** `O(N)`