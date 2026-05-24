# 按升序打印频率等于 K 次方的所有数组元素

> 原文: [https://www.geeksforgeeks.org/print-all-array-elements-having-frequencies-equal-to-powers-of-k-in-ascending-order/](https://www.geeksforgeeks.org/print-all-array-elements-having-frequencies-equal-to-powers-of-k-in-ascending-order/)

给定一个由 `N` 个整数和一个正整数 `K` 组成的数组 `arr[]`，任务是找出频率在 `K` 次方的数组元素，即 `K^1`，`K^2`，`K^3` 等等。

## 示例

**输入:** `arr[] = {1, 3, 2, 1, 2, 2, 3, 3, 4}`，`K = 2`
**输出:** `1 2`
**说明:**
- `1` 的频率为 `2`，即可以表示为 `K` 的幂(= `2`)，即 `2^1`。
- `2` 的频率为 `4`，可以表示为 `K` 的幂(= `2`)，即 `2^2`。

**输入:** `arr[] = {6, 1, 3, 1, 2, 2, 1}`，`K = 2`
**输出:** `2 3 6`

## 天真法

最简单的方法是统计每个阵元的频率，如果任意一个阵元的频率是 `K` 的完美幂，那么打印该阵元。否则，检查下一个元素。

- **时间复杂度:** `O(N^2)`
- **辅助空间:** `O(1)`

## 高效方法

上述方法也可以通过使用哈希来优化，用于将数组元素的频率存储在哈希映射中，然后检查所需的条件。按照以下步骤解决给定的问题:

1.  遍历给定的数组 `arr[]` 并将每个数组元素的频率存储在地图中，比如说 `M`。
2.  现在，遍历地图并执行以下步骤:
    - 将映射中每个值的频率存储在一个变量中，比如 `F`。
    - 如果 `(log F)/(log K)` 和 `K^((log F)/(log K))` 的值相同，那么电流元素的频率与 `K` 的完美功率相同。因此，打印当前元素。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the array elements
// whose frequency is a power of K
void countFrequency(int arr[], int N,
                    int K)
{
    // Stores the frequency of each
    // array elements
    unordered_map<int, int> freq;

    // Traverse the array
    for (int i = 0; i < N; i++) {

        // Update frequency of
        // array elements
        freq[arr[i]]++;
    }

    // Traverse the map freq
    for (auto i : freq) {

        // Calculate the log value of the
        // current frequency with base K
        int lg = log(i.second) / log(K);

        // Find the power of K of log value
        int a = pow(K, lg);

        // If the values are equal
        if (a == i.second) {

            // Print the current element
            cout << i.first << " ";
        }
    }
}

// Driver Code
int main()
{
    int arr[] = { 1, 4, 4, 2,
                  1, 2, 3, 2, 2 };
    int K = 2;
    int N = sizeof(arr) / sizeof(arr[0]);

    // Function Call
    countFrequency(arr, N, K);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;
import java.lang.*;
import java.util.*;

class GFG {

    // Function to find the array elements
    // whose frequency is a power of K
    static void countFrequency(int arr[], int N, int K)
    {

        // Stores the frequency of each
        // array elements
        HashMap<Integer, Integer> freq = new HashMap<>();

        // Traverse the array
        for (int i = 0; i < N; i++) {

            // Update frequency of
            // array elements
            freq.put(arr[i],
                     freq.getOrDefault(arr[i], 0) + 1);
        }

        // Traverse the map freq
        for (int key : freq.keySet()) {

            // Calculate the log value of the
            // current frequency with base K
            int lg = (int)(Math.log(freq.get(key))
                           / Math.log(K));

            // Find the power of K of log value
            int a = (int)(Math.pow(K, lg));

            // If the values are equal
            if (a == freq.get(key)) {

                // Print the current element
                System.out.print(key + " ");
            }
        }
    }
    // Driver Code
    public static void main(String[] args)
    {

        int arr[] = { 1, 4, 4, 2, 1, 2, 3, 2, 2 };
        int K = 2;
        int N = arr.length;

        // Function Call
        countFrequency(arr, N, K);
    }
}
```

### Python 3

```python
# Python3 program for the above approach

# Function to find the array elements
from math import log

def countFrequency(arr, N, K):

    # Stores the frequency of each
    # array elements
    freq = {}

    # Traverse the array
    for i in range(N):

        # Update frequency of
        # array elements
        if (arr[i] in freq):
            freq[arr[i]] += 1
        else:
            freq[arr[i]] = 1

    # Traverse the map freq
    for key,value in freq.items():

        # Calculate the log value of the
        # current frequency with base K
        lg = log(value) // log(K)

        # Find the power of K of log value
        a = pow(K, lg)

        # If the values are equal
        if (a == value):

            # Print the current element
            print(key, end = " ")

# Driver Code
if __name__ == '__main__':
    arr = [1, 4, 4, 2, 1, 2, 3, 2, 2]
    K = 2
    N = len(arr)

    # Function Call
    countFrequency(arr, N, K)

    # This code is contributed by bgangwar59.
```

### C\#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to find the array elements
// whose frequency is a power of K
static void countFrequency(int []arr, int N,
                           int K)
{

    // Stores the frequency of each
    // array elements
    Dictionary<int,
               int> freq = new Dictionary<int,
                                          int>();

    // Traverse the array
    for(int i = 0; i < N; i++)
    {

        // Update frequency of
        // array elements
        if (freq.ContainsKey(arr[i]))
            freq[arr[i]] += 1;
        else
            freq[arr[i]] = 1;
    }

    // Traverse the map freq
    foreach (KeyValuePair<int, int> entry in freq)
    {
        int temp = entry.Key;

        // Calculate the log value of the
        // current frequency with base K
        int lg = (int)(Math.Log(entry.Value) /
                       Math.Log(K));

        // Find the power of K of log value
        int a = (int)Math.Pow(K, lg);

        // If the values are equal
        if (a == entry.Value)
        {

            // Print the current element
            Console.Write(entry.Key + " ");
        }
    }
}

// Driver Code
public static void Main()
{
    int []arr = { 1, 4, 4, 2,
                  1, 2, 3, 2, 2 };
    int K = 2;
    int N = arr.Length;

    // Function Call
    countFrequency(arr, N, K);
}
}

// This code is contributed by SURENDRA_GANGWAR
```

# java 描述语言

### 代码示例

```javascript
<script>
    // Javascript program for the above approach

    // Function to find the array elements
    // whose frequency is a power of K
    function countFrequency(arr, N, K)
    {

        // Stores the frequency of each
        // array elements
        let freq = new Map();
        key = [3, 2, 1, 4]

        // Traverse the array
        for(let i = 0; i < N; i++)
        {

            // Update frequency of
            // array elements
            if (freq.has(arr[i]))
                freq.set(arr[i], freq.get(arr[i]) + 1);
            else
                freq.set(arr[i], 1);
        }
        let i = 0;
        freq.forEach((values,keys)=>{
            let temp = keys;

            // Calculate the log value of the
            // current frequency with base K
            let lg = parseInt(Math.log(values) /
                       Math.log(K), 10);

            // Find the power of K of log value
            let a = parseInt(Math.pow(K, lg), 10);

            // If the values are equal
            if (a == values)
            {

                // Print the current element
                document.write(key[i] + " ");
                i++;
            }
        })
    }

    let arr = [ 1, 4, 4, 2,
                  1, 2, 3, 2, 2 ];
    let K = 2;
    let N = arr.length;

    // Function Call
    countFrequency(arr, N, K);

  // This code is contributed by divyeshrabadiya07.
</script>
```

`Output:`

```
3 2 1 4
```

`时间复杂度:` O(N)
`辅助空间:` O(N)