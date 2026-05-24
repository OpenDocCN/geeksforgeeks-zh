# 程序寻找一个数与一个梅森数的乘积

> 原文：[https://www.geeksforgeeks.org/program-to-find-the-product-of-a-number-with-a-mersenne-number/](https://www.geeksforgeeks.org/program-to-find-the-product-of-a-number-with-a-mersenne-number/)

给定一个整数 `N` 和一个[梅森数](https://en.wikipedia.org/wiki/Mersenne_prime) `M`，任务是在不使用 `*` 运算符的情况下打印它们的乘积。
**注：** 梅森数是那些比 2 的幂小一的数。

**示例：**

> **输入：** `N = 4`，`M = 15`
> **输出：** `60`
>
> **输入：** `N = 9`，`M = 31`
> **输出：** `279`

**方法：** 给定的问题可以基于以下观察来解决：

> 假设 `M` 可以表示为 `2^X – 1`，那么 `N` 与 `M` 的乘积可以表示为 `N * 2^X – N`。

因此，任意梅森数与任意数 `N` 的乘积可以表示为 `(N << log2(M + 1)) – N`。

下面是上述方法的实现：

## C++

```cpp
// C++ implementation of above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find product of a
// Mersenne number with another number
long multiplyByMersenne(long N, long M)
{
    // Stores the power of
    // 2 of integer M + 1
    long x = log2(M + 1);

    // Return the product
    return ((N << x) - N);
}

// Driver Code
int main()
{
    long N = 4;
    long M = 15;

    cout << multiplyByMersenne(N, M);

    return 0;
}
```

## Java

```java
// Java program to implement
// the above approach
import java.io.*;
import java.util.*;
class GFG
{

// Function to find product of a
// Mersenne number with another number
static long multiplyByMersenne(long N, long M)
{

    // Stores the power of
    // 2 of integer M + 1
    long x = (int)(Math.log(M + 1) / Math.log(2));

    // Return the product
    return ((N << x) - N);
}

// Driver Code
public static void main(String[] args)
{
    long N = 4;
    long M = 15;

    System.out.print(multiplyByMersenne(N, M));
}
}

// This code is contributed by souravghosh0416.
```

## Python 3

```python
# Python3 program for the above approach
import math

# Function to find product of a
# Mersenne number with another number
def multiplyByMersenne(N, M) :

    # Stores the power of
    # 2 of integer M + 1
    x = int(math.log2(M + 1))

    # Return the product
    return ((N << x) - N)

# Driver Code
N = 4
M = 15

print(multiplyByMersenne(N, M))

# This code is contributed by sanjoy_62.
```

## C#

```csharp
// C# program for the above approach
using System;
class GFG{

  // Function to find product of a
  // Mersenne number with another number
  static int multiplyByMersenne(int N, int M)
  {

    // Stores the power of
    // 2 of integer M + 1
    int x = (int)(Math.Log(M + 1) / Math.Log(2));

    // Return the product
    return ((N << x) - N);
  }

  // Driver Code
  static public void Main()
  {
    int N = 4;
    int M = 15;

    Console.Write(multiplyByMersenne(N, M));
  }
}

// This code is contributed by splevel62.
```

## JavaScript

```javascript
<script>

// Javascript implementation of above approach

// Function to find product of a
// Mersenne number with another number
function multiplyByMersenne(N, M)
{

    // Stores the power of
    // 2 of integer M + 1
    let x = (Math.log(M + 1) / Math.log(2));

    // Return the product
    return ((N << x) - N);
}

// Driver code
let N = 4;
let M = 15;

document.write(multiplyByMersenne(N, M));

// This code is contributed by target_2

</script>
```

**输出：**

```
60
```

**时间复杂度：** `O(1)`
**辅助空间：** `O(1)`