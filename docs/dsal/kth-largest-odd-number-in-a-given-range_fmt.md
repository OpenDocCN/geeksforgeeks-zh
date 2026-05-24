# 给定范围内第 k 个最大奇数

> 原文: [https://www.geeksforgeeks.org/kth-largest-odd-number-in-a-given-range/](https://www.geeksforgeeks.org/kth-largest-odd-number-in-a-given-range/)

给定两个变量 `L` 和 `R`，表示从 `L` 到 `R` 的整数范围，以及一个数字 `K`，任务是找到 `Kth` 最大奇数。如果 `K` 大于 `L` 到 `R` 范围内的奇数个数，则返回 0。

### 示例

> **输入**: `L = -10`，`R = 10`，`K = 8`
> **输出**: `-5`
> **说明**: 范围内的奇数为 -9、-7、-5、-3、-1、3、5、7、9，第八大奇数为 -5
>
> **输入**: `L = -3`，`R = 3`，`K = 1`
> **输出**: `3`

### 算法思路

给定的问题可以用数学求解。想法是检查 `R` 是奇数还是偶数，并据此计算第 k 个最大奇数。以下步骤可用于解决问题:

*   如果 `K <= 0`，则返回 0
*   初始化 `count` 计算范围内的奇数个数
*   如果 `R` 是奇数:
    *   `count` = `ceil((float)(R - L + 1) / 2)`
    *   如果 `K > count` 返回 0
    *   否则返回 `(R - 2 * K + 2)`
*   如果 `R` 是偶数:
    *   `count` = `floor((R - L + 1) / 2)`
    *   如果 `K > count` 返回 0
    *   否则返回 `(R - 2 * K + 1)`

下面是上述方法的实现:

## C++

```cpp
// C++ implementation for the above approach

#include <cmath>
#include <iostream>
using namespace std;

// Function to return Kth largest
// odd number if it exists
int kthOdd(pair<int, int> range, int K)
{

    // Base Case
    if (K <= 0)
        return 0;

    int L = range.first;
    int R = range.second;

    if (R & 1) {

        // Calculate count of odd
        // numbers within the range
        int Count = ceil((float)(R - L + 1) / 2);

        // if k > range then kth largest
        // odd number is not in the range
        if (K > Count)
            return 0;

        else
            return (R - 2 * K + 2);
    }
    else {

        // Calculate count of odd
        // numbers within the range
        int Count = (R - L + 1) / 2;

        // If k > range then kth largest
        // odd number is not in this range
        if (K > Count)
            return 0;

        else
            return (R - 2 * K + 1);
    }
}

// Driver Code
int main()
{
    // Initialize the range
    pair<int, int> p = { -10, 10 };

    // Initialize k
    int k = 8;

    // print the kth odd number
    cout << kthOdd(p, k);

    return 0;
}
```

## Java

```java
// Java implementation for the above approach
class GFG {

    // Function to return Kth largest
    // odd number if it exists
    public static int kthOdd(int[] range, int K) {

        // Base Case
        if (K <= 0)
            return 0;

        int L = range[0];
        int R = range[1];

        if ((R & 1) > 0) {

            // Calculate count of odd
            // numbers within the range
            int Count = (int) Math.ceil((R - L + 1) / 2);

            // if k > range then kth largest
            // odd number is not in the range
            if (K > Count)
                return 0;

            else
                return (R - 2 * K + 2);
        } else {

            // Calculate count of odd
            // numbers within the range
            int Count = (R - L + 1) / 2;

            // If k > range then kth largest
            // odd number is not in this range
            if (K > Count)
                return 0;

            else
                return (R - 2 * K + 1);
        }
    }

    // Driver Code
    public static void main(String args[])
    {

        // Initialize the range
        int[] p = { -10, 10 };

        // Initialize k
        int k = 8;

        // print the kth odd number
        System.out.println(kthOdd(p, k));
    }
}

// This code is contributed by gfgking.
```

## Python 3

```python
# python implementation for the above approach
import math

# Function to return Kth largest
# odd number if it exists
def kthOdd(range, K):

    # Base Case
    if (K <= 0):
        return 0

    L = range[0]
    R = range[1]

    if (R & 1):

        # Calculate count of odd
        # numbers within the range
        Count = math.ceil((R - L + 1) / 2)

        # if k > range then kth largest
        # odd number is not in the range
        if (K > Count):
            return 0

        else:
            return (R - 2 * K + 2)

    else:

        # Calculate count of odd
        # numbers within the range
        Count = (R - L + 1) // 2

        # If k > range then kth largest
        # odd number is not in this range
        if (K > Count):
            return 0

        else:
            return (R - 2 * K + 1)

# Driver Code
if __name__ == "__main__":

    # Initialize the range
    p = [-10, 10]

    # Initialize k
    k = 8

    # print the kth odd number
    print(kthOdd(p, k))

# This code is contributed by rakeshsahni
```

## C#

```csharp
// C# code for the above approach
using System;

public class GFG
{

    // Function to return Kth largest
    // odd number if it exists
    public static int kthOdd(int[] range, int K) {

        // Base Case
        if (K <= 0)
            return 0;

        int L = range[0];
        int R = range[1];

        if ((R & 1) > 0) {

            // Calculate count of odd
            // numbers within the range
            int Count = ((R - L + 1) / 2);

            // if k > range then kth largest
            // odd number is not in the range
            if (K > Count)
                return 0;

            else
                return (R - 2 * K + 2);
        } else {

            // Calculate count of odd
            // numbers within the range
            int Count = (R - L + 1) / 2;

            // If k > range then kth largest
            // odd number is not in this range
            if (K > Count)
                return 0;

            else
                return (R - 2 * K + 1);
        }
    }

    // Driver Code
    public static void Main(string[] args)
    {

        // Initialize the range
        int[] p = { -10, 10 };

        // Initialize k
        int k = 8;

        // print the kth odd number
        Console.WriteLine(kthOdd(p, k));
    }
}

// This code is contributed by sanjoy_62.
```

## JavaScript

```javascript
<script>
        // JavaScript Program to implement
        // the above approach

        // Function to return Kth largest
        // odd number if it exists
        function kthOdd(range, K) {

            // Base Case
            if (K <= 0)
                return 0;

            let L = range.first;
            let R = range.second;

            if (R & 1) {

                // Calculate count of odd
                // numbers within the range
                let Count = Math.ceil((R - L + 1) / 2);

                // if k > range then kth largest
                // odd number is not in the range
                if (K > Count)
                    return 0;

                else
                    return (R - 2 * K + 2);
            }
            else {

                // Calculate count of odd
                // numbers within the range
                let Count = (R - L + 1) / 2;

                // If k > range then kth largest
                // odd number is not in this range
                if (K > Count)
                    return 0;

                else
                    return (R - 2 * K + 1);
            }
        }

        // Driver Code

        // Initialize the range
        let p = { first: -10, second: 10 };

        // Initialize k
        let k = 8;

        // print the kth odd number
        document.write(kthOdd(p, k));

    // This code is contributed by Potta Lokesh
    </script>
```

### 输出

```
-5
```

### 时间复杂度

`O(1)`

### 辅助空间

`O(1)`