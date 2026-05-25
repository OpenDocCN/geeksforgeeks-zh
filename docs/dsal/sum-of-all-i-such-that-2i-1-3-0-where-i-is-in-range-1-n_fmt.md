# 所有 i 的和，使得 (2^i + 1) % 3 = 0，其中 i 在范围 [1, n] 内

> 原文: [https://www.geeksforgeeks.org/sum-of-all-i-such-that-2i-1-3-0-where-i-is-in-range-1-n/](https://www.geeksforgeeks.org/sum-of-all-i-such-that-2i-1-3-0-where-i-is-in-range-1-n/)

给定一个整数 `N`，任务是计算从 `1` 到 `N` 的所有 `i` 的和，使得 `(2^i + 1) % 3 = 0`。

**示例:**

> **输入:** `N = 3`
> **输出:** 4
> 对于 `i = 1`，`2^1 + 1 = 3` 可被 3 整除。
> 对于 `i = 2`，`2^2 + 1 = 5` 不能被 3 整除。
> 对于 `i = 3`，`2^3 + 1 = 9` 可被 3 整除。
> 因此，和 = 1 + 3 = 4 (对于 `i = 1, 3`)
> **输入:** `N = 13`
> **输出:** 49

**方法:** 如果我们仔细观察，那么 `i` 将永远是一个奇数，即 `1, 3, 5, 7, …..`。我们将使用前 n 个奇数之和的公式，即 `n * n`。

以下是上述方法的实现：

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the required sum
int sumN(int n)
{

    // Total odd numbers from 1 to n
    n = (n + 1) / 2;

    // Sum of first n odd numbers
    return (n * n);
}

// Driver code
int main()
{
    int n = 3;
    cout << sumN(n);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
class GFG {

    // Function to return the required sum
    static int sum(int n)
    {

        // Total odd numbers from 1 to n
        n = (n + 1) / 2;

        // Sum of first n odd numbers
        return (n * n);
    }

    // Driver code
    public static void main(String args[])
    {
        int n = 3;
        System.out.println(sum(n));
    }
}
```

## Python 3

```python
# Python3 implementation of the approach

# Function to return the required sum
def sumN(n):

    # Total odd numbers from 1 to n
    n = (n + 1) // 2;

    # Sum of first n odd numbers
    return (n * n);

# Driver code
n = 3;
print(sumN(n));

# This code is contributed by mits
```

## C#

```csharp
// C# implementation of the approach
using System;
public class GFG {

    // Function to return the required sum
    public static int sum(int n)
    {

        // Total odd numbers from 1 to n
        n = (n + 1) / 2;

        // Sum of first n odd numbers
        return (n * n);
    }

    // Driver code
    public static void Main(string[] args)
    {
        int n = 3;
        Console.WriteLine(sum(n));
    }
}

// This code is contributed by Shrikant13
```

## PHP

```php
<?php
// PHP implementation of the approach

// Function to return the required sum
function sumN($n)
{

    // Total odd numbers from 1 to n
    $n = (int)(($n + 1) / 2);

    // Sum of first n odd numbers
    return ($n * $n);
}

// Driver code
$n = 3;
echo sumN($n);

// This code is contributed by mits
?>
```

## JavaScript

```javascript
<script>
// Javascript implementation of the approach

// Function to return the required sum
function sumN(n)
{

    // Total odd numbers from 1 to n
    n = parseInt((n + 1) / 2);

    // Sum of first n odd numbers
    return (n * n);
}

// Driver code
var n = 3;
document.write(sumN(n));

// This code is contributed by noob2000.

</script>
```

**输出:**

```
4
```

**时间复杂度:** `O(1)`