# 程序打印给定第 n 项的总和

> 原文: [https://www.geeksforgeeks.org/program-print-sum-given-nth-term/](https://www.geeksforgeeks.org/program-print-sum-given-nth-term/)

给定 `n` 的值，你必须找到数列的和，其中数列的第 `n` 项由下式给出：
`Tn = n² – (n–1)²`

**例：**

```
Input : 3
Output : 9

Explanation: So here the term of the sequence upto n = 3 are: 
             1, 3, 5 And hence the required sum is = 1 + 3 + 5 = 9

Input : 6
Output : 36
```

## 简单方法

只需用一个循环，计算每个项的和，打印和即可。

### C++

```cpp
// CPP program to find summation of series
#include <bits/stdc++.h>
using namespace std;

int summingSeries(long n)
{
    // use of loop to calculate
    // sum of each term
    int S = 0;
    for (int i = 1; i <= n; i++)
        S += i * i - (i - 1) * (i - 1);

    return S;
}

// Driver Code
int main()
{
    int n = 100;
    cout << "The sum of n term is: "
        << summingSeries(n) << endl;
    return 0;
}
```

### Java

```java
// JAVA program to find summation of series
import java.io.*;
import java.math.*;
import java.text.*;
import java.util.*;
import java.util.regex.*;

class GFG
{

    // function to calculate sum of series
    static int summingSeries(long n)
    {
        // use of loop to calculate
        // sum of each term
        int S = 0;
        for (i = 1; i <= n; i++)
            S += i * i - (i - 1) * (i - 1);    

        return S;
    }

    // Driver code
    public static void main(String[] args)
    {
        int n = 100;
        System.out.println("The sum of n term is: " +
                            summingSeries(n));
    }
}
```

### Python 3

```python
# Python3 program to find summation
# of series

def summingSeries(n):

    # use of loop to calculate
    # sum of each term
    S = 0
    for i in range(1, n+1):
        S += i * i - (i - 1) * (i - 1)

    return S

# Driver Code
n = 100
print("The sum of n term is: ",
           summingSeries(n), sep = "")
# This code is contributed by Smitha.
```

### C#

```csharp
// C# program to illustrate...
// Summation of series
using System;

class GFG
{

    // function to calculate sum of series
    static int summingSeries(long n)
    {

        // Using the pow function calculate
        // the sum of the series
        return (int)Math.Pow(n, 2);
    }

    // Driver code
    public static void Main(String[] args)
    {
        int n = 100;
        Console.Write("The sum of n term is: " +
                        summingSeries(n));
    }
}

// This code contribute by Parashar...
```

### PHP

```php
<?php
// PHP program to find
// summation of series

function summingSeries( $n)
{

    // use of loop to calculate
    // sum of each term
    $S = 0;
    for ($i = 1; $i <= $n; $i++)
         $S += $i * $i - ($i - 1) *
                       ($i - 1);

    return $S;
}

// Driver Code
$n = 100;
echo "The sum of n term is: ",
summingSeries($n) ;

// This code contribute by vt_m.
?>
```

### JavaScript

```javascript
<script>
// Javascript program to find summation of series

function summingSeries(n)
{
    // use of loop to calculate
    // sum of each term
    let S = 0;
    for (let i = 1; i <= n; i++)
        S += i * i - (i - 1) * (i - 1);

    return S;
}

// Driver Code
let n = 100;
document.write("The sum of n term is: " + summingSeries(n));

// This code is contributed by rishavmahato348.
</script>
```

**输出：**

```
The sum of n term is: 10000
```

**时间复杂度–** `O(N)`
**空间复杂度–** `O(1)`

## 高效方法

运用数学方法可以更高效的解决这个问题。

> `TN = N² – (N-1)²`
> 数列的和由 `(S) = SUM( Tn )` 给出。
> 让我们举个例子，如果 `N = 4`，这意味着数列中应该有 4 个项。
> 所以：
> 第 1 项 = `1² – (1–1)²`
> 第 2 项 = `2² – (2–1)²`
> 第 3 项 = `3² – (3–1)²`
> 第 4 项 = `4² – (3–1)²`
> `S = (1–0) + (4–1) + (9–4) + (16–9)`
> `= 16`
> 由此我们注意到 1，4，9 从系列中被取消，只剩下 16 个等于 `N` 的平方。
> 所以从上面的系列中我们注意到每个术语从下一个术语中被取消，只剩下最后一个术语等于 `N²`。

### C++

```cpp
// CPP program to illustrate...
// Summation of series

#include <bits/stdc++.h>
using namespace std;

int summingSeries(long n)
{
    // Sum of n terms is n^2
    return pow(n, 2);
}

// Driver Code
int main()
{
    int n = 100;
    cout << "The sum of n term is: "
         << summingSeries(n) << endl;
    return 0;
}
```

### Java

```java
// JAVA program to illustrate...
// Summation of series

import java.io.*;
import java.math.*;
import java.text.*;
import java.util.*;
import java.util.regex.*;

class GFG
{

    // function to calculate sum of series
    static int summingSeries(long n)
    {

        // Using the pow function calculate
        // the sum of the series
        return (int)Math.pow(n, 2);
    }

    // Driver code
    public static void main(String[] args)
    {
        int n = 100;
        System.out.println("The sum of n term is: " +
                            summingSeries(n));
    }
}
```

### Python 3

```python
# Python3 program to illustrate...
# Summation of series
import math

def summingSeries(n):

    # Sum of n terms is  n^2
    return math.pow(n, 2)

# Driver Code
n = 100
print ("The sum of n term is: ",
        summingSeries(n))
# This code is contributed by mits.
```

### C#

```csharp
// C# program to illustrate...
// Summation of series
using System;

class GFG
{
    // function to calculate sum of series
    static int summingSeries(long n)
    {
        // Using the pow function calculate
        // the sum of the series
        return (int)Math.Pow(n, 2);
    }

    // Driver code
    public static void Main()
    {
        int n = 100;
           Console.Write("The sum of n term is: " +
                          summingSeries(n));
    }
}

// This code is contributed by nitin mittal.
```

### PHP

```php
<?php
// PHP program to illustrate...
// Summation of series

function summingSeries($n)
{
    // Sum of n terms is  n^2
    return pow($n, 2);
}

// Driver Code
$n = 100;
echo "The sum of n term is: ",
summingSeries($n);

// This code contribute by vt_m.
?>
```

### JavaScript

```javascript
<script>
// Javascript program to illustrate...
// Summation of series

function summingSeries(n)
{
    // Sum of n terms is n^2
    return Math.pow(n, 2);
}

// Driver Code
let n = 100;
document.write("The sum of n term is: "
    + summingSeries(n) + "<br>");

    // This code is contributed by subham348.
</script>
```

**输出：**

```
The sum of n term is: 10000
```

**时间复杂度–** `O(1)`
**空间复杂度–** `O(1)`