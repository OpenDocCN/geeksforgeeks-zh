# 通过更新去除 K 个最小和最大元素后，查询计算数组平均值

> 原文：[https://www.geeksforgeeks.org/queries-to-calculate-average-of-an-array-after-removing-k-smallest-and-largest-elements-with-updates/](https://www.geeksforgeeks.org/queries-to-calculate-average-of-an-array-after-removing-k-smallest-and-largest-elements-with-updates/)

给定两个正整数 `N` 和 `K`，初始化一个空的数组 `arr[]` 和 `Q` 以下两种类型的查询数：

*   **添加元素(`x`):** 在数组 `arr[]` 中插入元素 `X`。如果数组的大小变得大于 `N`，则从数组的开始处移除元素。
*   **`calculateSpecialAverage()`:** 先去掉 `K` 最小最大元素，后求数组元素的平均值。如果数组的大小小于 `N`，则打印 `-1`。

任务是处理给定的查询并相应地打印结果。

**示例：**

> **输入：** `N = 3`，`K = 1`，`Q = 5`，查询[] = { `addInteger(4)`，`addInteger(2)`，`calculateSpecialAverage()`，`addInteger(10)`，`calculateSpecialAverage()`}
> **输出：** `-1`，`4`
> **解释：**
> 以下是执行的查询：
> **查询 1** 是在数组中插入元素 `4`，`arr[]` 变成 `{4}`。
> **查询 2** 是在数组中插入元素 `2`，`arr[]` 变成 `{4, 2}`。
> **查询 3** 是查找平均值。由于数组的大小小于 `N`（`= 3`），打印 `-1`。
> **查询 4** 是在数组中插入元素 `10`，`arr[]` 变成 `{4, 2, 10}`。
> **查询 5** 是查找平均值。由于数组的大小=`3`，去掉 `K`（`= 1`）最小的元素即 `2`，然后去掉最大的元素即 `10`。现在平均值将是 `4/1 = 4`。

> **输入：** `N = 3`，`K = 1`，`Q = 5`，查询[] = { `addInteger(4)`，`addInteger(21)`，`calculateSpecialAverage()`}
> **输出：** `-1`

**方法：** 给定的问题可以通过使用多集来解决。按照以下步骤解决问题：

*   初始化三个多集 `left`、`right` 和 `mid` 来存储 `K` 最小、`K` 最大以及剩余的 `(N–2 * K)` 整数。
*   声明一个大小为 `N` 的向量 `v` 来存储最后一个 `N` 整数。
*   声明一个整数变量 `pos` 来跟踪当前索引，声明一个整数 `sum` 来存储 `mid` 多集的值之和，这是计算 `(N–2 * K)` 整数平均值所需的和。
*   定义一个函数 `add` 根据其值在 `left`、`mid` 或 `right` 多集插入一个整数。要在正确的多集合中插入整数，请执行以下步骤：
    *   最初，在 `left` 多集插入整数。
    *   如果 `left` 多集的大小超过 `k`，则从 `left` 多集中删除最大的整数，并将其插入到 `mid` 多集中。
    *   如果 `mid` 多集的大小超过 `(n–2 * k)`，则从 `mid` 多集中删除最大的整数，并将其插入到 `right` 多集中。
    *   在 `mid` 多集移除和添加整数时，保持 `sum` 的正确值，即如果从 `mid` 多集移除一个整数，则从 `sum` 中减去其值，同样，如果在 `mid` 多集中添加一个整数，则将其值添加到 `sum` 中，以保持 `sum` 的值更新。
*   声明功能 `remove` 以从 `left`、`right` 或 `mid` 多集擦除整数。
    *   如果整数 `num` 的值小于或等于 `left` 多集的最大整数，则从 `left` 多集中查找并删除该整数，否则根据其值在 `mid` 或 `right` 多集中搜索该整数。
    *   如果移除 `num` 后，`left` 多集的大小减小，则从 `mid` 多集中删除最小整数，并将其插入到 `left` 多集中。
    *   同样，对于 `mid` 多集，如果尺寸减小，则从 `right` 多集中删除最小整数，并将其插入到 `mid` 多集中。
*   定义一个函数 `addInteger` 向当前流添加一个整数：
    *   如果当前流中的整数数量（`left`、`mid`、`right` 多集的大小之和）超过 `n`，则移除索引 `pos % n` 处的整数。
    *   调用功能 `add` 将整数插入 `left`、`mid` 或 `right` 多集，根据其值。
*   定义函数 `calculateSpecialAverage` 返回特殊平均值：
    *   如果流中的整数个数小于 `N`，则打印 `-1`。
    *   否则，将平均值打印为 `(sum / (N–2 * K))`。

**下面是上述方法的实现：**

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Special Average class
class SpecialAverage {
public:
    // Three multisets to store the
    // smaller K larger K and the
    // remaining (n-2*k) integers
    multiset<int> left, mid, right;

    int n, k;

    // Stores the index of current
    // integer in running stream of
    // integers and the sum of integers
    // in mid multiset
    long pos, sum;

    // Array to store last n integers
    vector<int> v;

    // Constructor to initialize the
    // values of n and k and initialize
    // default values
    SpecialAverage(int nvalue, int kvalue)
    {
        n = nvalue;
        k = kvalue;
        pos = 0;
        sum = 0;
        for (int i = 0; i < n; i++)
            v.push_back(0);
    }

    // Add current integer in the
    // multiset left, mid or right
    // based on its value
    void add(int num)
    {
        // Firstly, insert num in the
        // left multiset
        left.insert(num);

        // Check if size of the left
        // multiset is greater than k
        if (left.size() > k) {
```

```cpp
// Stores the value of the
// largest integer in the
// left multiset
int temp = *(prev(end(left)));

// Insert temp in the
// mid multiset
mid.insert(temp);

// Remove temp from the
// left multiset
left.erase(prev(end(left)));

// Add the value of temp
// to the current sum
sum += temp;
}

// Check if the size of mid
// multiset exceeds (n-2*k)
if (mid.size() > (n - 2 * k)) {

// Stores the value of the
// largest integer in the
// mid multiset
int temp = *(prev(end(mid)));

// Insert temp in the
// right multiset
right.insert(temp);

// Remove temp from the
// mid multiset
mid.erase(prev(end(mid)));

// Subtract the value of
// temp from current sum
sum -= temp;
}
}

// Remove integer from the
// multiset left, mid or right
// based on its value
void remove(int ele)
{

// If integer exists in the
// left multiset
if (ele <= *(left.rbegin()))
    left.erase(left.find(ele));

// If integer exists in the
// mid multiset
else if (ele <= *(mid.rbegin())) {

// Subtract the value of
// integer from current sum
sum -= ele;
mid.erase(mid.find(ele));
}

// If integer exists in the
// right multiset
else
    right.erase(right.find(ele));

// Balance all the multisets
// left, right and mid check
// if size of the left multiset
// is less than k
if (left.size() < k) {

// Stores the value of
// smallest integer
// in mid multiset
int temp = *(mid.begin());

// Insert temp in the
// left multiset
left.insert(temp);

// Remove temp from the
// mid multiset
mid.erase(mid.begin());

// Subtract the value of
// temp from current sum
sum -= temp;
}

// Check if the size of mid
// multiset becomes lesser
// than (n-2*k)
if (mid.size() < (n - 2 * k)) {

// Stores the value of
// smallest integer in
// right multiset
int temp = *(right.begin());

// Insert temp in the
// mid multiset
mid.insert(temp);

// Remove temp from the
// right multiset
right.erase(right.begin());

// Add the value of temp
// to the current sum
sum += temp;
}
}

// Function to add integer to
// the current stream
void addInteger(int num)
{

// Check if the total number
// of elements in stream > n
if (pos >= n)

// Call the function to
// remove  extra integer
    remove(v[pos % n]);

// Insert the current integer
// in array v
v[(pos++) % n] = num;

// Call the function to add
// the current integer in left,
// mid or right multiset
// based on its value
add(num);
}

// Function to calculate the
// special average
int calculateSpecialAverage()
{
// Check if the total number
// of elements is greater than
// or equal to n
if (pos >= n)

// Return desired average
    return ((double)sum) / (n - 2 * k);
return -1;
}
};

// Function to process all the queries
void processQueries(int n, int k)
{
// Create an object of the class
SpecialAverage* avg
    = new SpecialAverage(n, k);

// Add integer Query
avg->addInteger(4);
avg->addInteger(2);

// Find average Query
cout << avg->calculateSpecialAverage()
     << endl;

// Add integer Query
avg->addInteger(10);

// Find average Query
cout << avg->calculateSpecialAverage()
     << endl;
}

// Driver Code
int main()
{
int N = 3, K = 1;
processQueries(N, K);

return 0;
}
```

## Output:

```
```

### 时间复杂度:
`O(log N)` 代表 `addInteger()`，`O(1)` 代表 `calculateSpecialAverage()`

### 辅助空间:
`O(N)`