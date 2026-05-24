# 检查两个正方形的面积差是否为质数

> 原文: [https://www.geeksforgeeks.org/check-if-difference-of-areas-of-two-squares-is-prime/](https://www.geeksforgeeks.org/check-if-difference-of-areas-of-two-squares-is-prime/)

给定两个边长为 `a` 和 `b` 的正方形 (`a > b`)。任务是检查它们的面积差是否是质数。这里边长可以很大 (`1 < b < a < 10^12`)。

## 示例

```
Input : a = 6, b = 5
Output : Yes

Input : a = 61690850361, b = 24777622630    
Output : No
```

## 进场

因为边长是 `a` 和 `b`。因此，它们的面积之差 = (`a^2 – b^2`)，可以表示为 (`a–b`)(`a+b`)。当且仅当 `a–b = 1` 且 `a + b` 是质数时，此为质数。由于 `a+b` 最多为 `2×10^12`，我们可以用试除法来检查它的素性。

以下是上述思路的实现：

### C++

```cpp
// C++ program to check if difference of
// areas of two squares is prime or not
// when side length is large

#include <bits/stdc++.h>
using namespace std;

// Function to check if number is prime
bool isPrime(long long int n)
{
    // Corner cases
    if (n <= 1)
        return false;
    if (n <= 3)
        return true;

    // This is checked so that we can skip
    // middle five numbers in below loop
    if (n % 2 == 0 || n % 3 == 0)
        return false;

    for (long long int i = 5; i * i <= n; i = i + 6)
        if (n % i == 0 || n % (i + 2) == 0)
            return false;

    return true;
}

// Function to check if difference of areas of
// square is prime
bool isDiffPrime(long long int a, long long int b)
{
    // when a+b is prime and a-b is 1
    if (isPrime(a + b) && a - b == 1)
        return true;
    else
        return false;
}

// Driver code
int main()
{
    long long int a = 6, b = 5;

    if (isDiffPrime(a, b))
        cout << "Yes";
    else
        cout << "No";

    return 0;
}
```

### Java

```java
// Java program to check if difference
// of areas of two squares is prime or
// not when side length is large
class GFG
{

// Function to check if number
// is prime
static boolean isPrime(long n)
{
    // Corner cases
    if (n <= 1)
        return false;
    if (n <= 3)
        return true;

    // This is checked so that we can skip
    // middle five numbers in below loop
    if (n % 2 == 0 || n % 3 == 0)
        return false;

    for (long i = 5; i * i <= n; i = i + 6)
        if (n % i == 0 || n % (i + 2) == 0)
            return false;

    return true;
}

// Function to check if difference
// of areas of square is prime
static boolean isDiffPrime(long a, long b)
{
    // when a+b is prime and a-b is 1
    if (isPrime(a + b) && a - b == 1)
        return true;
    else
        return false;
}

// Driver code
public static void main(String []args)
{
    long a = 6, b = 5;

    if (isDiffPrime(a, b))
        System.out.println("Yes");
    else
        System.out.println("No");
}
}

// This code is contributed by ihritik
```

### C\#

```csharp
// C# program to check if difference
// of areas of two squares is prime
// or not when side length is large
using System;

class GFG
{
// Function to check if number
// is prime
static bool isPrime(long n)
{
    // Corner cases
    if (n <= 1)
        return false;
    if (n <= 3)
        return true;

    // This is checked so that we
    // can skip middle five numbers
    // in below loop
    if (n % 2 == 0 || n % 3 == 0)
        return false;

    for (long i = 5;
              i * i <= n; i = i + 6)
        if (n % i == 0 || n % (i + 2) == 0)
            return false;

    return true;
}

// Function to check if difference
// of areas of square is prime
static bool isDiffPrime(long a, long b)
{
    // when a+b is prime and a-b is 1
    if (isPrime(a + b) && a - b == 1)
        return true;
    else
        return false;
}

// Driver code
public static void Main()
{
    long a = 6, b = 5;

    if (isDiffPrime(a, b))
        Console.WriteLine("Yes");
    else
        Console.WriteLine("No");
}
}

// This code is contributed by ihritik
```

### Python 3

```python
# Python3 program to check if
# difference of areas of two
# squares is prime or not when
# side length is large

def isPrime(n) :

    # Corner cases
    if (n <= 1) :
        return False
    if (n <= 3) :
        return True

    # This is checked so that we 
    # can skip middle five numbers
    # in below loop
    if (n % 2 == 0 or n % 3 == 0) :
        return False

    i = 5
    while(i * i <= n) :
        if (n % i == 0 or n % (i + 2) == 0) :
            return False
        i = i + 6

    return True

# Function to check if difference
# of areas of square is prime
def isDiffPrime(a, b):

    # when a+b is prime and a-b is 1
    if (isPrime(a + b) and a - b == 1):
        return True
    else:
        return False

# Driver code
a = 6
b = 5

if (isDiffPrime(a, b)):
    print("Yes")
else:
    print("No")

# This code is contributed by ihritik
```

### PHP

```php
<?php
// PHP program to check if difference
// of areas of two squares is prime
// or not when side length is large
function isPrime($n)
{

    // Corner cases
    if ($n <= 1)
        return false;
    if ($n <= 3)
        return true;

    // This is checked so that we
    // can skip middle five numbers
    // in below loop
    if ($n % 2 == 0 || $n % 3 == 0)
        return false;

    for($i = 5; $i * $i <= $n;
                $i = $i + 6)
        if ($n % $i == 0 ||
            $n % ($i + 2) == 0)
        return false;

    return true;
}

// Function to check if difference
// of areas of square is prime
function isDiffPrime($a, $b)
{
    # when a+b is prime and a-b is 1
    if (isPrime($a + $b) &&
                $a - $b == 1)
        return true;
    else
        return false;

}

// Driver code
$a = 6;
$b = 5;

if (isDiffPrime($a, $b))
    echo "Yes";
else
    echo "No";

// This code is contributed by ihritik
?>
```

### JavaScript

```javascript
<script>
// Javascript program to check if difference
// of areas of two squares is prime
// or not when side length is large
function isPrime(n)
{

    // Corner cases
    if (n <= 1)
        return false;
    if (n <= 3)
        return true;

    // This is checked so that we
    // can skip middle five numbers
    // in below loop
    if (n % 2 == 0 || n % 3 == 0)
        return false;

    for(let i = 5; i * i <= n;
                i = i + 6)
        if (n % i == 0 ||
            n % (i + 2) == 0)
        return false;

    return true;
}

// Function to check if difference
// of areas of square is prime
function isDiffPrime(a, b)
{
    // when a+b is prime and a-b is 1
    if (isPrime(a + b) &&
                a - b == 1)
        return true;
    else
        return false;

}

// Driver code
let a = 6;
let b = 5;

if (isDiffPrime(a, b))
    document.write("Yes");
else
    document.write("No");

// This code is contributed by Saurabh Jaiswal
</script>
```

**输出：**

```
Yes
```