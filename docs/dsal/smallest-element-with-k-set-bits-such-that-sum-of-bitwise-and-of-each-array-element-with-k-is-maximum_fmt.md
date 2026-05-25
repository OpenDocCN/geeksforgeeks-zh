# 具有 K 个设置位的最小元素，使得每个具有 K 的数组元素的按位“与”之和最大

> 原文: [https://www.geeksforgeeks.org/smallest-element-with-k-set-bits-such-that-sum-of-bitwise-and-of-each-array-element-with-k-is-maximum/](https://www.geeksforgeeks.org/smallest-element-with-k-set-bits-such-that-sum-of-bitwise-and-of-each-array-element-with-k-is-maximum/)

给定一个由 `N` 个整数和整数 `K` 组成的数组 `arr[]`，任务是精确地用 `K` 个设置位找到最小的整数 `X`，使得 `X` 与每个数组元素 `arr[i]` 的按位 AND 之和最大。

**示例:**

> **输入:** `arr[] = {3, 4, 5, 1}`，`K = 1`
> **输出:** `4`
> **说明:** 将 `X` 的值考虑为 `4`。那么 `X` 与数组元素的按位 AND 之和 = `4&3 + 4&4 + 4&5 + 4&1 = 0 + 4 + 4 + 0 = 8`，最大。
>
> **输入:** `arr[] = {1, 3, 4, 5, 2, 5}`，`K = 2`
> **输出:** `5`

## 方法

给定的问题可以用贪婪方法解决。按照以下步骤解决问题:

*   初始化一个变量，比如 `X` 为 `0`，存储 `X` 的合成值。
*   初始化一个数组，比如说大小为 `30` 的 `cnt[]`，以在每个第 `i` 个索引处存储具有第 `i` 个位集的数组元素的数量。
*   遍历给定数组，如果第 `i` 位被设置，那么通过 `1` 更新 `cnt[i]`。
*   初始化一个 pair 的向量，比如 `v`，以存储每个位和值的贡献，即如果设置了第 `i` 位，则在 `v` 中存储值 `{i, cnt[i] * 2^i}`。
*   按照第二个元素的降序对向量对进行排序。
*   在范围 `[0, K-1]` 上遍历向量 `v`，并将 `X` 的值更新为 `X` 和 `2` 的位或 `(v[i].first)`。
*   完成以上步骤后，打印 `X` 的值作为结果。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Comparator function to sort the
// vector of pairs
bool comp(pair<int, int>& a,
          pair<int, int>& b)
{
    // If the second is not the same
    // then sort in decreasing order
    if (a.second != b.second)
        return a.second > b.second;

    // Otherwise
    return a.first < b.first;
}

// Function to find the value of X
// such that Bitwise AND of all array
// elements with X is maximum
int maximizeSum(int arr[], int n, int k)
{
    // Stores the count of set bit at
    // each position
    vector<int> cnt(30, 0);

    // Stores the resultant value of X
    int X = 0;

    // Calculate the count of set bits
    // at each position
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < 30; j++) {

            // If the jth bit is set
            if (arr[i] & (1 << j))
                cnt[j]++;
        }
    }

    // Stores the contribution
    // of each set bit
    vector<pair<int, int> > v;

    // Store all bit and amount of
    // contribution
    for (int i = 0; i < 30; i++) {

        // Find the total contribution
        int gain = cnt[i] * (1 << i);
        v.push_back({ i, gain });
    }

    // Sort v[] in decreasing
    // order of second parameter
    sort(v.begin(), v.end(), comp);

    // Choose exactly K set bits
    for (int i = 0; i < k; i++) {
        X |= (1 << v[i].first);
    }

    // Print the answer
    cout << X;
}

// Driver Code
int main()
{
    int arr[] = { 3, 4, 5, 1 };
    int K = 1;
    int N = sizeof(arr) / sizeof(arr[0]);
    maximizeSum(arr, N, K);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;
import java.lang.*;
import java.util.*;

class GFG{

    // Function to find the value of X
    // such that Bitwise AND of all array
    // elements with X is maximum
    static void maximizeSum(int arr[], int n, int k)
    {

        // Stores the count of set bit at
        // each position
        int cnt[] = new int[30];

        // Stores the resultant value of X
        int X = 0;

        // Calculate the count of set bits
        // at each position
        for(int i = 0; i < n; i++)
        {
            for(int j = 0; j < 30; j++)
            {

                // If the jth bit is set
                if ((arr[i] & (1 << j)) != 0)
                    cnt[j]++;
            }
        }

        // Stores the contribution
        // of each set bit
        ArrayList<int[]> v = new ArrayList<>();

        // Store all bit and amount of
        // contribution
        for(int i = 0; i < 30; i++)
        {

            // Find the total contribution
            int gain = cnt[i] * (1 << i);
            v.add(new int[] { i, gain });
        }

        // Sort v[] in decreasing
        // order of second parameter
        Collections.sort(v, (a, b) -> {

            // If the second is not the same
            // then sort in decreasing order
            if (a[1] != b[1])
                return b[1] - a[1];

            // Otherwise
            return a[0] - b[0];
        });

        // Choose exactly K set bits
        for(int i = 0; i < k; i++)
        {
            X |= (1 << v.get(i)[0]);
        }

        // Print the answer
        System.out.println(X);
    }

    // Driver Code
    public static void main(String[] args)
    {
        int arr[] = { 3, 4, 5, 1 };
        int K = 1;
        int N = arr.length;

        maximizeSum(arr, N, K);
    }
}

// This code is contributed by Kingash
```

### JavaScript

```javascript
<script>

// JavaScript program for the above approach

// Function to find the value of X
// such that Bitwise AND of all array
// elements with X is maximum
function maximizeSum(arr, n, k) {
    // Stores the count of set bit at
    // each position
    let cnt = new Array(30).fill(0);

    // Stores the resultant value of X
    let X = 0;

    // Calculate the count of set bits
    // at each position
    for (let i = 0; i < n; i++) {
        for (let j = 0; j < 30; j++) {

            // If the jth bit is set
            if (arr[i] & (1 << j))
                cnt[j]++;
        }
    }

    // Stores the contribution
    // of each set bit
    let v = new Array();

    // Store all bit and amount of
    // contribution
    for (let i = 0; i < 30; i++) {

        // Find the total contribution
        let gain = cnt[i] * (1 << i);
        v.push([i, gain]);
    }

    // Sort v[] in decreasing
    // order of second parameter
    v.sort((a, b) => {

        // If the second is not the same
        // then sort in decreasing order
        if (a[1] != b[1])
            return b[1] - a[1];

        // Otherwise
        return a[0] - b[0];
    });

    // Choose exactly K set bits
    for (let i = 0; i < k; i++) {
        X |= (1 << v[i][0]);
    }

    // Print the answer
    document.write(X);
}

// Driver Code

let arr = [3, 4, 5, 1];
let K = 1;
let N = arr.length;
maximizeSum(arr, N, K);

</script>
```

**输出:**

```
4
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`