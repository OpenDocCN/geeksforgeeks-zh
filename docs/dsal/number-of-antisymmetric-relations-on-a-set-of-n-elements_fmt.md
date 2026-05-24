# 一组 N 个元素上反对称关系的个数

> 原文: [https://www.geeksforgeeks.org/number-of-antisymmetric-relations-on-a-set-of-n-elements/](https://www.geeksforgeeks.org/number-of-antisymmetric-relations-on-a-set-of-n-elements/)

给定一个正整数 `N`，任务是在给定的一组 `N` 元素上找到**反对称关系**的个数。由于关系数可以很大，所以打印出来模 `10^9 + 7`。

> 集合 `A` 上的关系 `R` 称为**反对称**当且仅当 `(a, b) ∈ R` 和 `(b, a) ∈ R`，则 `a = b`。称为反对称，即关系 `R = {(a, b) | a ≤ b}` 为反对称，因为 `a ≤ b`。

## 示例

> **输入:** `N = 2`
> **输出:** 12
> **解释:** 考虑集合 `{a, b}`，所有可能的反对称关系为:
> `{}`、`{(a, b)}`、`{(b, a)}`、`{(a, a), (a, b)}`、`{(a, a), (b, a)}`、`{(b, b), (a, b)}`、`{(b, b), (b, a)}`、`{(a, a)}`、`{(b, b)}`、`{(a, a), (b, b)}`、`{(a, a), (b, b), (a, b)}`、`{(a, a), (b, b), (b, a)}`。
>
> **输入:** `N = 5`
> **输出:** 1889568

## 方法

给定的问题可以基于以下观察来解决:

*   考虑到一个反对称关系 `R` 在集合 `S` 上，对于任意两个不同的元素 `a` 和 `b`（即 `a ≠ b`），有序对 `(a, b)` 和 `(b, a)` 中最多只能有一个属于关系 `R`。它可能包含有序对之一，也可能不包含有序对。
*   所有对都有 `3` 种可能的选择。
*   因此，这些选择的所有组合的计数等于 `3^{(N * (N - 1)) / 2}`。
*   形式 `(a, a)` 的成对子集数等于 `2^N`。

因此，可能反对称关系的总数等于 `2^N * 3^{(N * (N - 1)) / 2}`。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach
#include <iostream>
using namespace std;

const int mod = 1000000007;

// Function to calculate the
// value of x ^ y % mod in O(log y)
int power(long long x, unsigned int y)
{
    // Stores the result of x^y
    int res = 1;

    // Update x if it exceeds mod
    x = x % mod;

    while (y > 0) {

        // If y is odd, then
        // multiply x with result
        if (y & 1)
            res = (res * x) % mod;

        // Divide y by 2
        y = y >> 1;

        // Update the value of x
        x = (x * x) % mod;
    }

    // Return the resultant
    // value of x^y
    return res;
}

// Function to count the number of
// antisymmetric relations in a set
// consisting of N elements
int antisymmetricRelation(int N)
{

    // Print the count of
    // antisymmetric relations
    return (power(2, N) * 1LL * power(3, (N * N - N) / 2)) % mod;
}

// Driver Code
int main()
{
    int N = 2;
    cout << antisymmetricRelation(N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

static int mod = 1000000007;

// Function to calculate the
// value of x ^ y % mod in O(log y)
static int power(int x, int y)
{

    // Stores the result of x^y
    int res = 1;

    // Update x if it exceeds mod
    x = x % mod;

    while (y > 0)
    {

        // If y is odd, then
        // multiply x with result
        if ((y & 1) != 0)
            res = (res * x) % mod;

        // Divide y by 2
        y = y >> 1;

        // Update the value of x
        x = (x * x) % mod;
    }

    // Return the resultant
    // value of x^y
    return res;
}

// Function to count the number of
// antisymmetric relations in a set
// consisting of N elements
static int antisymmetricRelation(int N)
{

    // Print the count of
    // antisymmetric relations
    return (power(2, N) *
            power(3, (N * N - N) / 2)) % mod;
}

// Driver Code
public static void main(String []args)
{
    int N = 2;

    System.out.print(antisymmetricRelation(N));
}
}

// This code is contributed by ipg2016107
```

### Python 3

```python
# Python3 program for the above approach
mod = 1000000007

# Function to calculate the
# value of x ^ y % mod in O(log y)
def power(x, y):

    # Stores the result of x^y
    res = 1

    # Update x if it exceeds mod
    x = x % mod

    while (y > 0):

        # If y is odd, then
        # multiply x with result
        if (y & 1):
            res = (res * x) % mod

        # Divide y by 2
        y = y >> 1

        # Update the value of x
        x = (x * x) % mod

    # Return the resultant
    # value of x^y
    return res

# Function to count the number of
# antisymmetric relations in a set
# consisting of N elements
def antisymmetricRelation(N):

    # Print the count of
    # antisymmetric relations
    return (power(2, N) *
            power(3, (N * N - N) // 2)) % mod

# Driver Code
if __name__ == "__main__":

    N = 2

    print(antisymmetricRelation(N))

# This code is contributed by ukasp
```

### C#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;

class GFG{

static int mod = 1000000007;

// Function to calculate the
// value of x ^ y % mod in O(log y)
static int power(int x, int y)
{

    // Stores the result of x^y
    int res = 1;

    // Update x if it exceeds mod
    x = x % mod;

    while (y > 0)
    {

        // If y is odd, then
        // multiply x with result
        if ((y & 1)>0)
            res = (res * x) % mod;

        // Divide y by 2
        y = y >> 1;

        // Update the value of x
        x = (x * x) % mod;
    }

    // Return the resultant
    // value of x^y
    return res;
}

// Function to count the number of
// antisymmetric relations in a set
// consisting of N elements
static int antisymmetricRelation(int N)
{

    // Print the count of
    // antisymmetric relations
    return (power(2, N) *
            power(3, (N * N - N) / 2)) % mod;
}

// Driver Code
public static void Main()
{
    int N = 2;

    Console.Write(antisymmetricRelation(N));
}
}

// This code is contributed by SURENDRA_GANGWAR
```

### JavaScript

```javascript
<script>

// Javascript program for the above approach

var mod = 1000000007;

// Function to calculate the
// value of x ^ y % mod in O(log y)
function power(x, y)
{
    // Stores the result of x^y
    var res = 1;

    // Update x if it exceeds mod
    x = x % mod;

    while (y > 0) {

        // If y is odd, then
        // multiply x with result
        if (y & 1)
            res = (res * x) % mod;

        // Divide y by 2
        y = y >> 1;

        // Update the value of x
        x = (x * x) % mod;
    }

    // Return the resultant
    // value of x^y
    return res;
}

// Function to count the number of
// antisymmetric relations in a set
// consisting of N elements
function antisymmetricRelation(N)
{

    // Print the count of
    // antisymmetric relations
    return (power(2, N) * power(3, (N * N - N) / 2)) % mod;
}

// Driver Code
var N = 2;
document.write( antisymmetricRelation(N));

</script>
```

**输出:**

```
12
```

**时间复杂度:** `O(log N)`
**辅助空间:** `O(1)`