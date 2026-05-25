# 带 AP 交替符号平方的级数之和

> 原文: [https://www.geeksforgeeks.org/sum-series-alternate-signed-squares-ap/](https://www.geeksforgeeks.org/sum-series-alternate-signed-squares-ap/)

我们得到整数 `n`，在下一行中还有 `2*n` 个整数，它们表示算术级数 `a1`，`a2`，`a3`…`a2n`，它们在 AP 中。我们需要找到 `a1^2 – a2^2 + a3^2… + a2n-1^2 – a2n^2`。

**例:**

```
Input : n = 2
        a[] = {1 2 3 4}
Output : -10
Explanation : 1^2 - 2^2 + 
3^2 - 4^2 = -10.

Input : n = 3
        a[] = {2 4 6 8 10 12}
Output : -84
```

## 简单方法

我们一个接一个地求出偶数项为负，奇数项为正的级数的平方和。

### C++

```cpp
// CPP program to find sum of
// series with alternate signed
// square AP sums.
#include <bits/stdc++.h>
using namespace std;

// function to calculate series sum
int seiresSum(int n, int a[])
{
    int res = 0;
    for (int i = 0; i < 2 * n; i++)
    {
        if (i % 2 == 0)
            res += a[i] * a[i];
        else
            res -= a[i] * a[i];
    }
    return res;
}

// Driver Code
int main()
{
    int n = 2;
    int a[] = { 1, 2, 3, 4 };
    cout << seiresSum(n, a);
    return 0;
}
```

### Java

```java
// Java program to find sum of
// series with alternate signed
// square AP sums.
import java.io.*;
import java.lang.*;
import java.util.*;

class GFG
{

    // function to calculate
    // series sum
    static int seiresSum(int n,
                         int[] a)
    {
        int res = 0, i;
        for (i = 0; i < 2 * n; i++)
        {
            if (i % 2 == 0)
                res += a[i] * a[i];
            else
                res -= a[i] * a[i];
        }
        return res;
    }

    // Driver code
    public static void main(String args[])
    {
        int n = 2;
        int a[] = { 1, 2, 3, 4 };
        System.out.println(seiresSum(n, a));
    }
}
```

### Python 3

```python
# Python3 program to find sum
# of series with alternate signed 
# square AP sums.

# Function to calculate series sum
def seiresSum(n, a):
    res = 0

    for i in range(0, 2 * n):
        if (i % 2 == 0):
            res += a[i] * a[i]
        else:
            res -= a[i] * a[i]
    return res

# Driver code
n = 2
a = [1, 2, 3, 4]
print(seiresSum(n, a))

# This code is contributed by Ajit.
```

### C#

```csharp
// C# program to find sum of
// series with alternate signed 
// square AP sums.
using System;

class GFG
{

    // function to calculate
    // series sum
    static int seiresSum(int n,
                         int[] a)
    {
        int res = 0, i;
        for (i = 0; i < 2 * n; i++)
        {
            if (i % 2 == 0)
                res += a[i] * a[i];
            else
                res -= a[i] * a[i];
        }
        return res;
    }

    // Driver code
    public static void Main()
    {
        int n = 2;
        int []a = { 1, 2, 3, 4 };
        Console.WriteLine(seiresSum(n, a));
    }
}

//This code is contributed by vt_m.
```

### PHP

```php
<?php
// PHP program to find sum of
// series with alternate signed 
// square AP sums.

// function to calculate
// series sum
function seiresSum($n, $a)
{
    $res = 0;
    for ( $i = 0; $i < 2 * $n; $i++)
    {
        if ($i % 2 == 0)
            $res += $a[$i] * $a[$i];
        else
            $res -= $a[$i] * $a[$i];
    }
    return $res;
}

    // Driver Code
    $n = 2;
    $a = array(1, 2, 3, 4);
    echo seiresSum($n, $a);

// This code is contributed by anuj_67.
?>
```

### JavaScript

```javascript
<script>
// JavaScript program to find sum of
// series with alternate signed

    // function to calculate
    // series sum
    function seiresSum(n, a)
    {
        let res = 0, i;
        for (i = 0; i < 2 * n; i++)
        {
            if (i % 2 == 0)
                res += a[i] * a[i];
            else
                res -= a[i] * a[i];
        }
        return res;
    }

// Driver Code

        let n = 2;
        let a = [1, 2, 3, 4];
        document.write(seiresSum(n, a));

// This code is contributed by code_hunt.
</script>
```

**Output :**

```
-10
```