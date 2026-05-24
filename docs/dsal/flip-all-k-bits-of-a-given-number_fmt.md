# 翻转给定数字的所有 K 位

> 原文: [https://www.geeksforgeeks.org/flip-all-k-bits-of-a-given-number/](https://www.geeksforgeeks.org/flip-all-k-bits-of-a-given-number/)

给定两个整数 `N` 和 `K`，任务是在 `K` 位中表示 `N`，并打印翻转所有位后得到的数字。

## 示例

> **输入:** `N = 1`，`K = 32`
> **输出:** `4294967294`
> **解释:**
> 1 在 `K(= 32)` 位表示为 `(00000000000000000000000000000001)₂`
> 翻转所有位将 `N` 修改为 `(11111111111111111111111111111110)₂ = (4294967294)₁₀`。
>
> **输入:** `N = 0`，`K = 32`
> **输出:** `4294967295`

## 方法

按照以下步骤解决问题:

*   求 `(1 << (K - 1)) - 1` 的值，记为 `X`。
*   最后，打印 `(X - N)` 的值。

下面是上述方法的实现:

## C++

```cpp
// C++ Program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to flip all K-bits
// of an unsigned number N
void flippingBits(unsigned long N,
                  unsigned long K)
{

    // Stores (2 ^ K) - 1
    unsigned long X = (1 << (K - 1)) - 1;

    // Update N
    N = X - N;

    // Print the answer
    cout << N;
}

// Driver Code
int main()
{
    unsigned long N = 1, K = 8;
    flippingBits(N, K);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function to flip all K-bits
// of an unsigned number N
static void flippingBits(long N,
                         long K)
{

    // Stores (2 ^ K) - 1
    long X = (1 << (K - 1)) - 1;

    // Update N
    N = X - N;

    // Print the answer
    System.out.print(N);
}

// Driver Code
public static void main(String[] args)
{
    long N = 1, K = 8;

    flippingBits(N, K);
}
}

// This code is contributed by shikhasingrajput
```

## Python 3

```python
# Python3 Program for the above approach

# Function to flip all K-bits
# of an unsigned number N
def flippingBits(N, K):

    # Stores (2 ^ K) - 1
    X = (1 << (K - 1)) - 1

    # Update N
    N = X - N

    # Print the answer
    print(N)

# Driver Code
if __name__ == '__main__':
    N, K = 1, 8
    flippingBits(N, K)

    # This code is contributed by mohit kumar 29
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to flip all K-bits
// of an unsigned number N
static void flippingBits(int N, int K)
{

    // Stores (2 ^ K) - 1
    int X = (1 << (K - 1)) - 1;

    // Update N
    N = X - N;

    // Print the answer
    Console.Write(N);
}

// Driver Code
public static void Main(string[] args)
{
    int N = 1, K = 8;

    flippingBits(N, K);
}
}

// This code is contributed by chitranayal
```

## JavaScript

```javascript
<script>

// Javascript program of the above approach

// Function to flip all K-bits
// of an unsigned number N
function flippingBits(N, K)
{

    // Stores (2 ^ K) - 1
    let X = (1 << (K - 1)) - 1;

    // Update N
    N = X - N;

    // Print the answer
    document.write(N);
}

    // Driver Code

  let N = 1, K = 8;

    flippingBits(N, K);

</script>
```

**输出:**

```
254
```

**时间复杂度:** `O(1)`
**辅助空间:** `O(1)`