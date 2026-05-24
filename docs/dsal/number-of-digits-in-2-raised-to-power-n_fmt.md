# 计算 2^n 的位数

> 原文: [https://www.geeksforgeeks.org/number-of-digits-in-2-raised-to-power-n/](https://www.geeksforgeeks.org/number-of-digits-in-2-raised-to-power-n/)

设 `n` 为任意指数，即 `2^n`。给定数字 `n`，我们的任务是找出 `2^n` 中包含的位数。

## 示例

```
Input : n = 5
Output : 2
Explanation : 2^n = 32, which has only 2 digits.

Input : n = 10
Output : 4
Explanation : 2^n = 1024, which has only 4 digits.
```

我们可以用对数重写 `2^n` 如下：

`2^n = 10^(n * log10(2))`

现在假设，`x = n * log10(2)`。
因此，`2^n = 10^x`。
同样，我们都知道数字 `10^n` 会有 `(n+1)` 个数字。因此，`10^x` 将有 `(x+1)` 个数字。
或者，我们可以说 `2^n` 会有 `(x+1)` 个数字，因为 `2^n = 10^x`。
因此，`2^n` 中的位数 = `(n * log10(2)) + 1`。

以下是上述思路的实现：

## C++

```cpp
// CPP program to find number of digits in 2^n
#include <bits/stdc++.h>
using namespace std;

// Function to find number of digits in 2^n
int countDigits(int n)
{
    return (n * log10(2) + 1);
}

// Driver code
int main()
{
    int n = 5;
    cout << countDigits(n) << endl;
    return 0;
}
```

## Java

```java
// Java program to find number of digits in 2^n
import java.util.*;

class Gfg
{
    // Function to find number of digits in 2^n
    static int countDigits(int n)
    {
        return (int)(n * Math.log10(2) + 1);
    }

    // Driver Code
    public static void main(String args[])
    {
        int n = 5;
        System.out.println(countDigits(n));
    }
}

// This code is contributed by Niraj_Pandey.
```

## Python 3

```python
# Python3 program to find number of digits in 2^n
import math

# Function to find number of digits in 2^n
def countDigits(n):
    return int(n * math.log10(2) + 1);

# Driver code
n = 5;
print(countDigits(n));

# This code is contributed by mits
```

## C#

```csharp
// C# program to find number of digits in 2^n
using System;

class GFG
{
    // Function to find number of digits in 2^n
    static int countDigits(int n)
    {
        return (int)(n * Math.Log10(2) + 1);
    }

    // Driver code
    static void Main()
    {
        int n = 5;
        Console.Write(countDigits(n));
    }
}
// This code is contributed by Manish Shaw(manishshaw1)
```

## PHP

```php
<?php
// PHP program to find number of digits in 2^n

// Function to find number of digits in 2^n
function countDigits($n)
{
    return intval($n * log10(2) + 1);
}

// Driver code
$n = 5;
echo (countDigits($n));

// This code is contributed by Manish Shaw(manishshaw1)
?>
```

## JavaScript

```javascript
<script>
// JavaScript program to find number of digits in 2^n

// Function to find number of digits in 2^n
function countDigits(n)
{
    return (n * Math.log10(2) + 1);
}

// Driver code
let n = 5;
document.write(Math.floor(countDigits(n)));

// This code is contributed by souravghosh0416.
</script>
```

## 输出

```
2
```

## 复杂度分析

- **时间复杂度:** `O(1)`
- **辅助空间:** `O(1)`