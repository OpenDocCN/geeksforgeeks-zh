# 求给定数列的第 n 项

> 原文: [https://www.geeksforgeeks.org/find-the-nth-term-of-the-given-series/](https://www.geeksforgeeks.org/find-the-nth-term-of-the-given-series/)

假设数列的前两个项为 `1` 和 `6`，数列的所有元素都比前后数的平均值少 2。任务是打印该系列的第 `n` 个术语。
该系列的前几个术语是:

> 1, 6, 15, 28, 45, 66, 91, …

**例:**

> **输入:** `N = 3`
> **输出:** `15`
> **输入:** `N = 1`
> **输出:** `1`

**方法:** 给定的数列表示[三角形数列](https://www.geeksforgeeks.org/triangular-numbers/)中的奇数。由于第 `n` 个三角数很容易被 `(n * (n + 1) / 2)` 找到，所以为了找到奇数，我们可以将 `n` 替换为 `(2 * n) - 1`，因为 `(2 * n) - 1` 将总是产生奇数，即给定系列的第 `n` 个数字将是 `N * ((2 * N) - 1)`。
以下是上述方法的实施:

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the nth term
// of the given series
int oddTriangularNumber(int N)
{
    return (N * ((2 * N) - 1));
}

// Driver code
int main()
{
    int N = 3;
    cout << oddTriangularNumber(N);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
class GFG
{

// Function to return the nth term
// of the given series
static int oddTriangularNumber(int N)
{
    return (N * ((2 * N) - 1));
}

// Driver code
public static void main(String[] args)
{
    int N = 3;
    System.out.println(oddTriangularNumber(N));
}
}

// This code contributed by Rajput-Ji
```

## Python 3

```python
# Python 3 implementation of the approach

# Function to return the nth term
# of the given series
def oddTriangularNumber(N):
    return (N * ((2 * N) - 1))

# Driver code
if __name__ == '__main__':
    N = 3
    print(oddTriangularNumber(N))

# This code is contributed by
# Surendra_Gangwar
```

## C#

```csharp
// C# implementation of the approach
using System;

class GFG
{

    // Function to return the nth term
    // of the given series
    static int oddTriangularNumber(int N)
    {
        return (N * ((2 * N) - 1));
    }

    // Driver code
    public static void Main(String[] args)
    {
        int N = 3;
        Console.WriteLine(oddTriangularNumber(N));
    }
}

/* This code contributed by PrinciRaj1992 */
```

## PHP

```php
<?php
// PHP implementation of the approach

// Function to return the nth term
// of the given series
function oddTriangularNumber($N)
{
    return ($N * ((2 * $N) - 1));
}

    // Driver code
    $N = 3;
    echo oddTriangularNumber($N);

    // This code is contributed by Ryuga

?>
```

## JavaScript

```javascript
<script>
// Javascript implementation of the approach

// Function to return the nth term
// of the given series
function oddTriangularNumber(N)
{
    return (N * ((2 * N) - 1));
}

// Driver code
let N = 3;
document.write(oddTriangularNumber(N));

// This code is contributed by subham348.
</script>
```

**Output:**

```
15
```