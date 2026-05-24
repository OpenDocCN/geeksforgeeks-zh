# 在 R 个不同的组中分配 N 个相同对象的方式数

> 原文：[https://www.geeksforgeeks.org/number-of-ways-of-distributing-n-identical-objects-in-r-distinct-groups/](https://www.geeksforgeeks.org/number-of-ways-of-distributing-n-identical-objects-in-r-distinct-groups/)

给定两个整数 `N` 和 `R`，任务是计算将 `N` 个相同的对象分配到 `R` 个不同的组中的方法数量。

## 示例

**输入：** `N = 4`，`R = 2`
**输出：** 5
第一组对象数量= 0，第二组对象数量= 4
第一组对象数量= 1，第二组对象数量= 3
第一组对象数量= 2，第二组对象数量= 2
第一组对象数量= 3，第二组对象数量= 1
第一组对象数量= 4，第二组对象数量= 0

**输入：** `N = 4`，`R = 3`
**输出：** 15

## 方法

思路是用[多项式定理](https://en.wikipedia.org/wiki/Multinomial_theorem)。让我们假设 `x1` 物体被放置在第一组中，`x2` 物体被放置在第二组中，`xR` 物体被放置在第 `R` 组中。给出了，
`x1 + x2 + x3 + … + xR = N`
该方程的多项式定理解由 `C(N + R - 1, R - 1)` 给出。

下面是上述方法的实现：

## C++

```cpp
// C++ implementation of the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the
// value of ncr effectively
int ncr(int n, int r)
{

    // Initialize the answer
    int ans = 1;

    for (int i = 1; i <= r; i += 1)
    {
        // Divide simultaneously by
        // i to avoid overflow
        ans *= (n - r + i);
        ans /= i;
    }
    return ans;
}

// Function to return the number of
// ways to distribute N identical
// objects in R distinct objects
int NoOfDistributions(int N, int R)
{
    return ncr(N + R - 1, R - 1);
}

// Driver code
int main()
{
    int N = 4, R = 3;

    // Function call
    cout << NoOfDistributions(N, R);

    return 0;
}
```

## Java

```java
// Java implementation of the above approach
import java.util.*;

class GFG {

    // Function to return the
    // value of ncr effectively
    static int ncr(int n, int r)
    {

        // Initialize the answer
        int ans = 1;

        for (int i = 1; i <= r; i += 1)
        {
            // Divide simultaneously by
            // i to avoid overflow
            ans *= (n - r + i);
            ans /= i;
        }
        return ans;
    }

    // Function to return the number of
    // ways to distribute N identical
    // objects in R distinct objects
    static int NoOfDistributions(int N, int R)
    {
        return ncr(N + R - 1, R - 1);
    }

    // Driver code
    public static void main(String[] args)
    {
        int N = 4, R = 3;

        // Function call
        System.out.println(NoOfDistributions(N, R));
    }
}

// This code is contributed by Princi Singh
```

## Python 3

```python
# Python3 implementation of the above approach

# Function to return the
# value of ncr effectively
def ncr(n, r):

    # Initialize the answer
    ans = 1

    for i in range(1, r+1):

        # Divide simultaneously by
        # i to avoid overflow
        ans *= (n - r + i)
        ans //= i

    return ans

# Function to return the number of
# ways to distribute N identical
# objects in R distinct objects
def NoOfDistributions(N, R):

    return ncr(N + R-1, R - 1)

# Driver code
N = 4
R = 3

# Function call
print(NoOfDistributions(N, R))

# This code is contributed by mohit kumar 29
```

## C#

```csharp
// C# implementation of the above approach
using System;

class GFG {

    // Function to return the
    // value of ncr effectively
    static int ncr(int n, int r)
    {

        // Initialize the answer
        int ans = 1;

        for (int i = 1; i <= r; i += 1)
        {
            // Divide simultaneously by
            // i to avoid overflow
            ans *= (n - r + i);
            ans /= i;
        }
        return ans;
    }

    // Function to return the number of
    // ways to distribute N identical
    // objects in R distinct objects
    static int NoOfDistributions(int N, int R)
    {
        return ncr(N + R - 1, R - 1);
    }

    // Driver code
    static public void Main()
    {
        int N = 4, R = 3;

        // Function call
        Console.WriteLine(NoOfDistributions(N, R));
    }
}

// This code is contributed by AnkitRai01
```

## JavaScript

```javascript
<script>

// Javascript implementation of the above approach

// Function to return the
// value of ncr effectively
function ncr(n, r)
{

    // Initialize the answer
    let ans = 1;

    for(let i = 1; i <= r; i += 1)
    {

        // Divide simultaneously by
        // i to avoid overflow
        ans *= (n - r + i);
        ans = parseInt(ans / i);
    }
    return ans;
}

// Function to return the number of
// ways to distribute N identical
// objects in R distinct objects
function NoOfDistributions(N, R)
{
    return ncr(N + R - 1, R - 1);
}

// Driver code
let N = 4, R = 3;

// Function call
document.write(NoOfDistributions(N, R));

// This code is contributed by subhammahato348

</script>
```

## 输出

```
15
```

**时间复杂度：** `O(R)`