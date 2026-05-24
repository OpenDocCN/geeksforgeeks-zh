# M 的最大可能值不超过 N，它们之间具有相等的按位“或”和“异或”运算

> 原文: [https://www.geeksforgeeks.org/largest-possible-value-of-m-not-exceeding-n-having-equal-bitwise-or-and-xor-between-them/](https://www.geeksforgeeks.org/largest-possible-value-of-m-not-exceeding-n-having-equal-bitwise-or-and-xor-between-them/)

给定一个整数 `N`，任务是找到最大的数 `M`，其中 `M < N`，使得 `N ^ M` 等于 `N | M`，即 `(N ^ M) = (N | M)`。

## 示例

**输入:** `N = 5`
**输出:** `2`
`5 ^ 4 = 1` 和 `5 | 4 = 5`。因此，它们之间的异或是 `1`，或是 `5`，不相等。
`5 ^ 3 = 6` 和 `5 | 3 = 7`。因此，它们之间的异或是 `6`，或是 `7`，不相等。
`5 ^ 2 = 7` 和 `5 | 2 = 7`。因此，它们之间的异或是 `7`，或是 `7`，相等。

**输入:** `N = 14`
**输出:** `1`

## 方法

要获得所需的数字 `M`，遍历 `N` 的所有位，从其最低有效位（LSB）到最高有效位（MSB）。这里出现两种情况：

1.  如果 `N` 的第 `i` 位为 `1`，则:
    *   如果将 `M` 的第 `i` 位设置为 `1`，则 `N ^ M` 将不等于 `N | M`，因为 `(1 ^ 1 = 0)` 和 `(1 | 1 = 1)`。
    *   如果第 `i` 位设置为 `M` 至 `0`，则 `N ^ M` 将等于 `N | M`，因为 `(1 ^ 0 = 1)` 和 `(1 | 0 = 1)`。
    *   所以如果 `N` 的第 `i` 位为 `1`，则将 `M` 的第 `i` 位设置为 `0`。
2.  如果 `N` 的第 `i` 位为 `0`，则:
    *   如果将 `M` 的第 `i` 位设置为 `1`，则 `N ^ M` 将等于 `N | M`，因为 `(0 ^ 1 = 1)` 和 `(0 | 1 = 1)`。
    *   如果我们将 `M` 的第 `i` 位设置为 `0`，那么 `N ^ M` 将等于 `N | M`，因为 `(0 ^ 0 = 0)` 和 `(0 | 0 = 0)`。
    *   因此，如果将 `M` 的第 `i` 位设置为 `0` 或 `1`，则 `N ^ M` 将始终等于 `N | M`。
    *   由于必须找出小于 `N` 的 `M` 的最大值，请始终将 `M` 的第 `i` 位设置为 `1`。

### 插图

*   `N = 5`
*   `5` 的 32 位表示 = `00000000000000000000000000000101`
*   `5` 的 LSB 指数为 `31`
*   `5` 的 MSB 指数为 `29`
*   从最低有效位到最高有效位，即从 `31` 到 `29`:
    *   对于索引 `31`，`N[31] = 1`。所以 `M[31]` 应该设为 `0`。
    *   对于索引 `30`，`N[30] = 0`。所以 `M[30]` 应该设为 `1`。
    *   对于索引 `29`，`N[29] = 1`。所以 `M[29]` 应该设为 `0`。
*   因此，`M` 的 32 位表示是 `00000000000000000000000000000010`，在十进制表示中等于 `2`。

## 实现

以下是上述方法的实现：

### C++

```cpp
// C++ Program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find required
// number M
int equalXORandOR(int n)
{
    // Initialising m
    int m = 0;

    // Finding the index of the
    // most significant bit of N
    int MSB = (int)log2(n);

    // Calculating required number
    for (int i = 0; i <= MSB; i++) {

        if (!(n & (1 << i))) {
            m += (1 << i);
        }
    }

    return m;
}

// Driver Code
int main()
{
    int n = 14;
    cout << equalXORandOR(n);
    return 0;
}
```

### Java

```java
// Java program to implement
// the above approach
class GFG{

// Function to find required
// number M
static int equalXORandOR(int n)
{

    // Initialising m
    int m = 0;

    // Finding the index of the
    // most significant bit of N
    int MSB = (int)Math.log(n);

    // Calculating required number
    for(int i = 0; i <= MSB; i++)
    {
        if ((n & (1 << i)) <= 0)
        {
            m += (1 << i);
        }
    }
    return m;
}

// Driver Code
public static void main(String[] args)
{
    int n = 14;

    System.out.print(equalXORandOR(n));
}
}

// This code is contributed by amal kumar choubey
```

### Python 3

```python
# Python3 program to implement
# the above approach
from math import log2

# Function to find required
# number M
def equalXORandOR(n):

    # Initialising m
    m = 0

    # Finding the index of the
    # most significant bit of N
    MSB = int(log2(n))

    # Calculating required number
    for i in range(MSB + 1):
        if(not(n & (1 << i))):
            m += (1 << i)

    return m

# Driver Code
n = 14

# Function call
print(equalXORandOR(n))

# This code is contributed by Shivam Singh
```

### C#

```csharp
// C# program to implement
// the above approach
using System;

class GFG{

// Function to find required
// number M
static int equalXORandOR(int n)
{

    // Initialising m
    int m = 0;

    // Finding the index of the
    // most significant bit of N
    int MSB = (int)Math.Log(n);

    // Calculating required number
    for(int i = 0; i <= MSB; i++)
    {
        if ((n & (1 << i)) <= 0)
        {
            m += (1 << i);
        }
    }
    return m;
}

// Driver Code
public static void Main(String[] args)
{
    int n = 14;

    Console.Write(equalXORandOR(n));
}
}

// This code is contributed by amal kumar choubey
```

### JavaScript

```javascript
<script>

// javascript program to implement
// the above approach
// Function to find required
// number M
function equalXORandOR(n) {

    // Initialising m
    var m = 0;

    // Finding the index of the
    // most significant bit of N
    var MSB = parseInt( Math.log(n));

    // Calculating required number
    for (i = 0; i <= MSB; i++) {
        if ((n & (1 << i)) <= 0) {
            m += (1 << i);
        }
    }
    return m;
}

// Driver Code
var n = 14;

document.write(equalXORandOR(n));

// This code contributed by Rajput-Ji

</script>
```

**输出:**

```
1
```

**时间复杂度:** `O(log2(N))`
**辅助空间:** `O(1)`