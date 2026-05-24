# 最大 N 数，其模与 X 等于 Y 模 X

> 原文：[https://www.geeksforgeeks.org/largest-number-up-to-n-whose-modulus-with-x-is-equal-to-y-modulo-x/](https://www.geeksforgeeks.org/largest-number-up-to-n-whose-modulus-with-x-is-equal-to-y-modulo-x/)

## 问题描述

给定三个正整数 `X`、`Y` 和 `N`，使得 `Y < X`，任务是从范围 `[0, N]` 中找出最大的数，其与 `X` 的模等于 `Y` 模 `X`。

**示例：**

> **输入：** `X = 10`，`Y = 5`，`N = 15`
> **输出：** `15`
> **说明：**
> `15 % 10`（= 5）和 `5 % 10`（= 5）的值相等。
> 因此，要求的输出是 `15`。

> **输入：** `X = 5`，`Y = 0`，`N = 4`
> **输出：** `0`

## 方法

给定的问题可以基于以下观察来解决：

*   既然 `Y` 小于 `X`，那么 `Y % X` 一定是 `Y`。因此，问题转化为在范围 `[0, N]` 内寻找最大值，其与 `X` 的模数为 `Y`。
*   假设最大数值为 `num = N`，计算其以 `X` 为模的余数。
*   用 `N % X` 的余数减去 `N` 得到余数为 `0` 的数，再加上 `Y`。然后，该数字与 `X` 的模数将是 `Y`。
*   检查该数字是否小于等于 `N`。如果为真，则设置 `num = (N - N % X + Y)`。
*   否则，再次用 `X` 的值减去该数，即 `num = (N - N % X - (X - Y))`，以得到区间 `[0, N]` 内的最大值。
*   数学上：
    *   如果 `(N - N % X + Y) <= N`，则设置 `num = (N - N % X + Y)`。
    *   否则，更新 `num = (N - N % X - (X - Y))`。

### 算法步骤

按照以下步骤解决问题：

1.  初始化一个变量，比如 `num`，以存储范围 `[0, N]` 内模 `X` 余数为 `Y` 的最大值。
2.  如果 `(N - N % X + Y) <= N`，则更新 `num = (N - N % X + Y)`。
3.  否则，更新 `num = (N - N % X - (X - Y))`。
4.  完成以上步骤后，打印 `num` 的值作为结果。

## 代码实现

下面是上述方法的实现：

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print the largest
// number upto N whose modulus
// with X is same as Y % X
long long maximumNum(long long X,
                     long long Y,
                     long long N)
{
    // Stores the required number
    long long num = 0;

    // Update num as the result
    if (N - N % X + Y <= N) {

        num = N - N % X + Y;
    }
    else {
        num = N - N % X - (X - Y);
    }

    // Return the resultant number
    return num;
}

// Driver Code
int main()
{
    long long X = 10;
    long long Y = 5;
    long long N = 15;

    cout << maximumNum(X, Y, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;
import java.lang.*;
import java.util.*;

class GFG
{

  // Function to print the largest
  // number upto N whose modulus
  // with X is same as Y % X
  static long maximumNum(long X, long Y, long N)
  {

    // Stores the required number
    long num = 0;

    // Update num as the result
    if (N - N % X + Y <= N)
    {
      num = N - N % X + Y;
    }
    else
    {
      num = N - N % X - (X - Y);
    }

    // Return the resultant number
    return num;
  }

  // Driver Code
  public static void main(String[] args)
  {

    long X = 10;
    long Y = 5;
    long N = 15;

    System.out.println(maximumNum(X, Y, N));
  }
}

// This code is contributed by Kingash.
```

### Python 3

```python
# Python3 program for the above approach

# Function to print the largest
# number upto N whose modulus
# with X is same as Y % X
def maximumNum(X, Y, N):

    # Stores the required number
    num = 0

    # Update num as the result
    if (N - N % X + Y <= N):
        num = N - N % X + Y
    else:
        num = N - N % X - (X - Y)

    # Return the resultant number
    return num

# Driver Code
if __name__ == '__main__':
    X = 10
    Y = 5
    N = 15

    print (maximumNum(X, Y, N))

# This code is contributed by mohit kumar 29.
```

### C#

```csharp
// C# program for the above approach
using System;
class GFG {

  // Function to print the largest
  // number upto N whose modulus
  // with X is same as Y % X
  static long maximumNum(long X, long Y, long N)
  {

    // Stores the required number
    long num = 0;

    // Update num as the result
    if (N - N % X + Y <= N) {
      num = N - N % X + Y;
    }
    else {
      num = N - N % X - (X - Y);
    }

    // Return the resultant number
    return num;
  }

  // Driver Code
  public static void Main(string[] args)
  {

    long X = 10;
    long Y = 5;
    long N = 15;

    Console.WriteLine(maximumNum(X, Y, N));
  }
}

// This code is contributed by ukasp.
```

### JavaScript

```javascript
<script>

// Javascript program for the above approach

// Function to print the largest
// number upto N whose modulus
// with X is same as Y % X
function maximumNum(X, Y, N)
{

    // Stores the required number
    let num = 0;

    // Update num as the result
    if (N - N % X + Y <= N)
    {
        num = N - N % X + Y;
    }
    else
    {
        num = N - N % X - (X - Y);
    }

    // Return the resultant number
    return num;
}

// Driver code
let X = 10;
let Y = 5;
let N = 15;

document.write(maximumNum(X, Y, N));

// This code is contributed by target_2

</script>
```

**输出：**

```
15
```

**时间复杂度：** `O(1)`
**辅助空间：** `O(1)`