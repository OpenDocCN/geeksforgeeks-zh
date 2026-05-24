# K的最大值，使得K和-K都存在于给定索引范围内的数组中[L，R]

> 原文: [https://www.geeksforgeeks.org/largest-value-of-k-such-that-both-k-and-k-exist-in-array-in-given-index-range-l-r/](https://www.geeksforgeeks.org/largest-value-of-k-such-that-both-k-and-k-exist-in-array-in-given-index-range-l-r/)

给定一个由 `N` 个整数和 `2` 个整数 `L` 和 `R` 组成的数组 `arr[]`，任务是返回大于 `0` 和 `L` 的最大整数 `K`，使得两个值 `K` 和 `-K` 都存在于数组的索引范围 `[L, R]` 内。如果没有这样的整数，则返回 `0`。

## 示例

> **输入:** `N = 5`, `arr[] = {3, 2, -2, 5, -3}`, `L = 2`, `R = 3`
> **输出:** `3`
> **解释:** 范围 `[2, 3]` 中 `K` 的最大值，使得数组中 `K` 和 `-K` 都存在，当 `arr[0]` 时为 `3`，`arr[4]` 时为 `-3`。

> **输入:** `N = 4`, `arr[] = {1, 2, 3, -4}`, `L = 1`, `R = 4`
> **输出:** `0`

## 方法

思路是遍历数组，将元素加入到集合中，同时检查其负值，即 `arr[i] * -1` 是否进入集合。如果找到，则将其推入向量 `possible[]` 中。按照以下步骤解决问题:

*   初始化一个 `unordered_set<int> s[]` 来存储元素。
*   初始化一个向量 `possible[]` 来存储可能的答案。
*   使用变量 `i` 迭代范围 `[0, N)`，并执行以下步骤:
    *   如果集合 `s[]` 中存在 `-arr[i]`，则将值 `abs(arr[i])` 推送到向量 `possible[]` 中。
    *   否则将元素 `arr[i]` 添加到集合 `s[]` 中。
*   将变量 `ans` 初始化为 `0` 来存储答案。
*   使用变量 `i` 迭代范围 `[0, size)`，其中 `size` 是向量 `possible` 的大小，并执行以下步骤:
    *   如果 `possible[i]` 大于等于 `L` 且小于等于 `R`，则更新 `ans` 的值作为 `ans` 或 `possible[i]` 的最大值。
*   执行上述步骤后，打印 `ans` 的值作为答案。

下面是上述方法的实现。

## C++14

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the maximum value of K
int findMax(int N, int arr[], int L, int R)
{

    // Using a set to store the elements
    unordered_set<int> s;

    // Vector to store the possible answers
    vector<int> possible;

    // Store the answer
    int ans = 0;

    // Traverse the array
    for (int i = 0; i < N; i++) {

        // If set has it's negation,
        // check if it is max
        if (s.find(arr[i] * -1) != s.end())
            possible.push_back(abs(arr[i]));
        else
            s.insert(arr[i]);
    }

    // Find the maximum possible answer
    for (int i = 0; i < possible.size(); i++) {
        if (possible[i] >= L and possible[i] <= R)
            ans = max(ans, possible[i]);
    }

    return ans;
}

// Driver Code
int main()
{

    int arr[] = { 3, 2, -2, 5, -3 },
        N = 5, L = 2, R = 3;

    int max = findMax(N, arr, L, R);

    // Display the output
    cout << max << endl;

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.*;

public class GFG
{

// Function to find the maximum value of K
static int findMax(int N, int []arr, int L, int R)
{

    // Using a set to store the elements
    HashSet<Integer> s = new HashSet<Integer>();

    // ArrayList to store the possible answers
    ArrayList<Integer> possible
            = new ArrayList<Integer>();

    // Store the answer
    int ans = 0;

    // Traverse the array
    for (int i = 0; i < N; i++) {

        // If set has it's negation,
        // check if it is max
        if (s.contains(arr[i] * -1))
            possible.add(Math.abs(arr[i]));
        else
            s.add(arr[i]);
    }

    // Find the maximum possible answer
    for (int i = 0; i < possible.size(); i++) {
        if (possible.get(i) >= L && possible.get(i) <= R) {
            ans = Math.max(ans, possible.get(i));
        }
    }

    return ans;
}

// Driver Code
public static void main(String args[])
{

    int []arr = { 3, 2, -2, 5, -3 };
    int N = 5, L = 2, R = 3;

    int max = findMax(N, arr, L, R);

    // Display the output
    System.out.println(max);

}
}

// This code is contributed by Samim Hossain Mondal.
```

## Python 3

```python
# Python3 program for the above approach

# Function to find the maximum value of K
def findMax(N, arr, L, R) :

    # Using a set to store the elements
    s = set();

    # Vector to store the possible answers
    possible = [];

    # Store the answer
    ans = 0;

    # Traverse the array
    for i in range(N) :

        # If set has it's negation,
        # check if it is max
        if arr[i] * -1 in s  :
            possible.append(abs(arr[i]));
        else :
            s.add(arr[i]);

    # Find the maximum possible answer
    for i in range(len(possible)) :
        if (possible[i] >= L and possible[i] <= R) :
            ans = max(ans, possible[i]);

    return ans;

# Driver Code
if __name__ ==  "__main__" :

    arr = [ 3, 2, -2, 5, -3 ];
    N = 5; L = 2; R = 3;

    Max = findMax(N, arr, L, R);

    # Display the output
    print(Max);

    # This code is contributed by Ankthon
```

## C#

```csharp
// C# program for the above approach
using System;
using System.Collections;
using System.Collections.Generic;

public class GFG
{
// Function to find the maximum value of K
static int findMax(int N, int []arr, int L, int R)
{

    // Using a set to store the elements
    HashSet<int> s = new HashSet<int>();

    // ArrayList to store the possible answers
    ArrayList possible = new ArrayList();

    // Store the answer
    int ans = 0;

    // Traverse the array
    for (int i = 0; i < N; i++) {

        // If set has it's negation,
        // check if it is max
        if (s.Contains(arr[i] * -1))
            possible.Add(Math.Abs(arr[i]));
        else
            s.Add(arr[i]);
    }

    // Find the maximum possible answer
    for (int i = 0; i < possible.Count; i++) {
        if ((int)possible[i] >= L && (int)possible[i] <= R) {
            ans = Math.Max(ans, (int)possible[i]);
        }
    }

    return ans;
}

// Driver Code
public static void Main()
{

    int []arr = { 3, 2, -2, 5, -3 };
    int N = 5, L = 2, R = 3;

    int max = findMax(N, arr, L, R);

    // Display the output
    Console.Write(max);;

}
}

// This code is contributed by Samim Hossain Mondal.
```

## JavaScript

```javascript
<script>

        // JavaScript Program to implement
        // the above approach

        // Function to find the maximum value of K
        function findMax(N, arr, L, R) {

            // Using a set to store the elements
            let s = new Set();

            // Vector to store the possible answers
            let possible = [];

            // Store the answer
            let ans = 0;

            // Traverse the array
            for (let i = 0; i < N; i++) {

                // If set has it's negation,
                // check if it is max
                if (s.has(arr[i] * -1))
                    possible.push(Math.abs(arr[i]));
                else
                    s.add(arr[i]);
            }

            // Find the maximum possible answer
            for (let i = 0; i < possible.length; i++) {
                if (possible[i] >= L && possible[i] <= R)
                    ans = Math.max(ans, possible[i]);
            }

            return ans;
        }

        // Driver Code
        let arr = [3, 2, -2, 5, -3];
        let N = 5, L = 2, R = 3;

        let max = findMax(N, arr, L, R);

        // Display the output
        document.write(max + '<br');

    // This code is contributed by Potta Lokesh
    </script>
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(N)`