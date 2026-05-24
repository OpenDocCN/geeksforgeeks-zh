# 计算配对数(A <= N，B <= N)，使得gcd(A，B)为B

> 原文:[https://www.geeksforgeeks.org/count-number-pairs-n-b-n-gcd-b-b/](https://www.geeksforgeeks.org/count-number-pairs-n-b-n-gcd-b-b/)

给定一个数`n`。我们需要找到`a`和`b`的有序对的个数，这样`gcd(a, b)`本身就是`b`。

**例:**

```
Input : n = 2
Output : 3
(1, 1) (2, 2) and (2, 1) 

Input : n = 3
Output : 5
(1, 1) (2, 2) (3, 3) (2, 1) and (3, 1)
```

**天真法:** `gcd(a, b) = b`表示`b`是`a`的因子，所以总对数将等于`a = 1`到`n`每个的除数之和，具体实现请参考[求自然数的所有除数](https://www.geeksforgeeks.org/find-all-divisors-of-a-natural-number-set-2/)。

**有效方法:** `gcd(a, b) = b`意味着`a`是`b`的倍数。因此，总的对数将是每个`b`的倍数之和(其中`b`从`1`到`n`不等)，该倍数小于或等于`n`。
对于数字`i`，`i`的倍数小于或等于`floor(n/i)`。因此，我们需要做的只是将每个`i = 1`到`n`的`floor(n/i)`相加并打印出来。但是可以做更多的优化。对于`i >= sqrt(n)`，`floor(n/i)`可以具有`2 * sqrt(n)`个不同的值。`floor(n/i)`可以从`1`变化到`sqrt(n)`，类似地，对于`i = 1`到`sqrt(n)`，`floor(n/i)`可以具有从`1`到`sqrt(n)`的值。总共`2*sqrt(n)`个不同的值。

```
let floor(n/i) = k
k <= n/i < k + 1
n/k+1 < i <= n/k
floor(n/k+1) < i <= floor(n/k)
Thus for given k the largest value of i for 
which the floor(n/i) = k is floor(n/k)
and all the set of i for which the 
floor(n/i) = k are consecutive
```

## C++ 实现

```cpp
// C++ implementation of counting pairs
// such that gcd (a, b) = b
#include <bits/stdc++.h>
using namespace std;

// returns number of valid pairs
int CountPairs(int n)
{
    // initialize k
    int k = n;

    // loop till imin <= n
    int imin = 1;

    // Initialize result
    int ans = 0;

    while (imin <= n) {

        // max i with given k floor(n/k)
        int imax = n / k;

        // adding k*(number of i with
        // floor(n/i) = k to ans
        ans += k * (imax - imin + 1);

        // set imin = imax + 1 and k = n/imin
        imin = imax + 1;
        k = n / imin;
    }

    return ans;
}

// Driver function
int main()
{
    cout << CountPairs(1) << endl;
    cout << CountPairs(2) << endl;
    cout << CountPairs(3) << endl;
    return 0;
}
```

## Java 实现

```java
// Java implementation of counting pairs
// such that gcd (a, b) = b
class GFG {

    // returns number of valid pairs
    static int CountPairs(int n) {

        // initialize k
        int k = n;

        // loop till imin <= n
        int imin = 1;

        // Initialize result
        int ans = 0;

        while (imin <= n) {

            // max i with given k floor(n/k)
            int imax = n / k;

            // adding k*(number of i with
            // floor(n/i) = k to ans
            ans += k * (imax - imin + 1);

            // set imin = imax + 1
            // and k = n/imin
            imin = imax + 1;
            k = n / imin;
        }

        return ans;
    }

    // Driver code
    public static void main(String[] args) {
        System.out.println(CountPairs(1));
        System.out.println(CountPairs(2));
        System.out.println(CountPairs(3));
    }
}

// This code is contributed by Anant Agarwal.
```

## Python 实现

```python
# Python implementation of counting
# pairs such that gcd (a, b) = b

# returns number of valid pairs
def CountPairs(n):

    # initialize k
    k = n

    # loop till imin <= n
    imin = 1

    # Initialize result
    ans = 0

    while(imin <= n):

        # max i with given k floor(n / k)
        imax = n / k

        # adding k*(number of i with
        # floor(n / i) = k to ans
        ans += k * (imax - imin + 1)

        # set imin = imax + 1 and
        # k = n / imin
        imin = imax + 1
        k = n / imin

    return ans

# Driver code
print(CountPairs(1))
print(CountPairs(2))
print(CountPairs(3))

# This code is contributed by Anant Agarwal.
```

## C# 实现

```csharp
// C# implementation of counting
// pairs such that gcd (a, b) = b
using System;

class GFG {

    // returns number of valid pairs
    static int CountPairs(int n)
    {

        // initialize k
        int k = n;

        // loop till imin <= n
        int imin = 1;

        // Initialize result
        int ans = 0;

        while (imin <= n) {

            // max i with given
            // k floor(n / k)
            int imax = n / k;

            // adding k * (number of i 
            // with floor(n / i) = k
            // to ans
            ans += k * (imax - imin + 1);

            // set imin = imax + 1
            // and k = n / imin
            imin = imax + 1;
            k = n / imin;
        }

        return ans;
    }

    // Driver code
    public static void Main(String []args)
    {
        Console.WriteLine(CountPairs(1));
        Console.WriteLine(CountPairs(2));
        Console.WriteLine(CountPairs(3));
    }
}

// This code is contributed by vt_m.
```

## PHP 实现

```php
<?php
// PHP implementation of counting
// pairs such that gcd (a, b) = b

// returns number of valid pairs
function CountPairs($n)
{

    // initialize k
    $k = $n;

    // loop till imin <= n
    $imin = 1;

    // Initialize result
    $ans = 0;

    while ($imin <= $n)
    {

        // max i with given k floor(n/k)
        $imax = $n / $k;

        // adding k*(number of i with
        // floor(n/i) = k to ans
        $ans += $k * ($imax - $imin + 1);

        // set imin = imax + 1
        // and k = n/imin
        $imin = $imax + 1;
        $k = (int)($n / $imin);
    }

    return $ans;
}

// Driver Code
echo(CountPairs(1) . "\n");
echo(CountPairs(2) . "\n");
echo(CountPairs(3) . "\n");

// This code is contributed by Ajit.
?>
```

## JavaScript 实现

```javascript
<script>

// Javascript implementation of counting pairs
// such that gcd (a, b) = b

// returns number of valid pairs
function CountPairs(n)
{
    // initialize k
    let k = n;

    // loop till imin <= n
    let imin = 1;

    // Initialize result
    let ans = 0;

    while (imin <= n) {

        // max i with given k floor(n/k)
        let imax = Math.floor(n / k);

        // adding k*(number of i with
        // floor(n/i) = k to ans
        ans += k * (imax - imin + 1);

        // set imin = imax + 1 and k = n/imin
        imin = imax + 1;
        k = Math.floor(n / imin);
    }

    return ans;
}

// Driver function

    document.write(CountPairs(1) + "<br>");
    document.write(CountPairs(2) + "<br>");
    document.write(CountPairs(3) + "<br>");

// This is code is contributed by Mayank Tyagi

</script>
```

**输出:**

```
1
3
5
```

本文由 **Ayush Jha** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。