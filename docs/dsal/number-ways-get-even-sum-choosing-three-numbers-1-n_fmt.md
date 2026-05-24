# 从 1 到 N 选择三个数字得到偶数和的方法数

> 原文: [https://www.geeksforgeeks.org/number-ways-get-even-sum-choosing-three-numbers-1-n/](https://www.geeksforgeeks.org/number-ways-get-even-sum-choosing-three-numbers-1-n/)

给定一个整数 `N`，找出我们可以从 `{1, 2, 3, ..., N}` 中选择 3 个数字的方法数，使它们的和为偶数。

示例:

```
Input :  N = 3
Output : 1
Explanation: Select 1, 2 and 3

Input :  N = 4
Output :  2
Either select (1, 2, 3) or (1, 3, 4)
```

[推荐:请先在“<u>”上解，再进行解。</u>](https://practice.geeksforgeeks.org/problems/three-number-even-sum/0)

为了得到和，只能有两种情况:

1.  取 2 个奇数和 1 个偶数。
2.  取所有偶数。

```
If n is even,
  Count of odd numbers = n/2 and even = n/2.
Else
  Count odd numbers = n/2 +1 and evne = n/2.
```

情况 1–路数为:`奇数 C 2 偶数`。
情况 2–路号为:`偶数 C 3`。
所以，总的方式是 `Case_1_result + Case_2_result`。

## C++

```
// C++ program for above implementation
#include <bits/stdc++.h>
#define MOD 1000000007
using namespace std;

// Function to count number of ways
int countWays(int N)
{
    long long int count, odd = N / 2, even;
    if (N & 1)
        odd = N / 2 + 1;

    even = N / 2;

    // Case 1: 2 odds and 1 even
    count = (((odd * (odd - 1)) / 2) * even) % MOD;

    // Case 2: 3 evens
    count = (count + ((even * (even - 1) *
                           (even - 2)) / 6)) % MOD;

    return count;
}

// Driver code
int main()
{
    int n = 10;
    cout << countWays(n) << endl;
    return 0;
}
```

## Java

```
// java program for above implementation
import java.io.*;

class GFG {

    static long MOD = 1000000007;

    // Function to count number of ways
    static long countWays(int N)
    {
        long count, odd = N / 2, even;

        if ((N & 1) > 0)
            odd = N / 2 + 1;

        even = N / 2;

        // Case 1: 2 odds and 1 even
        count = (((odd * (odd - 1)) / 2)
                          * even) % MOD;

        // Case 2: 3 evens
        count = (count + ((even * (even
                - 1) * (even - 2)) / 6))
                                  % MOD;

        return (long)count;
    }

    // Driver code
    static public void main (String[] args)
    {
        int n = 10;

        System.out.println(countWays(n));
    }
}

// This code is contributed by vt_m.
```

## Python 3

```
# Python3 code for above implementation

MOD = 1000000007

# Function to count number of ways
def countWays( N ):
    odd = N / 2
    if N & 1:
        odd = N / 2 + 1
    even = N / 2

    # Case 1: 2 odds and 1 even
    count = (((odd * (odd - 1)) / 2) * even) % MOD

    # Case 2: 3 evens
    count = (count + ((even * (even - 1) *
            (even - 2)) / 6)) % MOD
    return count

# Driver code
n = 10
print(int(countWays(n)))

# This code is contributed by "Sharad_Bhardwaj"
```

## C\#

```
// C# program for above implementation
using System;

public class GFG {

    static long MOD = 1000000007;

    // Function to count number of ways
    static long countWays(int N)
    {
        long count, odd = N / 2, even;

        if ((N & 1) > 0)
            odd = N / 2 + 1;

        even = N / 2;

        // Case 1: 2 odds and 1 even
        count = (((odd * (odd - 1)) / 2)
                            * even) % MOD;

        // Case 2: 3 evens
        count = (count + ((even * (even
                  - 1) * (even - 2)) / 6))
                                    % MOD;

        return (long)count;
    }

    // Driver code
    static public void Main ()
    {
        int n = 10;

        Console.WriteLine(countWays(n));
    }
}

// This code is contributed by vt_m.
```

## PHP

```
<?php
// PHP program for
// above implementation

$MOD = 1000000007;

// Function to count
// number of ways
function countWays($N)
{
    global $MOD;

    $count;
    $odd =$N / 2;
    $even;
    if ($N & 1)
        $odd = $N / 2 + 1;

    $even = $N / 2;

    // Case 1: 2 odds
    // and 1 even
    $count = ((($odd * ($odd - 1)) / 2) *
                            $even) % $MOD;

    // Case 2: 3 evens
    $count = ($count + (($even * ($even - 1) *
                        ($even - 2)) / 6)) % $MOD;

    return $count;
}

    // Driver Code
    $n = 10;
    echo countWays($n);

// This code is contributed by anuj_67.
?>
```

## JavaScript

```
<script>

// Javascript program for above implementation
let MOD = 1000000007;

    // Function to count number of ways
    function countWays(N)
    {
        let count, odd = N / 2, even;

        if ((N & 1) > 0)
            odd = N / 2 + 1;

        even = N / 2;

        // Case 1: 2 odds and 1 even
        count = (((odd * (odd - 1)) / 2)
                          * even) % MOD;

        // Case 2: 3 evens
        count = (count + ((even * (even
                - 1) * (even - 2)) / 6))
                                  % MOD;

        return count;
    }

// Driver code
        let n = 10;         
        document.write(countWays(n));

        // This code is contributed by code_hunt.
</script>
```

输出:

```

```

本文由 [**萨哈布拉**](https://www.facebook.com/sahil.chhabra.965) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。