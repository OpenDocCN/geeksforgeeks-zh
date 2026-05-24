# 给定和与乘积值时可能的最小数组大小

> 原文: [https://www.geeksforgeeks.org/minimum-size-of-array-possible-with-given-sum-and-product-values/](https://www.geeksforgeeks.org/minimum-size-of-array-possible-with-given-sum-and-product-values/)

给定两个正整数 `S` 和 `P`，任务是找到数组的最小可能大小，使得元素之和为 `S`，元素之积为 `P`。如果不存在这样的数组，则打印 `-1`。

## 示例

> **输入:** `S = 5`，`P = 6`
> **输出:** `2`
> **说明:** 有效数组可以是 `{2, 3}`，为最小大小。
>
> **输入:** `S = 5`，`P = 100`
> **输出:** `-1`

## 方法

给定的问题可以基于以下观察来解决：

*   使用 `N` 个数字，可以形成具有和 `S` 的尺寸 `N` 的数组。
*   当 `P` 的值在 `[0, (S/N)^N]` 之间时，可以实现任何乘积值。

按照以下步骤解决给定的问题：

*   首先检查 `S` 和 `P` 的值是否相同，然后返回 `1`，因为 `S` 值本身用于制作最小尺寸数组。
*   使用变量 `i` 迭代范围 `[2, S]`，如果 `(S/i) >= pow(P, 1/i)` 的值成立，则打印 `i` 的值作为形成的数组的最终最小大小。
*   完成上述步骤后，如果没有满足上述条件的可能值 `i`，则打印 `-1`。

下面是上述方法的实现：

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the minimum size
// of array with sum S and product P
int minimumSizeArray(int S, int P)
{
    // Base Case
    if (S == P) {

        return 1;
    }

    // Iterate through all values of S
    // and check the mentioned condition
    for (int i = 2; i <= S; i++) {

        double d = i;
        if ((S / d) >= pow(P, 1.0 / d)) {
            return i;
        }
    }

    // Otherwise, print "-1"
    return -1;
}

// Driver Code
int main()
{
    int S = 5, P = 6;
    cout << minimumSizeArray(S, P);

    return 0;
}
```

### Java

```java
// Java program for the above approach
class GFG{

// Function to find the minimum size
// of array with sum S and product P
static int minimumSizeArray(int S, int P)
{
    // Base Case
    if (S == P) {

        return 1;
    }

    // Iterate through all values of S
    // and check the mentioned condition
    for (int i = 2; i <= S; i++) {

        double d = i;
        if ((S / d) >= Math.pow(P, 1.0 / d)) {
            return i;
        }
    }

    // Otherwise, print "-1"
    return -1;
}

// Driver Code
public static void main(String args[])
{
    int S = 5, P = 6;
       System.out.println(minimumSizeArray(S, P));
}
}

// This code is contributed by AnkThon
```

### Python 3

```python
# python program for the above approach

# Function to find the minimum size
# of array with sum S and product P
def minimumSizeArray(S, P):

    # Base Case
    if (S == P):
        return 1

    # Iterate through all values of S
    # and check the mentioned condition
    for i in range(2, S+1):

        d = i
        if ((S / d) >= pow(P, 1.0 / d)):
            return i

    # Otherwise, print "-1"
    return -1

# Driver Code
if __name__ == "__main__":
    S = 5
    P = 6
    print(minimumSizeArray(S, P))

    # This code is contributed by rakeshsahni
```

### C#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to find the minimum size
// of array with sum S and product P
static int minimumSizeArray(int S, int P)
{
    // Base Case
    if (S == P) {

        return 1;
    }

    // Iterate through all values of S
    // and check the mentioned condition
    for (int i = 2; i <= S; i++) {

        double d = i;
        if ((S / d) >= Math.Pow(P, 1.0 / d)) {
            return i;
        }
    }

    // Otherwise, print "-1"
    return -1;
}

// Driver Code
public static void Main()
{
    int S = 5, P = 6;
    Console.Write(minimumSizeArray(S, P));
}
}

// This code is contributed by SURENDRA_GANGWAR.
```

### JavaScript

```javascript
<script>
        // JavaScript Program to implement
        // the above approach

        // Function to find the minimum size
        // of array with sum S and product P
        function minimumSizeArray(S, P)
        {

            // Base Case
            if (S == P) {

                return 1;
            }

            // Iterate through all values of S
            // and check the mentioned condition
            for (let i = 2; i <= S; i++) {

                let d = i;
                if ((S / d) >= Math.pow(P, 1.0 / d)) {
                    return i;
                }
            }

            // Otherwise, print "-1"
            return -1;
        }

        // Driver Code
        let S = 5, P = 6;
        document.write(minimumSizeArray(S, P));

// This code is contributed by Potta Lokesh
    </script>
```

**输出:**

```
2
```

**时间复杂度:** `O(log P)`
**辅助空间:** `O(1)`