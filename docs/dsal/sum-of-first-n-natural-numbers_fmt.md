# 前 n 个自然数之和

> 原文：[https://www.geeksforgeeks.org/sum-of-first-n-natural-numbers/](https://www.geeksforgeeks.org/sum-of-first-n-natural-numbers/)

给定正整数 `n`。任务是求前 `n` 个自然数之和的和。

示例：

```
Input : n = 3
Output : 10
Sum of first natural number: 1
Sum of first and second natural number: 1 + 2 = 3
Sum of first, second and third natural number = 1 + 2 + 3 = 6
Sum of sum of first three natural number = 1 + 3 + 6 = 10

Input : n = 2
Output : 4
```

## 简单解决方案

一个简单的解决方法就是一个个加三角数。

### C++

```cpp
/* CPP program to find sum
 series 1, 3, 6, 10, 15, 21...
and then find its sum*/
#include <iostream>
using namespace std;

// Function to find the sum of series
int seriesSum(int n)
{
    int sum = 0;
    for (int i=1; i<=n; i++)
       sum += i*(i+1)/2;
    return sum;
}

// Driver code
int main()
{
    int n = 4;
    cout << seriesSum(n);
    return 0;
}
```

### Java

```java
// Java program to find sum
// series 1, 3, 6, 10, 15, 21...
// and then find its sum*/
import java.io.*;

class GFG {

    // Function to find the sum of series
    static int seriesSum(int n)
    {
        int sum = 0;
        for (int i = 1; i <= n; i++)
        sum += i * (i + 1) / 2;
        return sum;
    }

    // Driver code
    public static void main (String[] args)
    {
        int n = 4;
        System.out.println(seriesSum(n));

    }
}

// This article is contributed by vt_m
```

### Python 3

```python
# Python3 program to find sum
# series 1, 3, 6, 10, 15, 21...
# and then find its sum.

# Function to find the sum of series
def seriessum(n):

    sum = 0
    for i in range(1, n + 1):
        sum += i * (i + 1) / 2
    return sum

# Driver code
n = 4
print(seriessum(n))

# This code is Contributed by Azkia Anam.
```

### C#

```csharp
// C# program to find sum
// series 1, 3, 6, 10, 15, 21...
// and then find its sum*/
using System;

class GFG {

    // Function to find the sum of series
    static int seriesSum(int n)
    {
        int sum = 0;

        for (int i = 1; i <= n; i++)
            sum += i * (i + 1) / 2;

        return sum;
    }

    // Driver code
    public static void Main()
    {
        int n = 4;

        Console.WriteLine(seriesSum(n));
    }
}

// This article is contributed by vt_m.
```

### PHP

```php
<?php
// PHP program to find sum
// series 1, 3, 6, 10, 15, 21...
// and then find its sum

// Function to find
// the sum of series
function seriesSum($n)
{
    $sum = 0;
    for ($i = 1; $i <= $n; $i++)
        $sum += $i * ($i + 1) / 2;
    return $sum;
}

// Driver code
$n = 4;
echo(seriesSum($n));

// This code is contributed by Ajit.
?>
```

### JavaScript

```javascript
<script>

// javascript program to find sum
// series 1, 3, 6, 10, 15, 21...
// and then find its sum*/

    // Function to find the sum of series
    function seriesSum(n) {
        var sum = 0;
        for (i = 1; i <= n; i++)
            sum += i * ((i + 1) / 2);
        return sum;
    }

    // Driver code

        var n = 4;
        document.write(seriesSum(n));

// This code contributed by Rajput-Ji

</script>
```

**输出:**

```
10
```

时间复杂度：`O(n)`

## 有效解决方案

一个有效的解决方案是使用直接公式 `n(n+1)(n+2)/6`。

数学上，我们需要找到，`σ((i *(i+1))/2)`，其中 `1 <= i <= n`。

那么，让我们求解这个求和：

```
Sum = Σ ((i * (i + 1))/2), where 1 <= i <= n
    = (1/2) * Σ (i * (i + 1))
    = (1/2) * Σ (i2 + i)
    = (1/2) * (Σ i2 + Σ i)

We know Σ i2 = n * (n + 1) * (2*n + 1) / 6 and 
Σ i = n * ( n + 1) / 2.
Substituting the value, we get,
Sum = (1/2) * ((n * (n + 1) * (2*n + 1) / 6) + (n * ( n + 1) / 2))  
    = n * (n + 1)/2 [(2n + 1)/6 + 1/2]
    = n * (n + 1) * (n + 2) / 6
```

以下是上述方法的实现：

### C++

```cpp
/* CPP program to find sum
 series 1, 3, 6, 10, 15, 21...
and then find its sum*/
#include <iostream>
using namespace std;

// Function to find the sum of series
int seriesSum(int n)
{
    return (n * (n + 1) * (n + 2)) / 6;
}

// Driver code
int main()
{
    int n = 4;
    cout << seriesSum(n);
    return 0;
}
```

### Java

```java
// java program to find sum
// series 1, 3, 6, 10, 15, 21...
// and then find its sum
import java.io.*;

class GFG
{
    // Function to find the sum of series
    static int seriesSum(int n)
    {
        return (n * (n + 1) * (n + 2)) / 6;
    }

   // Driver code
    public static void main (String[] args) {

        int n = 4;
        System.out.println( seriesSum(n));

    }
}

// This article is contributed by vt_m
```

### Python 3

```python
# Python 3 program to find sum
# series 1, 3, 6, 10, 15, 21...
# and then find its sum*/

# Function to find the sum of series
def seriesSum(n):

    return int((n * (n + 1) * (n + 2)) / 6)

# Driver code
n = 4
print(seriesSum(n))

# This code is contributed by Smitha.
```

### C#

```csharp
// C# program to find sum
// series 1, 3, 6, 10, 15, 21...
// and then find its sum
using System;

class GFG {

    // Function to find the sum of series
    static int seriesSum(int n)
    {
        return (n * (n + 1) * (n + 2)) / 6;
    }

    // Driver code
    public static void Main()
    {

        int n = 4;

        Console.WriteLine(seriesSum(n));
    }
}

// This code is contributed by vt_m.
```

### PHP

```php
<?php
// PHP program to find sum
// series 1, 3, 6, 10, 15, 21...
// and then find its sum

// Function to find
// the sum of series
function seriesSum($n)
{
    return ($n * ($n + 1) *
           ($n + 2)) / 6;
}

// Driver code
$n = 4;
echo(seriesSum($n));

// This code is contributed by Ajit.
?>
```

### JavaScript

```javascript
<script>
// javascript program to find sum
// series 1, 3, 6, 10, 15, 21...
// and then find its sum

// Function to find the sum of series
function seriesSum(n)
{
    return (n * (n + 1) * (n + 2)) / 6;
}

// Driver code
var n = 4;
document.write( seriesSum(n));

// This code is contributed by shikhasingrajput
</script>
```

输出：

```
10
```

时间复杂度：`O(1)`