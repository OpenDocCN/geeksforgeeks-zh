# 级数之和

求数列第 n 项之和的公式：`(n^2-1^2) + 2(n^2-2^2) + 3(n^2-3^2) + ... + n(n^2-n^2)`

> 原文：[https://www.geeksforgeeks.org/sum-series-n2-12-2n2-22-nn2-n2/](https://www.geeksforgeeks.org/sum-series-n2-12-2n2-22-nn2-n2/)

## 问题描述与示例

给定一个整数 `n`，计算上述数列的和。

**示例：**

```
Input : 2
Output : 3

Input : 5
Output : 150
```

## 解决方法

为了解决这个问题，我们有公式：`((1/4)*n^2*(n^2-1))`。我们可以用数学归纳法证明这个公式。

**示例：** `n = 2`
```
result = ((1/4)*2^2*(2^2-1))
       = ((0.25)*4*(4-1))
       = ((0.25)*4*3)
       = 3
```

## 代码实现

### C++

```cpp
// CPP Program to finding the
// sum of the nth series
#include <bits/stdc++.h>
using namespace std;

// function that calculate
// the sum of the nth series
int sum_series(int n)
{
    int nSquare = n * n;

    // using formula of the nth term
    return nSquare * (nSquare - 1) / 4;
}

// driver function
int main()
{
    int n = 2;
    cout << sum_series(n) << endl;
    return 0;
}
```

### Java

```java
// javaProgram to finding the
// sum of the nth series
import java.io.*;

class GFG {

    // function that calculate
    // the sum of the nth series
    static int sum_series(int n)
    {
        int nSquare = n * n;

        // using formula of the nth term
        return nSquare * (nSquare - 1) / 4;
    }

    // Driver function
    public static void main (String[] args)
    {
        int n = 2;
        System.out.println( sum_series(n)) ;

    }

}
// This article is contributed by vt_m
```

### Python 3

```python
# Python 3 Program to finding
# the sum of the nth series

# function that calculate
# the sum of the nth series
def sum_series(n):

    nSquare = n * n

    # Using formula of the
    # nth term
    return int(nSquare * (nSquare - 1) / 4)

# Driver function
n = 2
print(sum_series(n))

# This code is contributed by Smitha Dinesh Semwal
```

### C\#

```csharp
// C# program to finding the
// sum of the nth series
using System;

class GFG {

    // Function that calculate
    // the sum of the nth series
    static int sum_series(int n)
    {
        int nSquare = n * n;

        // Using formula of the nth term
        return nSquare * (nSquare - 1) / 4;
    }

    // Driver Code
    public static void Main ()
    {
        int n = 2;
        Console.Write( sum_series(n)) ;

    }
}

// This code is contributed by vt_m
```

### PHP

```php
<?php
// PHP Program to finding the
// sum of the nth series

// function that calculate
// the sum of the nth series
function sum_series($n)
{
    $nSquare = $n * $n;

    // using formula of the nth term
    return $nSquare * ($nSquare - 1) / 4;
}

// Driver Code
$n = 2;
echo(sum_series($n));

// This code is contributed by Ajit.
?>
```

### JavaScript

```javascript
<script>

// JavaScript Program to finding the
// the sum of the nth series

    // function that calculate
    // the sum of the nth series
    function sum_series(n)
    {
        let nSquare = n * n;

        // using formula of the nth term
        return nSquare * (nSquare - 1) / 4;
    }

// Driver code

        let n = 2;
        document.write( sum_series(n)) ;

</script>
```

**Output:**

```