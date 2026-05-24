# 找出给定范围内某一对的最大可能 GCD

> 原文: [https://www.geeksforgeeks.org/find-the-maximum-gcd-possible-for-some-pair-in-a-given-range-l-r/](https://www.geeksforgeeks.org/find-the-maximum-gcd-possible-for-some-pair-in-a-given-range-l-r/)

给定范围 `L` 到 `R`，任务是找到 `GCD(X, Y)` 的最大可能值，使得 `X` 和 `Y` 属于给定范围，即 `L ≤ X < Y ≤ R`。

**示例:**

> **输入:** `L = 101`, `R = 139`
> **输出:**
> 34
> **说明:**
> 对于 `X = 102` 和 `Y = 136`，`X` 和 `Y` 的 GCD 为 34，这是最大可能。
>
> **输入:** `L = 8`, `R = 14`
> **输出:** 7

## 天真方法

从 `L` 到 `R` 的每一对都可以使用两个嵌套循环进行迭代，可以找到最大值 `GCD`。

**时间复杂度:** `O((R-L)^2 Log(R))`
**辅助空间:** `O(1)`

## 高效方法

按照以下步骤解决问题:

*   让最大 `GCD` 为 `Z`，因此，`X` 和 `Y` 都是 `Z` 的倍数。相反，如果在段 `[L, R]` 中有两个或两个以上的 `Z` 倍数，则可以选择 `(X, Y)`，通过选择 `[L, R]` 中 `Z` 的连续倍数，使 `GCD(x, y)` 最大。
*   从 `R` 到 `1` 迭代，找出其中是否有任何一个在 `[L, R]` 范围内至少有两个倍数。
*   `L` 和 `R` 之间的 `Z` 的倍数可以用以下公式计算:
    *   `Z 在[L，R]中的倍数 = Z 在[1，R]中的倍数 – Z 在[1，L-1]中的倍数`
    *   这可以写成:
        *   `Z 在[L，R]中的倍数 = floor(R/Z) – floor((L-1)/Z)`

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to calculate GCD
int GCD(int a, int b)
{
    if (b == 0)
        return a;
    return GCD(b, a % b);
}

// Function to calculate
// maximum GCD in a range
int maxGCDInRange(int L, int R)
{
    // Variable to store the answer
    int ans = 1;

    for (int Z = R; Z >= 1; Z--) {

        // If Z has two multiples in [L, R]
        if ((R / Z) - (L - 1) / Z > 1) {

            // Update ans
            ans = Z;
            break;
        }
    }

    // Return the value
    return ans;
}
// Driver code
int main()
{
    // Input
    int L = 102;
    int R = 139;

    // Function Call
    cout << maxGCDInRange(L, R);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;

class GFG {
    // Function to calculate GCD
    public static int GCD(int a, int b)
    {
        if (b == 0)
            return a;
        return GCD(b, a % b);
    }

    // Function to calculate
    // maximum GCD in a range
    public static int maxGCDInRange(int L, int R)
    {
        // Variable to store the answer
        int ans = 1;

        for (int Z = R; Z >= 1; Z--) {

            // If Z has two multiples in [L, R]
            if ((R / Z) - (L - 1) / Z > 1) {

                // Update ans
                ans = Z;
                break;
            }
        }

        // Return the value
        return ans;
    }

  // Driver code
    public static void main(String[] args)
    {
        // Input
        int L = 102;
        int R = 139;

        // Function Call
        System.out.println(maxGCDInRange(L, R));
    }

   // This code is contributed by Potta Lokesh
}
```

### Python 3

```python
# Python3 program for the above approach

# Function to calculate GCD
def GCD(a, b):

    if (b == 0):
        return a

    return GCD(b, a % b)

# Function to calculate
# maximum GCD in a range
def maxGCDInRange(L, R):

    # Variable to store the answer
    ans = 1

    for Z in range(R, 1, -1):

        # If Z has two multiples in [L, R]
        if (((R // Z) - (L - 1) // Z ) > 1):

            # Update ans
            ans = Z
            break

    # Return the value
    return ans

# Driver code

# Input
L = 102
R = 139

# Function Call
print(maxGCDInRange(L, R))

# This code is contributed by SoumikMondal
```

### C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to calculate GCD
public static int GCD(int a, int b)
{
    if (b == 0)
        return a;

    return GCD(b, a % b);
}

// Function to calculate
// maximum GCD in a range
public static int maxGCDInRange(int L, int R)
{

    // Variable to store the answer
    int ans = 1;

    for(int Z = R; Z >= 1; Z--)
    {

        // If Z has two multiples in [L, R]
        if ((R / Z) - (L - 1) / Z > 1)
        {

            // Update ans
            ans = Z;
            break;
        }
    }

    // Return the value
    return ans;
}

// Driver code
public static void Main()
{

    // Input
    int L = 102;
    int R = 139;

    // Function Call
    Console.Write(maxGCDInRange(L, R));
}
}

// This code is contributed by rishavmahato348
```

### JavaScript

```javascript
<script>

// JavaScript program for the above approach

// Function to calculate GCD
function GCD( a, b)
{
    if (b == 0)
        return a;
    return GCD(b, a % b);
}

// Function to calculate
// maximum GCD in a range
function maxGCDInRange(L, R)
{

    // Variable to store the answer
    let ans = 1;

    for (let Z = R; Z >= 1; Z--)
    {

        // If Z has two multiples in [L, R]
        if (parseInt((R / Z)) - parseInt((L - 1) / Z )> 1)
        {

            // Update ans
            ans = Z;
            break;
        }
    }

    // Return the value
    return ans;
}

// Driver code

// Input
let L = 102;
let R = 139;

// Function Call
document.write(maxGCDInRange(L, R));

// This code is contributed by Potta Lokesh

</script>
```

**Output**

```
34
```

**时间复杂度:** `O(R)`
**辅助空间:** `O(1)`