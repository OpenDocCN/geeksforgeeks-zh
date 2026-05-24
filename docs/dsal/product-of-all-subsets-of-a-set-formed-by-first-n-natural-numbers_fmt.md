# 由前 N 个自然数构成的集合的所有子集的乘积

> 原文: [https://www.geeksforgeeks.org/product-of-all-subsets-of-a-set-formed-by-first-n-natural-numbers/](https://www.geeksforgeeks.org/product-of-all-subsets-of-a-set-formed-by-first-n-natural-numbers/)

给定一个数 `N`，任务是从由前 `N` 个自然数组成的集合的所有可能子集中找到所有元素的乘积。

**例:**

> **输入:** `N = 2`
> **输出:** 4
> 可能的子集有 `{1}`、`{2}`、`{1, 2}`。
> 子集内元素的乘积= `{1}` * `{2}` * `{1 * 2}` = 4
>
> **输入:** `N = 3`
> **输出:** 1296
> 可能的子集有 `{1}`、`{2}`、`{3}`、`{1, 2}`、`{1, 3}`、`{2, 3}`、`{1, 2, 3}`
> 子集内元素的乘积= 1 * 2 * 3 * (1 * 2) * (1 * 3) * (2 * 3) * (1 * 2 * 3) = 1296

**天真方法:** 一个简单的解决方案是[生成前 N 个自然数的所有子集](https://www.geeksforgeeks.org/power-set/)。然后对于每个子集，计算它的乘积，最后返回每个子集的总乘积。

**高效方法:**

*   可以观察到，原始数组的每个元素在所有子集中出现 `2^(N–1)` 次。
*   因此最终答案中任何元素 `arr[i]` 的贡献都将是 `i * 2^(N – 1)`。
*   所以，所有子集的乘积将是 `1^(2^(N-1)) * 2^(2^(N-1)) * 3^(2^(N-1)) * ... * N^(2^(N-1))`。

以下是上述方法的实现:

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the product of all elements
// in all subsets in natural numbers from 1 to N
int product(int N)
{
    int ans = 1;
    int val = pow(2, N - 1);

    for (int i = 1; i <= N; i++) {
        ans *= pow(i, val);
    }

    return ans;
}

// Driver Code
int main()
{
    int N = 2;

    cout << product(N);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
class GFG {

    // Function to find the product of all elements
    // in all subsets in natural numbers from 1 to N
    static int product(int N)
    {
        int ans = 1;
        int val = (int)Math.pow(2, N - 1);

        for (int i = 1; i <= N; i++) {
            ans *= (int)Math.pow(i, val);
        }

        return ans;
    }

    // Driver Code
    public static void main (String[] args)
    {
        int N = 2;

        System.out.println(product(N));
    }
}

// This code is contributed by AnkitRai01
```

## Python 3

```python
# Python3 implementation of the approach

# Function to find the product of all elements
# in all subsets in natural numbers from 1 to N
def product(N) :
    ans = 1;
    val = 2 **(N - 1);

    for i in range(1, N + 1) :
        ans *= (i**val);

    return ans;

# Driver Code
if __name__ == "__main__" :

    N = 2;

    print(product(N));

# This code is contributed by AnkitRai01
```

## C#

```csharp
// C# implementation of the approach
using System;

class GFG {

    // Function to find the product of all elements
    // in all subsets in natural numbers from 1 to N
    static int product(int N)
    {
        int ans = 1;
        int val = (int)Math.Pow(2, N - 1);

        for (int i = 1; i <= N; i++) {
            ans *= (int)Math.Pow(i, val);
        }

        return ans;
    }

    // Driver Code
    public static void Main (string[] args)
    {
        int N = 2;

        Console.WriteLine(product(N));
    }
}

// This code is contributed by AnkitRai01
```

## JavaScript

```javascript
<script>
// javascript implementation of the approach

// Function to find the product of all elements
// in all subsets in natural numbers from 1 to N
function product( N)
{
    let ans = 1;
    let val = Math.pow(2, N - 1);
    for (let i = 1; i <= N; i++)
    {
        ans *= Math.pow(i, val);
    }
    return ans;
}

// Driver Code

    let N = 2;
    document.write(product(N));

// This code is contributed by todaysgaurav

</script>
```

**输出:**

```
4
```

**时间复杂度:** `O(N*logN)`

**辅助空间:** `O(1)`