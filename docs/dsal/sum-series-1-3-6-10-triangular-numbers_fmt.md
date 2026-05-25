# 数列 1、3、6、10 的和……(三角数)

> 原文: [https://www.geeksforgeeks.org/sum-series-1-3-6-10-triangular-numbers/](https://www.geeksforgeeks.org/sum-series-1-3-6-10-triangular-numbers/)

给定 `n`，数列中元素个数，求数列 1，3，6，10…n 的和，数列主要表示[三角数](https://www.geeksforgeeks.org/triangular-numbers/)。

示例:

```
Input: 2
Output: 4
Explanation: 1 + 3 = 4

Input: 4
Output: 20
Explanation: 1 + 3 + 6 + 10 = 20
```

## 简单的解决方法

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
// and then find its sum

// Function to find the sum of series
function seriesSum(n)
{
    let sum = 0;
    for (let i = 1; i <= n; i++)
       sum += i * ((i + 1) / 2);
    return sum;
}

// Driver code
let n = 4;
  document.write(seriesSum(n)) ;

// This code is contributed by aashish1995

</script>
```

输出:

```
20
```

时间复杂度: O(n)

## 高效的解决方案

一个高效的解决方案是使用直接公式 `n(n+1)(n+2)/6`。

```
Let g(i) be i-th triangular number.
g(1) = 1
g(2) = 3
g(3) = 6
g(n) = n(n+1)/2
```

```
Let f(n) be the sum of the triangular
numbers 1 through n.
f(n) = g(1) + g(2) + ... + g(n)

Then:
f(n) = n(n+1)(n+2)/6
```

我们如何证明这一点？我们可以通过归纳法来证明。也就是证明两件事:

1.  对于某些 `n` (在这种情况下，`n = 1`)来说是真的。
2.  如果 `n` 是真的，那么 `n+1` 也是真的。

这使我们可以得出结论，所有 `n >= 1` 都是真的。

```
Now 1) is easy. We know that f(1) = g(1) 
= 1. So it's true for n = 1.

Now for 2). Suppose it's true for n. 
Consider f(n+1). We have:
f(n+1) = g(1) + g(2) + ... + g(n) + g(n+1) 
       = f(n) + g(n+1)

Using our assumption f(n) = n(n+1)(n+2)/6 
and g(n+1) = (n+1)(n+2)/2, we have:
f(n+1) = n(n+1)(n+2)/6 + (n+1)(n+2)/2
       = n(n+1)(n+2)/6 + 3(n+1)(n+2)/6
       = (n+1)(n+2)(n+3)/6
Therefore, f(n) = n(n+1)(n+2)/6
```

以下是上述方法的实现:

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
/* javascript program to find sum
 series 1, 3, 6, 10, 15, 21...
and then find its sum*/

// Function to find the sum of series
function seriesSum( n)
{
    return (n * (n + 1) * (n + 2)) / 6;
}

// Driver code
    let n = 4;
    document.write(seriesSum(n));

// This code is contributed by todaysgaurav

</script>
```

输出:

```
20
```

时间复杂度: O(1)