# 求长度为 L 的神奇串对的个数

> 原文: [https://www.geeksforgeeks.org/find-number-of-magical-pairs-of-string-of-length-l/](https://www.geeksforgeeks.org/find-number-of-magical-pairs-of-string-of-length-l/)

一对弦 `s` 和 `r` 如果每个指标 `i` 的 `s` 的字符小于 `r` ，即 `s[i]<r[i]`，则称之为神奇。任务是计算长度为 `L` 的可能字符串对的数量。由于该值可以很大，所以以 `10^9` 为模给出答案。

**注意**:字符串只包含小写英文字母。

**示例:**

> **输入:** `L = 1`
> **输出:** `325`
> 因为需要的字符串长度是 1。
> 如果 `s =“a”`，那么 `r` 可以是“b”、“c”、“d”、…“z”(25 种可能性)
> 如果 `s =“b”`，那么 `r` 可以是“c”、“d”、“e”、…“z”(24 种可能性)
> …。
> 如果 `s =“y”`，那么 `r` 只能是“z”(1 种可能性)
> `s` 不能是“z”，因为它是最大小写字符。
> 因此总的可能性是 1 + 2 + 3 + … + 25 = 325
>
> **输入:** `L = 2`
> **输出:** `105625`

**进场:** 对于 `L = 1` ，总可能性为 `325` 。对于 `L = 2` ，总可能性为 `325^2` 。任何数值 `L` 的总可能性为 `325^L` 。由于该值可能很大，打印答案时取模 `10^9` 。

下面是上述方法的实现:

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Iterative Function to calculate (x^y)%p in O(log y)
int power(int x, unsigned int y, int p)
{

    // Initialize result
    int res = 1;

    // Update x if it is >= p
    x = x % p;

    while (y > 0) {

        // If y is odd, multiply x with result
        if (y & 1)
            res = (res * x) % p;

        // Y must be even now
        y = y >> 1; // y = y/2
        x = (x * x) % p;
    }
    return res;
}

// Driver Code
int main()
{

    int L = 2, P = pow(10, 9);

    int ans = power(325, L, P);

    cout << ans << "\n";

    return 0;
}
```

## Java

```java
// Java implementation of the approach

class GFG
{

    // Iterative Function to calculate (x^y)%p in O(log y)
    static int power(int x, int y, int p)
    {

        // Initialize result
        int res = 1;

        // Update x if it is >= p
        x = x % p;

        while (y > 0)
        {

            // If y is odd, multiply x with result
            if (y % 2 == 1)
            {
                res = (res * x) % p;
            }

            // Y must be even now
            y = y >> 1; // y = y/2
            x = (x * x) % p;
        }
        return res;
    }

    // Driver Code
    public static void main(String[] args)
    {
        int L = 2;
        int P = (int) Math.pow(10, 9);

        int ans = power(325, L, P);
        System.out.println(ans);
    }
}

// This code has been contributed by 29AjayKumar
```

## Python

```python
# Python implementation of the approach

# Iterative Function to calculate (x^y)%p in O(log y)
def power(x, y, p):

    # Initialize result
    res = 1;

    # Update x if it is >= p
    x = x % p;

    while (y > 0):

        # If y is odd, multiply x with result
        if (y %2== 1):
            res = (res * x) % p;

        # Y must be even now
        y = y >> 1; # y = y/2
        x = (x * x) % p;
    return res;

# Driver Code
L = 2; P = pow(10, 9);
ans = power(325, L, P);
print(ans);

#  This code contributed by Rajput-Ji
```

## C#

```csharp
// C# implementation of the approach
using System;

class GFG
{

    // Iterative Function to calculate (x^y)%p in O(log y)
    static int power(int x, int y, int p)
    {

        // Initialize result
        int res = 1;

        // Update x if it is >= p
        x = x % p;

        while (y > 0)
        {

            // If y is odd, multiply x with result
            if (y % 2 == 1)
            {
                res = (res * x) % p;
            }

            // Y must be even now
            y = y >> 1; // y = y/2
            x = (x * x) % p;
        }
        return res;
    }

    // Driver Code
    public static void Main()
    {
        int L = 2;
        int P = (int) Math.Pow(10, 9);

        int ans = power(325, L, P);
        Console.WriteLine(ans);
    }
}

// This code is contributed by AnkitRai01
```

## PHP

```php
<?php
// PHP implementation of the approach

// Iterative Function to calculate (x^y)%p in O(log y)
function power($x, $y, $p)
{

    // Initialize result
    $res = 1;

    // Update x if it is >= p
    $x = $x % $p;

    while ($y > 0)
    {

        // If y is odd, multiply x with result
        if ($y & 1)
            $res = ($res * $x) % $p;

        // Y must be even now
        $y = $y >> 1; // y = y/2
        $x = ($x * $x) % $p;
    }
    return $res;
}

// Driver Code

$L = 2;
$P = pow(10, 9);

$ans = power(325, $L, $P);

echo $ans , "\n";

// This code is contributed by ajit.
?>
```

## JavaScript

```javascript
<script>
    // Javascript implementation of the approach

    // Iterative Function to calculate (x^y)%p in O(log y)
    function power(x, y, p)
    {

        // Initialize result
        let res = 1;

        // Update x if it is >= p
        x = x % p;

        while (y > 0)
        {

            // If y is odd, multiply x with result
            if (y % 2 == 1)
            {
                res = (res * x) % p;
            }

            // Y must be even now
            y = y >> 1; // y = y/2
            x = (x * x) % p;
        }
        return res;
    }

    let L = 2;
    let P = Math.pow(10, 9);

    let ans = power(325, L, P);
    document.write(ans);

</script>
```

**Output:**

```
105625
```