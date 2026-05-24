# 找到最小的完美平方数 A，使得 N + A 也是一个完美平方数

> 原文：[https://www.geeksforgeeks.org/find-smallest-perfect-square-number-a-such-that-n-a-is-also-a-perfect-square-number/](https://www.geeksforgeeks.org/find-smallest-perfect-square-number-a-such-that-n-a-is-also-a-perfect-square-number/)

给定一个正数 `N`。任务是找出最小的完美平方数 `A`，使得 `N + A` 也是一个完美平方数，或者返回 `-1`。

## 示例

```
Input: N = 3
Output: 1
Explanation: 
As 1 + 3 = 4 = 2^2

Input: N=1
Output: -1
```

## 天真方法

从 `{1, 2, 3, 4, 5...}` 遍历 `M`，检查 `(N + M * M)` 是否是一个完美的平方数。

## 高效方法

在观察时，我们有一个方程，如：

> `N + (X * X) = (M * M)`，其中 `N` 是给定的，`M` 和 `X` 是未知的。
> 我们可以重新排列它得到：
> `N = (M * M) – (X * X)`
> `N = (M + X) * (M – X)`

现在我们可以看到，为了得到 `N`，我们需要找到 `N` 的因子，`N` 的因子可以在 `O(N)` 时间内得到。但是可以通过[这个](https://www.geeksforgeeks.org/find-divisors-natural-number-set-1/)方法优化到 `O(N^1/2)`。

设 `N` 的因子为 `a` 和 `b = (N / a)`。所以，从上面的方程 `a = (M – X)` 和 `b = (M + X)`，求解后我们可以得到 `X = (b – a) / 2` 的值。

以下是上述方法的实现：

## C++

```cpp
// C++ code to find out the smallest
// perfect square X which when added to N
// yields another perfect square number.
#include<bits/stdc++.h>
using namespace std;

long SmallestPerfectSquare(long N){

    // X is the smallest perfect
    // square number
    long X = (long)1e9;
    long ans;

    // Loop from 1 to square root of N
    for(int i = 1; i < sqrt(N); i++)
    {

        // Condition to check whether i
        // is factor of N or not
        if (N % i == 0)
        {
            long a = i;
            long b = N / i;

            // Condition to check whether
            // factors satisfies the
            // equation or not
            if((b - a != 0) && ((b - a) % 2 == 0))
            {

                // Stores minimum value
                X = min(X, (b - a) / 2);
            }
        }
    }

    // Return if X * X if X is not equal
    // to 1e9 else return -1
    if (X != 1e9)
        ans = X * X;
    else
        ans = -1;

    return ans;
}

// Driver code
int main()
{
    long N = 3;
    cout << SmallestPerfectSquare(N);
    return 0;
}

// This code is contributed by AnkitRai01
```

## Java

```java
// Java code to find out the smallest
// perfect square X which when added to N
// yields another perfect square number.

public class GFG {

    static long SmallestPerfectSquare(long N)
    {

        // X is the smallest perfect
        // square number
        long X = (long)1e9;
        long ans;

        // Loop from 1 to square root of N
        for(int i = 1; i < Math.sqrt(N); i++){

            // Condition to check whether i
            // is factor of N or not
            if (N % i == 0){
                long a = i ;
                long b = N / i;

                // Condition to check whether
                // factors satisfies the
                // equation or not
                if ((b - a != 0) && ((b - a) % 2 == 0)){

                    // Stores minimum value
                    X = Math.min(X, (b - a) / 2) ;
                }
            }
        }

        // Return if X * X if X is not equal
        // to 1e9 else return -1
        if (X != 1e9)
            ans = X * X;
        else
            ans = -1;

        return ans;
    }

    // Driver code
    public static void main (String[] args){
        long N = 3;

        System.out.println(SmallestPerfectSquare(N)) ;

        }
}
// This code is contributed by AnkitRai01
```

## Python 3

```python
# Python3 code to find out the smallest
# perfect square X which when added to N
# yields another perfect square number.
import math
def SmallestPerfectSquare(N):

    # X is the smallest perfect
    # square number
    X = 1e9

    # Loop from 1 to square root of N
    for i in range(1, int(math.sqrt(N)) + 1):

        # Condition to check whether i
        # is factor of N or not
        if N % i == 0:
            a = i
            b = N // i 

            # Condition to check whether 
            # factors satisfies the
            # equation or not
            if b - a != 0 and (b - a) % 2 == 0:

                # Stores minimum value
                 X = min(X, (b - a) // 2)

    # Return if X * X if X is not equal
    # to 1e9 else return -1
    return(X * X if X != 1e9 else -1)

# Driver code
if __name__ == "__main__" : 

    N = 3

    print(SmallestPerfectSquare(N))
```

## C\#

```csharp
// C# code to find out the smallest
// perfect square X which when added to N
// yields another perfect square number.
using System;

class GFG {

    static long SmallestPerfectSquare(long N)
    {
        // X is the smallest perfect
        // square number
        long X = (long)1e9;
        long ans;

        // Loop from 1 to square root of N
        for(int i = 1; i < Math.Sqrt(N); i++){

            // Condition to check whether i
            // is factor of N or not
            if (N % i == 0)
            {
                long a = i;
                long b = N / i;

                // Condition to check whether
                // factors satisfies the
                // equation or not
                if ((b - a != 0) && ((b - a) % 2 == 0))
                {
                    // Stores minimum value
                    X = Math.Min(X, (b - a) / 2);
                }
            }
        }

        // Return if X*X if X is not equal
        // to 1e9 else return -1
        if (X != 1e9)
            ans = X * X;
        else
            ans = -1;

        return ans;
    }

    // Driver code
    public static void Main (string[] args)
    {
        long N = 3;
        Console.WriteLine(SmallestPerfectSquare(N));
    }
}

// This code is contributed by AnkitRai01
```

## JavaScript

```javascript
<script>

// JavaScript code to find out the smallest
// perfect square X which when added to N
// yields another perfect square number. 

function SmallestPerfectSquare(N){

    // X is the smallest perfect
    // square number
    let X = 1e9;
    let ans;

    // Loop from 1 to square root of N
    for(let i = 1; i < Math.sqrt(N); i++)
    {

        // Condition to check whether i
        // is factor of N or not
        if (N % i == 0)
        {
            let a = i;
            let b = N / i;

            // Condition to check whether
            // factors satisfies the
            // equation or not
            if((b - a != 0) && ((b - a) % 2 == 0))
            {

                // Stores minimum value
                X = Math.min(X, (b - a) / 2);
            }
        }
    }

    // Return if X * X if X is not equal
    // to 1e9 else return -1
    if (X != 1e9)
        ans = X * X;
    else
        ans = -1;

    return ans;
}

// Driver code

    let N = 3;
    document.write(SmallestPerfectSquare(N)); 

// This code is contributed by Surbhi Tyagi.

</script>
```

**输出：**

```
1
```

**时间复杂度：** `O(sqrt(N))`