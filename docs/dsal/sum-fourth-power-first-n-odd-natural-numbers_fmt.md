# 前 n 个奇数自然数的四次幂之和

> 原文: [https://www.geeksforgeeks.org/sum-fourth-power-first-n-odd-natural-numbers/](https://www.geeksforgeeks.org/sum-fourth-power-first-n-odd-natural-numbers/)

写一个程序求前 `n` 个奇数自然数的四次幂之和。
`1^4 + 3^4 + 5^4 + 7^4 + 9^4 + 11^4 …… + (2n-1)^4`。

示例:

```
Input  :   3
Output :   707
1^4 + 3^4 + 5^4 =  707
Input  :   6
Output :   24310
1^4 + 3^4 + 5^4 + 7^4 + 9^4 + 11^4
```

## 天真的方法

在这个简单的寻找前 `n` 个奇数自然数的四次方的方法中，迭代一个从 `1` 到 `n` 次的循环，结果存储在变量 `sum` 中。
例如：`n=3` 那么，`(1 * 1 * 1 * 1) + (3 * 3 * 3 * 3) + (5 * 5 * 5 * 5) = 707`。

### C++

```cpp
// CPP Program to find the sum of fourth powers
// of first n odd natural numbers
#include <bits/stdc++.h>
using namespace std;

// calculate the sum of fourth power of first
// n odd natural numbers
long long int oddNumSum(int n)
{
    int j = 0;
    long long int sum = 0;
    for (int i = 1; i <= n; i++) {
        j = (2 * i - 1);
        sum = sum + (j * j * j * j);
    }
    return sum;
}

// Driven Program
int main()
{
    int n = 6;
    cout << oddNumSum(n) << endl;
    return 0;
}
```

### Java

```java
// Java Program to find the
// sum of fourth powers of
// first n odd natural numbers
import java.io.*;

class GFG {

    // calculate the sum of
    // fourth power of first
    // n odd natural numbers
    static long oddNumSum(int n)
    {
        int j = 0;
        long sum = 0;
        for (int i = 1; i <= n; i++) {
            j = (2 * i - 1);
            sum = sum + (j * j * j * j);
        }
        return sum;
    }

    // Driven Program
    public static void main(String args[])
    {
        int n = 6;
        System.out.println(oddNumSum(n));
    }
}

// This code is contributed
// by Nikita tiwari.
```

### Python 3

```python
# Python 3 Program to find the
# sum of fourth powers of
# first n odd natural numbers

# calculate the sum of
# fourth power of first
# n odd natural numbers
def oddNumSum(n) :
    j = 0
    sm = 0
    for i in range(1, n + 1) :
        j = (2 * i - 1)
        sm = sm + (j * j * j * j)

    return sm

# Driven Program
n = 6;
print(oddNumSum(n))

# This code is contributed
# by Nikita tiwari.
```

### C#

```csharp
// C# Program to find the
// sum of fourth powers of
// first n odd natural numbers
using System;

class GFG {

    // calculate the sum of
    // fourth power of first
    // n odd natural numbers
    static long oddNumSum(int n)
    {
        int j = 0;
        long sum = 0;
        for (int i = 1; i <= n; i++) {
            j = (2 * i - 1);
            sum = sum + (j * j * j * j);
        }
        return sum;
    }

    // Driven Program
    public static void Main()
    {
        int n = 6;
        Console.Write(oddNumSum(n));
    }
}

// This code is contributed by
// vt_m.
```

### PHP

```php
<?php
// PHP Program to find the
// sum of fourth powers
// of first n odd natural
// numbers

// calculate the sum of
// fourth power of first
// n odd natural numbers
function oddNumSum($n)
{
    $j = 0;
    $sum = 0;
    for ($i = 1; $i <= $n; $i++)
    {
        $j = (2 * $i - 1);
        $sum = $sum + ($j * $j * $j * $j);
    }
    return $sum;
}

// Driver Code
$n = 6;
echo(oddNumSum($n));

// This code is contributed by Ajit.
?>
```

### JavaScript

```javascript
<script>

// javascript Program to find the sum of fourth powers
// of first n odd natural numbers

// calculate the sum of fourth power of first
// n odd natural numbers
function oddNumSum( n)
{
    let j = 0;
    let sum = 0;
    for (let i = 1; i <= n; i++) {
        j = (2 * i - 1);
        sum = sum + (j * j * j * j);
    }
    return sum;
}

// Driven Program

    let n = 6;
     document.write(oddNumSum(n));

// This code contributed by aashish1995

</script>
```

**输出:**

```
24310
```

**时间复杂度:** `O(N)`

## 有效方法

一个有效的解决方案是使用直接的数学公式，即:

> [前 n 个自然数的四次方和](https://www.geeksforgeeks.org/sum-fourth-powers-first-n-natural-numbers/) = `(1^4 + 2^4 + 3^4 + ………… + n^4)`
> = `(n(n+1)(2n+1)(3n^2+3n-1))/30`
> [前 n 个偶数自然数的四次方和](https://www.geeksforgeeks.org/sum-of-fourth-power-of-first-n-even-natural-numbers/) = `(2^4 + 4^4 + 6^4 + ………… + (2n)^4)`
> 我们需要奇数，所以我们减去
> 前 `n` 个奇数自然数的四次方和 = 前 `2n` 个自然数的四次方和 – 前 `n` 个偶数自然数的四次方和
> = `(1^4 + 2^4 + 3^4 + …… + (2n)^4) – (2^4 + 4^4 + 6^4 + ………… + (2n)^4)`
> = `(1^4 + 3^4 + 5^4 + ………… + (2n-1)^4)`
> 推导公式
> = `(2n(2n+1)(4n+1)(12n^2+6n-1))/30 – ( 8(n(n+1)(2n+1)(3n^2+3n-1))/30 )`
> = `n(2n+1)/15[24n^3 - 12n^2 - 14n + 7]`

```
    Sum of fourth power of first n odd numbers =  n(2n+1)/15[24n^3 - 12n^2 - 14n + 7]
```

### C++

```cpp
// CPP Program to find the sum of fourth powers
// of first n odd natural numbers
#include <bits/stdc++.h>
using namespace std;

// calculate the sum of fourth power of first
// n odd natural numbers
long long int oddNumSum(int n)
{
    return (n * (2 * n + 1) *
    (24 * n * n * n - 12 * n
    * n - 14 * n + 7)) / 15;
}

// Driven Program
int main()
{
    int n = 4;
    cout << oddNumSum(n) << endl;
    return 0;
}
```

### Java

```java
// Java Program to find the sum of
// fourth powers of first n odd
// natural numbers
class GFG {

    // calculate the sum of fourth
    // power of first n odd natural
    // numbers
    static long oddNumSum(int n)
    {
        return (n * (2 * n + 1) *
         (24 * n * n * n - 12 * n
          * n - 14 * n + 7)) / 15;
    }

    // Driven Program
    public static void main(String[] args)
    {
        int n = 4;

        System.out.println(oddNumSum(n));
    }
}

// This code is contributed by
// Smitha Dinesh Semwal.
```

### Python 3

```python
# Python 3 Program to find the
# sum of fourth powers of first
# n odd natural numbers

# calculate the sum of fourth
# power of first n odd natural
#numbers
def oddNumSum(n):

    return (n * (2 * n + 1) *
      (24 * n * n * n - 12 * n
      * n - 14 * n + 7)) / 15

# Driven Program
n = 4
print(int(oddNumSum(n)))

# This code is contributed by
# Smitha Dinesh Semwal.
```

### C#

```csharp
// C# Program to find the sum of
// fourth powers of first n
// odd natural numbers
using System;

class GFG {

    // calculate the sum of fourth
    // power of first n odd
    // natural numbers
    static long oddNumSum(int n)
    {
        return (n * (2 * n + 1) *
        (24 * n * n * n - 12 * n
        * n - 14 * n + 7)) / 15;
    }

    // Driven Program
    public static void Main()
    {
        int n = 4;
        Console.Write(oddNumSum(n));
    }
}

// This code is contributed by
// vt_m.
```

### PHP

```php
<?php
// PHP Program to find the
// sum of fourth powers
// of first n odd natural
// numbers

// calculate the sum of
// fourth power of first
// n odd natural numbers
function oddNumSum($n)
{
    return ($n * (2 * $n + 1) *
           (24 * $n * $n * $n -
            12 * $n * $n - 14 *
            $n + 7)) / 15;
}

// Driver Code
$n = 4;
echo(oddNumSum($n));

// This code is contributed by Ajit.
?>
```

### JavaScript

```javascript
<script>
// javascript Program to find the sum of
// fourth powers of first n odd
// natural numbers

// calculate the sum of fourth
// power of first n odd natural
// numbers
function oddNumSum(n)
{
    return (n * (2 * n + 1) *
     (24 * n * n * n - 12 * n
      * n - 14 * n + 7)) / 15;
}

// Driven Program
var n = 4;

document.write(oddNumSum(n));

// This code is contributed by Amit Katiyar
</script>
```

**输出:**

```
1368
```

**时间复杂度:** `O(1)`