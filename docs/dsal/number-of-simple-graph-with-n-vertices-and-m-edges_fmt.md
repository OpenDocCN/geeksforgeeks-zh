# 具有 N 个顶点和 M 条边的简单图的数量

> 原文: [https://www.geeksforgeeks.org/number-of-simple-graph-with-n-vertices-and-m-edges/](https://www.geeksforgeeks.org/number-of-simple-graph-with-n-vertices-and-m-edges/)

给定两个整数 `N` 和 `M`，任务是统计可以用 `N` 个顶点和 `M` 条边绘制的简单无向图的数量。简单图是不包含多条边和自循环的图。

## 示例

> **输入:** `N = 3`，`M = 1`
> **输出:** 3
> 这 3 个图分别是 `{1-2，3}`、`{2-3，1}`、`{1-3，2}`。
>
> **输入:** `N = 5`，`M = 1`
> **输出:** 10

## 方法

从 `1` 到 `N` 对 `N` 个顶点进行编号。由于没有自循环或多条边，边必须出现在两个不同的顶点之间。所以我们可以选择两个不同顶点的方式数是 `^N C_2`，等于 `(N * (N - 1)) / 2`。假设是 `P`。
现在 `M` 条边必须和这几对顶点一起使用，所以在 `P` 对之间选择 `M` 对顶点的方式数将是 `P C_M`。
如果 `P < M` 那么答案将是 `0`，因为多余的边不能单独留下。

下面是上述方法的实现：

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the value of
// Binomial Coefficient C(n, k)
int binomialCoeff(int n, int k)
{

    if (k > n)
        return 0;

    int res = 1;

    // Since C(n, k) = C(n, n-k)
    if (k > n - k)
        k = n - k;

    // Calculate the value of
    // [n * (n - 1) *---* (n - k + 1)] / [k * (k - 1) * ... * 1]
    for (int i = 0; i < k; ++i) {
        res *= (n - i);
        res /= (i + 1);
    }

    return res;
}

// Driver Code
int main()
{
    int N = 5, M = 1;

    int P = (N * (N - 1)) / 2;

    cout << binomialCoeff(P, M);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
class GFG
{

    // Function to return the value of
    // Binomial Coefficient C(n, k)
    static int binomialCoeff(int n, int k)
    {

        if (k > n)
            return 0;

        int res = 1;

        // Since C(n, k) = C(n, n-k)
        if (k > n - k)
            k = n - k;

        // Calculate the value of
        // [n * (n - 1) *---* (n - k + 1)] /
        // [k * (k - 1) * ... * 1]
        for (int i = 0; i < k; ++i)
        {
            res *= (n - i);
            res /= (i + 1);
        }
        return res;
    }

// Driver Code
public static void main(String[] args)
{
    int N = 5, M = 1;
    int P = (N * (N - 1)) / 2;

    System.out.println(binomialCoeff(P, M));
}
}

// This code is contributed by Shivi_Aggarwal
```

## Python 3

```python
# Python 3 implementation of the approach

# Function to return the value of
# Binomial Coefficient C(n, k)
def binomialCoeff(n, k):

    if (k > n):
        return 0

    res = 1

    # Since C(n, k) = C(n, n-k)
    if (k > n - k):
        k = n - k

    # Calculate the value of
    # [n * (n - 1) *---* (n - k + 1)] /
    # [k * (k - 1) * ... * 1]
    for i in range( k):
        res *= (n - i)
        res //= (i + 1)

    return res

# Driver Code
if __name__=="__main__":

    N = 5
    M = 1

    P = (N * (N - 1)) // 2

    print(binomialCoeff(P, M))

# This code is contributed by ita_c
```

## C#

```csharp
// C# implementation of the approach
using System;

class GFG
{
// Function to return the value of
// Binomial Coefficient C(n, k)
static int binomialCoeff(int n, int k)
{

    if (k > n)
        return 0;

    int res = 1;

    // Since C(n, k) = C(n, n-k)
    if (k > n - k)
        k = n - k;

    // Calculate the value of
    // [n * (n - 1) *---* (n - k + 1)] /
    // [k * (k - 1) * ... * 1]
    for (int i = 0; i < k; ++i)
    {
        res *= (n - i);
        res /= (i + 1);
    }

    return res;
}

// Driver Code
public static void Main()
{
    int N = 5, M = 1;

    int P = (N * (N - 1)) / 2;

    Console.Write(binomialCoeff(P, M));
}
}

// This code is contributed
// by Akanksha Rai
```

## PHP

```php
<?php
// PHP implementation of the approach

// Function to return the value of
// Binomial Coefficient C(n, k)
function binomialCoeff($n, $k)
{
    if ($k > $n)
        return 0;

    $res = 1;

    // Since C(n, k) = C(n, n-k)
    if ($k > $n - $k)
        $k = $n - $k;

    // Calculate the value of
    // [n * (n - 1) *---* (n - k + 1)] /
    // [k * (k - 1) * ... * 1]
    for ($i = 0; $i < $k; ++$i)
    {
        $res *= ($n - $i);
        $res /= ($i + 1);
    }

    return $res;
}

// Driver Code
$N = 5;
$M = 1;

$P = floor(($N * ($N - 1)) / 2);

echo binomialCoeff($P, $M);

// This code is contributed by Ryuga
?>
```

## JavaScript

```javascript
<script>

// Javascript implementation of the approach

// Function to return the value of
// Binomial Coefficient C(n, k)
function binomialCoeff(n, k)
{

    if (k > n)
        return 0;

    var res = 1;

    // Since C(n, k) = C(n, n-k)
    if (k > n - k)
        k = n - k;

    // Calculate the value of
    // [n * (n - 1) *---* (n - k + 1)] / [k * (k - 1) * ... * 1]
    for (var i = 0; i < k; ++i) {
        res *= (n - i);
        res /= (i + 1);
    }

    return res;
}

// Driver Code
var N = 5, M = 1;
var P = (N * (N - 1)) / 2;
document.write( binomialCoeff(P, M));

</script>
```

**Output:**

```