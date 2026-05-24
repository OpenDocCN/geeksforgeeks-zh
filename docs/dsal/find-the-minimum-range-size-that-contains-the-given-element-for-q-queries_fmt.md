# 找到包含 Q 查询给定元素的最小范围大小

> 原文：[https://www.geeksforgeeks.org/find-the-minimum-range-size-that-contains-the-given-element-for-q-queries/](https://www.geeksforgeeks.org/find-the-minimum-range-size-that-contains-the-given-element-for-q-queries/)

## 问题描述

给定一个由 **N** 对整数组成的数组 `interval[]`，其中每对整数表示值范围 `[L, R]`。另外，给定一个由 **M** 查询组成的整数数组 `Q[]`。对于每个查询，任务是找到包含该元素的最小范围的大小。如果不存在有效间隔，返回 **-1**。

## 示例

> **输入：** `interval[] = [[1, 4], [2, 3], [3, 6], [9, 25], [7, 15], [4, 4]]`
> `Q[] = [7, 50, 2]`
> **输出：** `[9, -1, 2]`
> **解释：** 元素 7 仅在 `[7, 15]` 范围内，因此答案将为 `15 - 7 + 1 = 8`。元素 50 不在任何范围内，因此答案将是 `-1`。
> 同样，元素 2 在 `[2, 3]` 和 `[1, 4]` 的范围内，但最小的范围是 `[2, 3]`，因此答案将是 `3 - 2 + 1 = 2`。

> **输入：** `interval[] = [[1, 4], [2, 4], [3, 6]]`
> `Q[] = [2, 3]`
> **输出：** `[3, 3]`

## 解法

### 暴力方法

解决问题最简单的方法是迭代数组 `range[]`，并为每个查询找到包含给定元素的最小范围。

- **时间复杂度：** `O(N × M)`
- **辅助空间：** `O(M)`

### 高效方法

使用优先级队列可以进一步优化上述方法。按照以下步骤解决问题：

1.  初始化一个向量向量，例如 `queries`，将所有查询连同其索引一起插入到数组 `Q` 中。
2.  使用向量的默认排序功能对向量 `interval` 和 `queries` 进行排序。
3.  初始化一个优先级队列，例如 `pq`，键为区间大小，值为范围的右边界。
4.  初始化一个向量，例如 `result`，它将存储每个查询的最小范围的大小。
5.  初始化一个整数变量，例如 `i`，它将保持数组中遍历元素的轨迹 `interval`。
6.  使用变量 `j` 在范围 `[0, M-1]` 中迭代，并执行以下步骤：
    - 当 `i < interval.size()` 和 `interval[i][0] <= query[j][0]` 时迭代，将 `-(interval[i][1] - interval[i][0] + 1)` 和 `interval[i][1]` 作为一对，并将 `i` 的值增加 `1`。
    - 现在从优先级队列 `pq` 中移除所有元素，其右元素小于 `queries[j][0]`。
    - 如果优先级队列 `pq` 的大小 `> 0`，则将 `result[queries[j][1]]` 的值修改为 `-pq.top()[0]`。
7.  返回数组 `res` 作为答案。

## 代码实现

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the size of minimum
// Interval that contains the given element
vector<int> minInterval(vector<vector<int> >& intervals,
                        vector<int>& q)
{
    // Store all the queries
    // along with their index
    vector<vector<int> > queries;

    for (int i = 0; i < q.size(); i++)
        queries.push_back({ q[i], i });

    // Sort the vector intervals and queries
    sort(intervals.begin(), intervals.end());
    sort(queries.begin(), queries.end());

    // Max priority queue to keep track
    // of intervals size and right value
    priority_queue<vector<int> > pq;

    // Stores the result of all the queries
    vector<int> result(queries.size(), -1);

    // Current position of intervals
    int i = 0;

    for (int j = 0; j < queries.size(); j++) {

        // Stores the current query
        int temp = queries[j][0];

        // Insert all the intervals whose left value
        // is less than or equal to the current query
        while (i < intervals.size()
               && intervals[i][0] <= temp) {

            // Insert the negative of range size and
            // the right bound of the interval
            pq.push(
                { -intervals[i][1] + intervals[i][0] - 1,
                  intervals[i++][1] });
        }

        // Pop all the intervals with right value
        // less than the current query
        while (!pq.empty() && temp > pq.top()[1]) {
            pq.pop();
        }

        // Check if the valid interval exists
        // Update the answer for current query
        // in result array
        if (!pq.empty())
            result[queries[j][1]] = -pq.top()[0];
    }
    // Return the result array
    return result;
}

// Driver Code
int main()
{
    // Given Input
    vector<vector<int> > intervals
        = { { 1, 4 }, { 2, 3 }, { 3, 6 }, { 9, 25 }, { 7, 15 }, { 4, 4 } };
    vector<int> Q = { 7, 50, 2, 3, 4, 9 };

    // Function Call
    vector<int> result = minInterval(intervals, Q);

    // Print the result for each query
    for (int i = 0; i < result.size(); i++)
        cout << result[i] << " ";
    return 0;
}
```

### JavaScript

```javascript
// Javascript program for the above approach

// Function to find the size of minimum
// Interval that contains the given element
function minInterval(intervals, q)
{
    // Store all the queries
    // along with their index
    var queries = [];

    for (var i = 0; i < q.length; i++)
        queries.push([q[i], i]);

    // Sort the vector intervals and queries
    intervals.sort((a,b)=> {
            if(a[0] == b[0])
                return a[1] - b[1];
            return a[0] - b[0];
        });
    queries.sort((a,b)=> {
            if(a[0] == b[0])
                return a[1]-b[1];
            return a[0]-b[0];
        });

    // Max priority queue to keep track
    // of intervals size and right value
    var pq = [];

    // Stores the result of all the queries
    var result = Array(queries.length).fill(-1);

    // Current position of intervals
    var i = 0;

    for (var j = 0; j < queries.length; j++) {

        // Stores the current query
        var temp = queries[j][0];

        // Insert all the intervals whose left value
        // is less than or equal to the current query
        while (i < intervals.length
               && intervals[i][0] <= temp) {

            // Insert the negative of range size and
            // the right bound of the interval
            pq.push(
                [ -intervals[i][1] + intervals[i][0] - 1,
                  intervals[i++][1] ]);
        }
        pq.sort((a,b)=> {
            if(a[0] == b[0])
                return a[1]-b[1];
            return a[0]-b[0];
        });

        // Pop all the intervals with right value
        // less than the current query
        while (pq.length != 0 && temp > pq[pq.length-1][1]) {
            pq.pop();
        }

        // Check if the valid interval exists
        // Update the answer for current query
        // in result array
        if (pq.length!=0)
            result[queries[j][1]] = -pq[pq.length-1][0];
    }
    // Return the result array
    return result;
}

// Driver Code
// Given Input
var intervals
    = [ [ 1, 4 ], [ 2, 3 ], [ 3, 6 ], [ 9, 25 ], [ 7, 15 ], [ 4, 4 ] ];
var Q = [ 7, 50, 2, 3, 4, 9 ];

// Function Call
var result = minInterval(intervals, Q);

// Print the result for each query
for (var i = 0; i < result.length; i++)
    document.write(result[i] + " ");

// This code is contributed by rrrtnx.
```

## 输出

```
9 -1 2 2 1 9 
```

## 复杂度分析

- **时间复杂度：** `O(NlogN + MlogM)`
- **辅助空间：** `O(N + M)`