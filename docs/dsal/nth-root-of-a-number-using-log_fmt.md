# 使用对数的一个数的第 n 个根

> 原文: [https://www.geeksforgeeks.org/nth-root-of-a-number-using-log/](https://www.geeksforgeeks.org/nth-root-of-a-number-using-log/)

给定两个整数 `N` 和 `K`，任务是找到 `K` 的 `N` 次根。

**示例:**

> **输入:** `N = 3`，`K = 8`
> **输出:** `2.00`
> **说明:**
> 8 的立方根为 2。即 `2^3 = 8`
>
> **输入:** `N = 2`，`K = 16`
> **输出:** `4.00`
> **说明:**
> 16 的平方根是 4，即 `4^2 = 16`

## 方法

思路是用[对数函数](https://www.geeksforgeeks.org/log-function-cpp/)求 `K` 的 `N` 次根。

> 让 `D` 成为 `K` 的 `N` 次根，
> 然后，`N^(1/K) = D`
> 两边取以 `K` 为底的对数：
> => `log_K(N^(1/K)) = log_K(D)`
> => `(1/K) * log_K(N) = log_K(D)`
> => `D = K^((1/K) * log_K(N))`

下面是上述方法的实现：

## C++

```cpp
// C++ implementation to find the
// Kth root of a number using log

#include <bits/stdc++.h>

// Function to find the Kth root
// of the number using log function
double kthRoot(double n, int k)
{
    return pow(k,
               (1.0 / k)
                   * (log(n)
                      / log(k)));
}

// Driver Code
int main(void)
{
    double n = 81;
    int k = 4;
    printf("%lf ", kthRoot(n, k));
    return 0;
}
```

## Java

```java
// Java implementation to find the
// Kth root of a number using log
import java.util.*;

class GFG {

// Function to find the Kth root
// of the number using log function
static double kthRoot(double n, int k)
{
    return Math.pow(k, ((1.0 / k) *
                       (Math.log(n) /
                        Math.log(k))));
}

// Driver Code
public static void main(String args[])
{
    double n = 81;
    int k = 4;

    System.out.printf("%.6f", kthRoot(n, k));
}
}

// This code is contributed by rutvik_56
```

## Python 3

```python
# Python3 implementation to find the
# Kth root of a number using log

import numpy as np

# Function to find the Kth root
# of the number using log function
def kthRoot(n, k):

    return pow(k, ((1.0 / k) *
                  (np.log(n) /
                   np.log(k))))

# Driver Code
n = 81
k = 4

print("%.6f" % kthRoot(n, k))

# This code is contributed by PratikBasu
```

## C#

```csharp
// C# implementation to find the
// Kth root of a number using log
using System;

class GFG {

// Function to find the Kth root
// of the number using log function
static double kthRoot(double n, int k)
{

    return Math.Pow(k, ((1.0 / k) *
                        (Math.Log(n) /
                         Math.Log(k))));
}

// Driver Code
public static void Main(String []args)
{
    double n = 81;
    int k = 4;

    Console.Write("{0:F6}", kthRoot(n, k));
}
}

// This code is contributed by AbhiThakur
```

## JavaScript

```javascript
<script>

// Javascript implementation to find the
// Kth root of a number using log

// Function to find the Kth root
// of the number using log function
function kthRoot(n, k)
{
   return Math.pow(k, ((1.0 / k) *
                       (Math.log(n) /
                        Math.log(k))));
}

// Driver Code
var n = 81;
var k = 4;
var x = kthRoot(n, k)

document.write(x.toFixed(6));

// This code is contributed by Ankita saini

</script>
```

**输出:**

```
3.000000
```