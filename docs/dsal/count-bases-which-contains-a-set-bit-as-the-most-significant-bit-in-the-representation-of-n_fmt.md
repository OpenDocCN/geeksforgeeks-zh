# 计数包含一个设定位作为最高有效位的基数

> 原文: [https://www.geeksforgeeks.org/count-bases-which-contains-a-set-bit-as-the-most-significant-bit-in-the-representation-of-n/](https://www.geeksforgeeks.org/count-bases-which-contains-a-set-bit-as-the-most-significant-bit-in-the-representation-of-n/)

给定一个正整数 `N`，任务是统计不同基数的数量，其中当 `N` 被表示时，`N` 的[最高有效位](https://www.geeksforgeeks.org/find-significant-set-bit-number/)被发现是一个设定位。

## 示例

**输入:** `N = 6`
**输出:** 4
**说明:** 数字 6 可以用 5 个不同的基数表示，即基数 2、基数 3、基数 4、基数 5、基数 6。
1.  `(6)₁₀` 在基数 2: `(110)₂`
2.  `(6)₁₀` 在基数 3: `(20)₃`
3.  `(6)₁₀` 在基数 4: `(12)₄`
4.  `(6)₁₀` 在基数 5: `(11)₅`
5.  `(6)₁₀` 在基数 6: `(10)₆`

`(6)₁₀` 在基数 2、基数 4、基数 5、基数 6 中的表示以 1 开始。因此，所需的基数数量是 4。

**输入:** `N = 5`
**输出:** 4

## 方法

给定的问题可以通过为每个可能的基数找到给定数量 `N` 的 [MSB](https://www.geeksforgeeks.org/find-significant-set-bit-number/) 来解决，并且将那些 `MSB` 为 1 的基数进行计数。按照以下步骤解决问题:
*   初始化一个变量，比如 `count` 为 0，存储需要的结果。
*   [使用变量迭代范围](https://www.geeksforgeeks.org/range-based-loop-c/) `[2, N]`，比如 `B`，并执行以下步骤:
    *   将表示数字 `N` 所需的[基数 `B` 的最高幂](https://www.geeksforgeeks.org/largest-n-digit-number-in-base-b/)存储在变量 `P` 中。这可以很容易地通过找到 `log N` 到基数 `B` 的值，即 `log_B(N)` 截断到最近的整数来实现。
    *   要找到 `log_B(N)` 的值，请使用 log 属性: `log_B(N) = log(N) / log(B)`
    *   通过将 `N` 除以 `(B)^P`，存储 `N` 的最高有效位。如果等于 1，则将 `count` 的值增加 1。
*   完成上述步骤后，打印 `count` 的值作为结果。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to count bases
// having MSB of N as a set bit
int countOfBase(int N)
{
    // Store the required count
    int count = 0;

    // Iterate over the range [2, N]
    for (int i = 2; i <= N; ++i) {

        int highestPower
            = (int)(log(N) / log(i));

        // Store the MSB of N
        int firstDigit = N / (int)pow(
                                 i, highestPower);

        // If MSB is 1, then increment
        // the count by 1
        if (firstDigit == 1) {
            ++count;
        }
    }

    // Return the count
    return count;
}

// Driver Code
int main()
{
    int N = 6;
    cout << countOfBase(N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;
class GFG {

    public static int countOfBase(int N)
    {
        // Store the required count
        int count = 0;

        // Iterate over the range [2, N]
        for (int i = 2; i <= N; ++i) {

            int highestPower
                = (int)(Math.log(N) / Math.log(i));

            // Store the MSB of N
            int firstDigit = N / (int)Math.pow(
                                     i, highestPower);

            // If MSB is 1, then increment
            // the count by 1
            if (firstDigit == 1) {
                ++count;
            }
        }

        // Return the count
        return count;
    }

    // DRIVER CODE
    public static void main (String[] args)
    {
        int N = 6;
        System.out.println(countOfBase(N));
    }
}

// This code is contributed by Potta Lokesh
```

### C#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to count bases
// having MSB of N as a set bit
static int countOfBase(int N)
{
    // Store the required count
    int count = 0;

    // Iterate over the range [2, N]
    for(int i = 2; i <= N; ++i)
    {
        int highestPower = (int)(Math.Log(N) /
                                 Math.Log(i));

        // Store the MSB of N
        int firstDigit = N / (int)Math.Pow(
                                 i, highestPower);

        // If MSB is 1, then increment
        // the count by 1
        if (firstDigit == 1)
        {
            ++count;
        }
    }

    // Return the count
    return count;
}

// Driver Code
public static void Main()
{
    int N = 6;
    Console.Write(countOfBase(N));
}
}

// This code is contributed by ipg2016107
```

### JavaScript

```javascript
// JavaScript implementation of the approach
function countOfBase(N)
{
    // Store the required count
    let count = 0;

    // Iterate over the range [2, N]
    for (let i = 2; i <= N; ++i) {

        let highestPower
            = parseInt(Math.log(N) / Math.log(i));

        // Store the MSB of N
        let firstDigit = parseInt(N / Math.pow(
            i, highestPower));

        // If MSB is 1, then increment
        // the count by 1
        if (firstDigit == 1) {
            ++count;
        }
    }

    // Return the count
    return count;
}

// Driver code
let N = 6;
document.write(countOfBase(N))

// This code is contributed by Potta Lokesh
```

### Python

```python
# Python 3 program for the above approach
import math

# Function to count bases
# having MSB of N as a set bit
def countOfBase(N) :
    # Store the required count
    count = 0

    # Iterate over the range [2, N]
    for i in range(2, N+1):
        highestPower = int(math.log(N) / math.log(i))

        # Store the MSB of N
        firstDigit = int(N / int(math.pow(i, highestPower)))

        # If MSB is 1, then increment
        # the count by 1
        if (firstDigit == 1) :
            count += 1

    # Return the count
    return count

# Driver Code
N = 6
print(countOfBase(N))
```

**输出:**

```
4
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`