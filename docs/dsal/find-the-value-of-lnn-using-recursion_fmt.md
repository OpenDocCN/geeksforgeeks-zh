# 求 ln(N!) 使用递归

> 原文: [https://www.geeksforgeeks.org/find-the-value-of-lnn-using-recursion/](https://www.geeksforgeeks.org/find-the-value-of-lnn-using-recursion/)

给定一个数字 `N`，任务是找到 `N` 的阶乘的对数值，即 `log(N!)`。
注: `ln` 表示自然对数（以 `e` 为底）。

**例:**

```
Input: N = 2
Output: 0.693147

Input:  N = 3
Output: 1.791759
```

## 进场

**方法-1:** 先计算 `n!`，然后取其对数值。
**方法-2:** 利用对数的性质，即取 `n`，`n-1`，`n-2` … `1` 的对数值之和。

> **ln(n!) = ln(n * n-1 * n-2 * ... * 2 * 1) = ln(n) + ln(n-1) + ... + ln(2) + ln(1)**

下面是方法-2 的实现:

### C++

```cpp
// C++ implementation of the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to calculate the value
double fact(int n)
{
    if (n == 1)
        return 0;
    return fact(n - 1) + log(n);
}
// Driver code
int main()
{
    int N = 3;
    cout << fact(N) << "\n";
    return 0;
}
```

### C

```c
// C implementation of the above approach
#include <math.h>
#include <stdio.h>

long double fact(int n)
{
    if (n == 1)
        return 0;
    return fact(n - 1) + log(n);
}

// Driver code
int main()
{
    int n = 3;
    printf("%Lf", fact(n));
    return 0;
}
```

### Java

```java
// Java implementation of the above approach
import java.util.*;
import java.io.*;
class logfact {
    public static double fact(int n)
    {
        if (n == 1)
            return 0;
        return fact(n - 1) + Math.log(n);
    }

    public static void main(String[] args)
    {

        int N = 3;
        System.out.println(fact(N));
    }
}
```

### Python

```python
# Python implementation of the above approach
import math
def fact(n):
    if (n == 1):
        return 0
    else:
        return fact(n-1) + math.log(n)
N = 3
print(fact(N))
```

### C#

```csharp
// C# implementation of the above approach
using System;

class GFG
{
    public static double fact(int n)
    {
        if (n == 1)
            return 0;
        return fact(n - 1) + Math.Log(n);
    }

    // Driver code
    public static void Main()
    {
        int N = 3;
        Console.WriteLine(fact(N));
    }
}

// This code is contributed by ihritik
```

### PHP

```php
<?php

//PHP implementation of the above approach

function fact($n)
{
    if ($n == 1)
        return 0;
    return fact($n - 1) + log($n);
}

// Driver code
$n = 3;
echo fact($n);

// This code is contributed by ihritik
?>
```

### JavaScript

```javascript
<script>

// Javascript implementation of the above approach

// Function to calculate the value
function fact(n)
{
    if (n == 1)
        return 0;
    return fact(n - 1) + Math.log(n);
}
// Driver code
var N = 3;
document.write( fact(N).toFixed(6) + "<br>");

</script>
```

**Output:**

```
1.791759
```