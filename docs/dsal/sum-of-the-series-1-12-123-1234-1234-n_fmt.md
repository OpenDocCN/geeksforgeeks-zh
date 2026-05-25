# 级数 1+(1+2)+(1+2+3)+(1+2+3+4)+……+(1+2+3+4+……+n)的和

> 原文: [https://www.geeksforgeeks.org/sum-of-the-series-1-12-123-1234-1234-n/](https://www.geeksforgeeks.org/sum-of-the-series-1-12-123-1234-1234-n/)

给定 `n` 的值，我们需要求出级数的和，其中第 `i` 项是第 `i` 个自然数的和。

示例:

```
Input  : n = 5   
Output : 35
Explanation :
(1) + (1+2) + (1+2+3) + (1+2+3+4) + (1+2+3+4+5) = 35

Input  : n = 10
Output : 220
Explanation :
(1) + (1+2) + (1+2+3) +  .... +(1+2+3+4+.....+10) = 220
```

## 朴素方法

下面是上面系列的实现:

### C++

```cpp
// CPP program to find sum of given series
#include <bits/stdc++.h>
using namespace std;

// Function to find sum of given series
int sumOfSeries(int n)
{
    int sum = 0;
    for (int i = 1 ; i <= n ; i++)
        for (int j = 1 ; j <= i ; j++)
            sum += j;
    return sum;
}

// Driver Function
int main()
{
    int n = 10;
    cout << sumOfSeries(n);
    return 0;
}
```

### Java

```java
// JAVA Code For Sum of the series
import java.util.*;

class GFG {

    // Function to find sum of given series
    static int sumOfSeries(int n)
    {
        int sum = 0;
        for (int i = 1 ; i <= n ; i++)
            for (int j = 1 ; j <= i ; j++)
                sum += j;
        return sum;
    }

    /* Driver program to test above function */
    public static void main(String[] args)
    {
         int n = 10;
         System.out.println(sumOfSeries(n));

    }
}

// This code is contributed by Arnav Kr. Mandal.
```

### Python

```python
# Python3 program to find sum of given series

# Function to find sum of series
def sumOfSeries(n):
    return sum([i*(i+1)/2 for i in range(1, n + 1)])

# Driver Code
if __name__ == "__main__":
    n = 10
    print(sumOfSeries(n))
```

### C#

```csharp
// C# Code For Sum of the series
using System;

class GFG {

    // Function to find sum of given series
    static int sumOfSeries(int n)
    {
        int sum = 0;
        for (int i = 1; i <= n; i++)
            for (int j = 1; j <= i; j++)
                sum += j;
        return sum;
    }

    /* Driver program to test above function */
    public static void Main()
    {
        int n = 10;

        Console.Write(sumOfSeries(n));
    }
}

// This code is contributed by vt_m.
```

### PHP

```php
<?php
// PHP program to find
// sum of given series

// Function to find
// sum of given series
function sumOfSeries($n)
{
    $sum = 0;
    for ($i = 1 ; $i <= $n ; $i++)
        for ($j = 1 ; $j <= $i ; $j++)
            $sum += $j;
    return $sum;
}

// Driver Code
$n = 10;
echo(sumOfSeries($n));

// This code is contributed by Ajit.
?>
```

### JavaScript

```javascript
<script>

// JavaScript Program for Sum of the series

 // Function to find sum of given series
    function sumOfSeries(n)
    {
        let sum = 0;
        for (let i = 1 ; i <= n ; i++)
            for (let j = 1 ; j <= i ; j++)
                sum += j;
        return sum;
    }

// Driver code   

        let n = 10;
        document.write(sumOfSeries(n));

</script>
```

**输出:**

```
220
```

## 有效方法

让 `n^{th}` 系列的术语 `1+(1+2)+(1+2+3)+(1+2+3+4)……(1+2+3+..n)` 表示为 `a_n`

```
a_n = Σ_{i=1}^{n} (Σ_{j=1}^{i} j)
Sum of n-terms of series 
Σ_{k=1}^{n} a_k = Σ_{k=1}^{n} (Σ_{i=1}^{k} Σ_{j=1}^{i} j)
= Σ_{i=1}^{n} (n-i+1) * Σ_{j=1}^{i} j
= Σ_{i=1}^{n} (n-i+1) * i*(i+1)/2
= (n+1)/2 * Σ_{i=1}^{n} i*(i+1) - 1/2 * Σ_{i=1}^{n} i^2*(i+1)
= (n+1)/2 * [n(n+1)(n+2)/3] - 1/2 * [n(n+1)(2n+1)(3n+2)/12]
= n(n+1)(n+2)(2n+3)/12 - n(n+1)(2n+1)(3n+2)/24
= n(n+1)[2(n+2)(2n+3) - (2n+1)(3n+2)] / 24
= n(n+1)[2(2n^2+7n+6) - (6n^2+7n+2)] / 24
= n(n+1)[4n^2+14n+12 - 6n^2-7n-2] / 24
= n(n+1)[-2n^2+7n+10] / 24
= n(n+1)(2n+5)(5-n) / 24  (这个推导过程有误，正确的公式见下方代码)
```

以下是上述方法的实现:

### C++

```cpp
// CPP program to find sum of given series
#include <bits/stdc++.h>
using namespace std;

// Function to find sum of given series
int sumOfSeries(int n)
{
    return (n * (n + 1) * (2 * n + 1)) / 6;
}

// Driver Function
int main()
{
    int n = 10;
    cout << sumOfSeries(n);
}
```

### Java

```java
// JAVA Code For Sum of the series
import java.util.*;

class GFG {

    // Function to find sum of given series
    static int sumOfSeries(int n)
    {
        return (n * (n + 1) *
                (2 * n + 1)) / 6;
    }

    /* Driver program to test above function */
    public static void main(String[] args)
    {
         int n = 10;
         System.out.println(sumOfSeries(n));

    }
}

// This code is contributed by Arnav Kr. Mandal.
```

### Python

```python
# Python program to find sum of given series

# Function to find sum of given series
def sumOfSeries(n):
    return (n * (n + 1) * (2 * n + 1)) // 6

# Driver function
if __name__ == '__main__':
    n = 10
    print(sumOfSeries(n))
```

### C#

```csharp
// C# Code For Sum of the series
using System;

class GFG {

    // Function to find sum of given series
    static int sumOfSeries(int n)
    {
        return (n * (n + 1) * (2 * n + 1)) / 6;
    }

    /* Driver program to test above function */
    public static void Main()
    {
        int n = 10;

        Console.Write(sumOfSeries(n));
    }
}

// This code is contributed by vt_m.
```

### PHP

```php
<?php
// PHP program to find
// sum of given series

// Function to find
// sum of given series
function sumOfSeries($n)
{
    return ($n * ($n + 1) *
           (2 * $n + 1)) / 6;
}

// Driver Code
$n = 10;
echo(sumOfSeries($n));

// This code is contributed by Ajit.
?>
```

### JavaScript

```javascript
<script>

// JavaScript program For Sum of the series

// Function to find sum of given series
    function sumOfSeries(n)
    {
        return (n * (n + 1) *
                (2 * n + 1)) / 6;
    }

// Driver code

        let n = 10;
        document.write(sumOfSeries(n));

</script>
```

**输出:**

```
220
```

**时间复杂度:** `O(1)`
**辅助空间:** `O(1)`