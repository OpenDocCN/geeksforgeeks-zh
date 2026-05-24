# 打印前 N 个马赛克号

> 原文: [https://www.geeksforgeeks.org/print-first-n-mosaic-numbers/](https://www.geeksforgeeks.org/print-first-n-mosaic-numbers/)

给定一个整数 `N`，任务是打印前 `N` 个马赛克数字。马赛克数可以表示如下:

> 如果 `N = p1^a1 * p2^a2 * ... * pk^ak` 在 `N` 的素因式分解中，其中 `p1, p2 ... pk` 是质数，那么第 `N` 个镶嵌数等于 `(p1 * a1) * (p2 * a2) * ... * (pk * ak)`。

## 示例

> **输入:** `N = 10`
> **输出:** `1 2 3 4 5 6 7 6 10`
> 对于 `N = 4`，`N = 2^2`。
> 4<sup>第</sup>镶嵌编号= `2*2 = 4`
> 对于 `N=8`，`N = 2^3`，8<sup>第</sup>镶嵌编号= `2*3 = 6`
> 同样打印前 `N` 个镶嵌编号
>
> **输入:** `N = 5`
> **输出:** `1 2 3 4 5`

## 逼近

运行一个从 `1` 到 `N` 的循环，对于每一个 `i`，我们必须通过将数除以因子直到因子除以数来找到所有的质因数以及数中因子的幂。然后，第 `i` 个马赛克数将是已发现的质因数及其幂的乘积。

下面是上述方法的实现:

### C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the nth mosaic number
int mosaic(int n)
{
    int i, ans = 1;

    // Iterate from 2 to the number
    for (i = 2; i <= n; i++) {

        // If i is the factor of n
        if (n % i == 0 && n > 0) {
            int count = 0;

            // Find the count where i^count
            // is a factor of n
            while (n % i == 0) {

                // Divide the number by i
                n /= i;

                // Increase the count
                count++;
            }

            // Multiply the answer with
            // count and i
            ans *= count * i;
        }
    }

    // Return the answer
    return ans;
}

// Function to print first N Mosaic numbers
void nMosaicNumbers(int n)
{
    for (int i = 1; i <= n; i++)
        cout << mosaic(i) << " ";
}

// Driver code
int main()
{
    int n = 10;
    nMosaicNumbers(n);

    return 0;
}
```

### Java

```java
// Java implementation of the approach
class GFG
{

    // Function to return the nth mosaic number
    static int mosaic(int n)
    {
        int i, ans = 1;

        // Iterate from 2 to the number
        for (i = 2; i <= n; i++)
        {

            // If i is the factor of n
            if (n % i == 0 && n > 0)
            {
                int count = 0;

                // Find the count where i^count
                // is a factor of n
                while (n % i == 0)
                {

                    // Divide the number by i
                    n /= i;

                    // Increase the count
                    count++;
                }

                // Multiply the answer with
                // count and i
                ans *= count * i;
            }
        }

        // Return the answer
        return ans;
    }

    // Function to print first N Mosaic numbers
    static void nMosaicNumbers(int n)
    {
        for (int i = 1; i <= n; i++)
            System.out.print( mosaic(i)+ " ");
    }

    // Driver code
    public static void main(String[] args)
    {

        int n = 10;
        nMosaicNumbers(n);
    }
}

// This code contributed by Rajput-Ji
```

### C\#

```csharp
// C# implementation of the approach
using System;

class GFG
{

    // Function to return the nth mosaic number
    static int mosaic(int n)
    {
        int i, ans = 1;

        // Iterate from 2 to the number
        for (i = 2; i <= n; i++)
        {

            // If i is the factor of n
            if (n % i == 0 && n > 0)
            {
                int count = 0;

                // Find the count where i^count
                // is a factor of n
                while (n % i == 0)
                {

                    // Divide the number by i
                    n /= i;

                    // Increase the count
                    count++;
                }

                // Multiply the answer with
                // count and i
                ans *= count * i;
            }
        }

        // Return the answer
        return ans;
    }

    // Function to print first N Mosaic numbers
    static void nMosaicNumbers(int n)
    {
        for (int i = 1; i <= n; i++)
            Console.Write( mosaic(i)+ " ");
    }

    // Driver code
    public static void Main()
    {

        int n = 10;
        nMosaicNumbers(n);
    }
}

// This code is contributed by AnkitRai01
```

### Python

```python
# Python implementation of the approach

# Function to return the nth mosaic number
def mosaic( n):
    ans = 1

    # Iterate from 2 to the number
    for i in range(2,n+1):

        # If i is the factor of n
        if (n % i == 0 and n > 0):
            count = 0;

            # Find the count where i^count
            # is a factor of n
            while (n % i == 0):

                # Divide the number by i
                n = n// i

                # Increase the count
                count+=1;

            # Multiply the answer with
            # count and i
            ans *= count * i;

    # Return the answer
    return ans;

# Function to print first N Mosaic numbers
def nMosaicNumbers(n):
    for i in range(1,n+1):
        print (mosaic(i), end=" ")

# Driver code
n = 10;
nMosaicNumbers(n);

# This code is contributed by CrazyPro
```

### JavaScript

```javascript
<script>

// Javascript implementation of the approach

// Function to return the nth mosaic number
function mosaic(n)
{
    var i, ans = 1;

    // Iterate from 2 to the number
    for (i = 2; i <= n; i++) {

        // If i is the factor of n
        if (n % i == 0 && n > 0) {
            var count = 0;

            // Find the count where i^count
            // is a factor of n
            while (n % i == 0) {

                // Divide the number by i
                n /= i;

                // Increase the count
                count++;
            }

            // Multiply the answer with
            // count and i
            ans *= count * i;
        }
    }

    // Return the answer
    return ans;
}

// Function to print first N Mosaic numbers
function nMosaicNumbers(n)
{
    for (var i = 1; i <= n; i++)
        document.write( mosaic(i) + " ");
}

// Driver code
var n = 10;
nMosaicNumbers(n);

</script>
```

## 输出

```
1 2 3 4 5 6 7 6 6 10
```