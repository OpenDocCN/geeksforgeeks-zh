# 范围[L，R]

内所有 `I` 的 `I * countDigits(I)^2` 之和

> 原文: [https://www.geeksforgeeks.org/sum-of-i-countdigitsi2-for-all-i-in-range-l-r/](https://www.geeksforgeeks.org/sum-of-i-countdigitsi2-for-all-i-in-range-l-r/)

给定一个范围 `[L，R]`，任务是找出所有 `I∈[L，R]` 的和 `I * countDigits(I)^2`，其中 `countDigits(i)` 是 `i` 中的位数。
即查找:
`L * countDigits(L)^2+(L+1)* countDigits(L+1)^2+…..+ R * countDigits(R)^2`。

**例:**

> **输入:** `L = 8`，`R = 11`
> **输出:** `101`
> `8 * 1^2+9 * 1^2+10 * 2^2+11 * 2^2= 8+9+40+44 = 101`
> **输入:** `L = 98`，`R = 102`
> **输出:** `3515`
> `98 * 2^2+99 * 2^2+100 * 3^2+101 * 3^2+102 * 3^2= 3515`

### 进场

我们把段 `[L，R]` 分解成几段相同位数的数字。
`[1–9]`、`[10–99]`、`[100–999]`、`[1000–9999]`、`[10000–99999]`、`[100000–999999]`、`[1000000–9999999]` 等等。
当 `L` 和 `R` 长度相同时，所需的总和将为 `countDigits(L)^2*(L+R)*(R–L+1)/2`。

**证明:**

> 让 `[L，R]=[10，14]`，其中 `L` 和 `R` 长度相同，即 2。
> 因此该段 `[L，R]` 之和为 `10 * 2^2+11 * 2^2+12 * 2^2+13 * 2^2+14 * 2^2`。
> 取 `2^2` 为公因子，`2^2*(10+11+12+13+14)=` **位数^2 * (AP 之和)**
> 之和 `AP =(项数/ 2) *(第一项+最后一项)` 即 `(R–L+1)*(L+R)/2`。

以下是上述方法的实现:

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;
#define MOD 1000000007

// Function to return the required sum
int rangeSum(int l, int r)
{

    int a = 1, b = 9, res = 0;
    for (int i = 1; i <= 10; i++) {
        int L = max(l, a);
        int R = min(r, b);

        // If range is valid
        if (L <= R) {

            // Sum of AP
            int sum = (L + R) * (R - L + 1) / 2;
            res += (i * i) * (sum % MOD);
            res %= MOD;
        }
        a = a * 10;
        b = b * 10 + 9;
    }
    return res;
}

// Driver code
int main()
{
    int l = 98, r = 102;
    cout << rangeSum(l, r);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
class GFG {

    static final int MOD = 1000000007;

    // Function to return the required sum
    static int rangeSum(int l, int r)
    {

        int a = 1, b = 9, res = 0;
        for (int i = 1; i <= 10; i++) {
            int L = Math.max(l, a);
            int R = Math.min(r, b);

            // If range is valid
            if (L <= R) {

                // Sum of AP
                int sum = (L + R) * (R - L + 1) / 2;
                res += (i * i) * (sum % MOD);
                res %= MOD;
            }
            a = a * 10;
            b = b * 10 + 9;
        }
        return res;
    }

    // Driver code
    public static void main(String args[])
    {

        int l = 98, r = 102;
        System.out.print(rangeSum(l, r));
    }
}
```

## Python 3

```python
# Python3 implementation of the approach

MOD = 1000000007;

# Function to return the required sum
def rangeSum(l, r) :

    a = 1; b = 9; res = 0;
    for i in range(1, 11) :
        L = max(l, a);
        R = min(r, b);

        # If range is valid
        if (L <= R) :

            # Sum of AP
            sum = (L + R) * (R - L + 1) // 2;
            res += (i * i) * (sum % MOD);
            res %= MOD;

        a *= 10;
        b = b * 10 + 9;

    return res;

# Driver code
if __name__ == "__main__" :

    l = 98 ; r = 102;

    print(rangeSum(l, r));

# This code is contributed by Ryuga
```

## C#

```csharp
// C# implementation of the approach
using System;
class GFG {

    const int MOD = 1000000007;

    // Function to return the required sum
    static int rangeSum(int l, int r)
    {

        int a = 1, b = 9, res = 0;
        for (int i = 1; i <= 10; i++) {
            int L = Math.Max(l, a);
            int R = Math.Min(r, b);

            // If range is valid
            if (L <= R) {

                // Sum of AP
                int sum = (L + R) * (R - L + 1) / 2;
                res += (i * i) * (sum % MOD);
                res %= MOD;
            }
            a = a * 10;
            b = b * 10 + 9;
        }
        return res;
    }

    // Driver code
    public static void Main()
    {
        int l = 98, r = 102;
        Console.WriteLine(rangeSum(l, r));
    }
}
```

## PHP

```php
<?php
// PHP implementation of the approach

$MOD = 1000000007;

// Function to return the required sum
function rangeSum($l, $r)
{
    global $MOD;
    $a = 1; $b = 9; $res = 0;
    for ($i = 1; $i <= 10; $i++)
    {
        $L = max($l, $a);
        $R = min($r, $b);

        // If range is valid
        if ($L <= $R)
        {

            // Sum of AP
            $sum = ($L + $R) * ($R - $L + 1) / 2;
            $res += ($i * $i) * ($sum % $MOD);
            $res %= $MOD;
        }
        $a = $a * 10;
        $b = $b * 10 + 9;
    }
    return $res;
}

// Driver code
$l = 98; $r = 102;
echo rangeSum($l, $r);

// This code is contributed
// by Akanksha Rai
?>
```

## JavaScript

```javascript
<script>
// Javascript implementation of the approach
MOD=1000000007

// Function to return the required sum
function rangeSum(l, r)
{

    var a = 1, b = 9, res = 0;
    for (var i = 1; i <= 10; i++) {
        var L = Math.max(l, a);
        var R = Math.min(r, b);

        // If range is valid
        if (L <= R) {

            // Sum of AP
            var sum = (L + R) * (R - L + 1) / 2;
            res += (i * i) * (sum % MOD);
            res %= MOD;
        }
        a = a * 10;
        b = b * 10 + 9;
    }
    return res;
}

// Driver code
var l = 98, r = 102;
document.write(rangeSum(l, r));

// This code is contributed by noob2000.
</script>
```

**Output:**

```
3515
```