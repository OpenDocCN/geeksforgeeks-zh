# 求数列 2*3*5，3*5*7，4*7*9 的前 N 项之和

> 原文: [https://www.geeksforgeeks.org/find-the-sum-of-first-n-terms-of-the-series-235-357-479/](https://www.geeksforgeeks.org/find-the-sum-of-first-n-terms-of-the-series-235-357-479/)

给定一个整数 `N`，任务是找到系列的第一个 `N` 项的和:
> (2 * 3 * 5)，(3 * 5 * 7)，(4 * 7 * 9)，…

**例:**
> **输入:** `N = 3`
> **输出:** 387
> S<sub>3</sub> = (2 * 3 * 5) + (3 * 5 * 7) + (4 * 7 * 9) = 30 + 105 + 252 = 387
> **输入:** `N = 5`
> **输出:** 1740

**方法:** 让本系列的第 `N` 项为 `T_n`。通过观察系列的第 `N` 项可以很容易地找到系列的总和:
> `T_n` = {第 n 个 2, 3, 4, … 项} * {第 n 个 3, 5, 7, … 项} * {第 n 个 5, 7, 9, … 项}
> `T_n` = (n + 1) * (2 * n + 1) * (2 * n + 3)

前 n 项之和 (`S_n`) 可由下式找到:
> `S_n` = Σ `T_n` 从 i=1 到 n

**以下是上述方法的实现:**

## C++

```cpp
// C++ program to find sum of the
// first n terms of the given series
#include <bits/stdc++.h>
using namespace std;

// Function to return the sum of the
// first n terms of the given series
int calSum(int n)
{
    // As described in the approach
    return (n * (2 * n * n * n + 12 * n * n + 25 * n + 21)) / 2;
}

// Driver code
int main()
{
    int n = 3;
    cout << calSum(n);
    return 0;
}
```

## Java

```java
// Java program to find sum of the
// first n terms of the given series
class GFG {

    // Function to return the sum of the
    // first n terms of the given series
    static int calSum(int n)
    {

        // As described in the approach
        return (n * (2 * n * n * n + 12 * n * n + 25 * n + 21)) / 2;
    }

    // Driver Code
    public static void main(String args[])
    {
        int n = 3;
        System.out.println(calSum(n));
    }
}
```

## Python

```python
# Python program to find sum of the
# first n terms of the given series

# Function to return the sum of the
# first n terms of the given series
def calSum(n):

    # As described in the approach
    return (n*(2 * n*n * n + 12 * n*n + 25 * n + 21))//2

# Driver Code
n = 3
print(calSum(n))
```

## C#

```csharp
// C# program to find sum of the
// first n terms of the given series
using System;

class GFG {

    // Function to return the sum of the
    // first n terms of the given series
    static int calSum(int n)
    {

        // As described in the approach
        return (n * (2 * n * n * n + 12 * n * n + 25 * n + 21)) / 2;
    }

    // Driver code
    static public void Main()
    {
        int n = 3;
        Console.WriteLine(calSum(n));
    }
}
```

## PHP

```php
<?php
// PHP script to find sum of the
// first n terms of the given series

// Function to return the sum of the
// first n terms of the given series
function calculateSum($n)
{

    // As described in the approach
    return ($n*(2*$n*$n*$n+12*$n*$n+25*$n+21))/2;
}

// Driver code
$n = 3;
echo calculateSum($n);

?>
```

## JavaScript

```javascript
<script>
// Javascript program to find sum of the
// first n terms of the given series

    // Function to return the sum of the
    // first n terms of the given series
    function calSum( n) {

        // As described in the approach
        return (n * (2 * n * n * n + 12 * n * n + 25 * n + 21)) / 2;
    }

    // Driver Code
    let n = 3;
    document.write(calSum(n));

// This code is contributed by 29AjayKumar
</script>
```

**Output:**

```