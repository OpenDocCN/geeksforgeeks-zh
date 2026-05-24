# 给定数组中第 K 个最小对和

> 原文: [https://www.geeksforgeeks.org/k-th-smallest-pair-sum-in-given-array/](https://www.geeksforgeeks.org/k-th-smallest-pair-sum-in-given-array/)

给定一个整数数组 `arr[]` 大小 `N` 和一个整数 `K`，任务是找到给定数组的第 `K` 个最小对和。

## 示例

> **输入:** `arr[] = {1, 5, 6, 3, 2}`，`K = 3`
> **输出:** 5
> **解释:** 所有对的和为: 1+5 = 6，1+6 = 7，1+3 = 4，1+2 = 3，5+6 = 11，5+3 = 8，5+2 = 7，6+3 = 9，6+2 = 8，2+3 = 5。第三小的是 5。
>
> **输入:** `arr[] = {2, 4, 5, 6}`，`K = 6`
> **输出:** 11

## 天真方法

这是一个贪婪方法。我们将得到所有可能对的和，并将它们存储在一个数组中。然后，我们将按升序对该数组进行排序，第 `K` 个值是必需的答案。

**时间复杂度:** O(N<sup>2</sup> * log(N<sup>2</sup>))
**辅助空间:** O(N<sup>2</sup>)

## 高效方法

该方法的概念基于最大堆。我们将实现大小为 `k` 的最大堆。遵循下面提到的步骤:

*   从 `i = 0` 到 `i = N-2` 开始迭代数组。
    *   对于每个 `i`，从 `j = i+1` 迭代到 `j = N-1`。
    *   获取该 `(i, j)` 对的和并将其插入最大堆中。
    *   如果堆满了，则将堆的顶元素与之和进行比较。
    *   如果顶元素的值大于，则用新的总和替换。
*   当迭代结束时，最大堆的最顶层元素是第 `K` 个最小对和。

下面是上述方法的实现:

## C++

```cpp
#include <bits/stdc++.h>
using namespace std;

// Function to get the Kth smallest pair sum
int kthPairSum(vector<int>& arr, int K)
{
    int n = arr.size();

    // Priority queue to implement max-heap
    priority_queue<int> pq;

    // Loop to calculate all possible pair sum
    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {

            // Variable to store the sum
            int temp = arr[i] + arr[j];

            // If the heap is full
            if (pq.size() == K) {

                // If the top element is greater
                if (pq.top() > temp) {
                    pq.pop();
                    pq.push(temp);
                }
            }
            else
                pq.push(temp);
        }
    }

    // Return the Kth smallest value
    return pq.top();
}

// Driver code
int main()
{
    vector<int> arr = { 1, 5, 6, 3, 2 };
    int K = 3;

    cout << kthPairSum(arr, K);
    return 0;
}
```

## Java

```java
// Java code for the above approach
import java.util.*;
class GFG {

    // Function to get the Kth smallest pair sum
    static int kthPairSum(int[] arr, int K)
    {
        int n = arr.length;

        // Priority queue to implement max-heap
        // Creating empty priority queue
        PriorityQueue<Integer> pq
            = new PriorityQueue<Integer>(
                Collections.reverseOrder());

        // Loop to calculate all possible pair sum
        for (int i = 0; i < n - 1; i++) {
            for (int j = i + 1; j < n; j++) {

                // Variable to store the sum
                int temp = arr[i] + arr[j];

                // If the heap is full
                if (pq.size() == K) {

                    // If the top element is greater
                    if (pq.peek() > temp) {
                        pq.poll();
                        pq.add(temp);
                    }
                }
                else
                    pq.add(temp);
            }
        }

        // Return the Kth smallest value
        return pq.peek();
    }

    // Driver code
    public static void main(String[] args)
    {
        int[] arr = { 1, 5, 6, 3, 2 };
        int K = 3;

        System.out.println(kthPairSum(arr, K));
    }
}

// This code is contributed by Potta Lokesh
```

## Python 3

```python
from queue import PriorityQueue

# Function to get the Kth smallest pair sum
def kthPairSum(arr, K):
    n = len(arr);

    # Priority queue to implement max-heap
    pq = PriorityQueue()

    # Loop to calculate all possible pair sum
    for i in range(n - 1):
        for j in range(i + 1, n):

            # Variable to store the sum
            temp = arr[i] + arr[j];

            # If the heap is full
            if (pq.qsize() == K):

                # If the top element is greater
                if (pq.queue[-1] > temp):
                    pq.get();
                    pq.put(temp);
            else:
                pq.put(temp);

    # Return the Kth smallest value
    return pq.queue[0];

# Driver code
arr = [ 1, 5, 6, 3, 2 ];
K = 3;

print(kthPairSum(arr, K));

# This code is contributed by saurabh_jaiswal.
```

**输出**

```
5
```

**时间复杂度:** O(N<sup>2</sup> * logK)
**辅助空间:** O(K)