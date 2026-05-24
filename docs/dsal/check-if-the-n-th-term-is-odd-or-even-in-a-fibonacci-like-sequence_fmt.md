# 检查第 n 项在斐波那契数列中是奇数还是偶数

> 原文: [https://www.geeksforgeeks.org/check-if-the-n-th-term-is-odd-or-even-in-a-fibonacci-like-sequence/](https://www.geeksforgeeks.org/check-if-the-n-th-term-is-odd-or-even-in-a-fibonacci-like-sequence/)

考虑一个序列 `a_0`，`a_1`，...，`a_n`，其中 `a_i = a_{i-1} + a_{i-2}`。给定 `a_0`，`a_1`，以及正整数 `n`。任务是找出 `a_n` 是奇数还是偶数。
注意，给定的序列类似[斐波那契](https://www.geeksforgeeks.org/program-for-nth-fibonacci-number/)，区别在于前两项可以是任何东西，而不是 0 或 1。

**举例:**

```
Input : a0 = 2, a1 = 4, n =3
Output : Even 
a2 = 6, a3 = 10
And a3 is even.

Input : a0 = 1, a1 = 9, n = 2
Output : Even
```

**方法 1:** 思路是利用数组找到序列，检查第 n 个元素是偶数还是奇数。

## C++

```cpp
// CPP Program to check if the nth is odd or even in a
// sequence where each term is sum of previous two term
#include <bits/stdc++.h>
using namespace std;
#define MAX 100

// Return if the nth term is even or odd.
bool findNature(int a, int b, int n)
{
    int seq[MAX] = { 0 };

    seq[0] = a;
    seq[1] = b;

    for (int i = 2; i <= n; i++)
        seq[i] = seq[i - 1] + seq[i - 2];

    // Return true if odd
    return (seq[n] & 1);
}

// Driven Program
int main()
{
    int a = 2, b = 4;
    int n = 3;

    (findNature(a, b, n) ? (cout << "Odd"
                                 << " ")
                         : (cout << "Even"
                                 << " "));

    return 0;
}
```

## Java

```java
// Java Program to check if
// the nth is odd or even
// in a sequence where each
// term is sum of previous
// two term

// Return if the nth
// term is even or odd.
class GFG
{
public static int findNature(int a,
                             int b, int n)
{
    int[] seq = new int[100];

    seq[0] = a;
    seq[1] = b;

    for (int i = 2; i <= n; i++)
        seq[i] = seq[i - 1] + seq[i - 2];

    // Return true if odd
    if((seq[n] & 1) != 0)
    return 1;
    else
    return 0;
}

// Driver Code
public static void main(String[] args)
{
    int a = 2, b = 4;
    int n = 3;
    if(findNature(a, b, n) == 1)
    System.out.println("Odd ");
    else
    System.out.println("Even ");
}
}

// This code is contributed
// by mits
```

## Python 3

```python
# Python3 Program to check if
# the nth is odd or even in a
# sequence where each term is
# sum of previous two term
MAX = 100;

# Return if the nth
# term is even or odd.
def findNature(a, b, n):
    seq = [0] * MAX;
    seq[0] = a;
    seq[1] = b;

    for i in range(2, n + 1):
        seq[i] = seq[i - 1] + seq[i - 2];

    # Return true if odd
    return (seq[n] & 1);

# Driver Code
a = 2;
b = 4;
n = 3;

if(findNature(a, b, n)):
    print("Odd");
else:
    print("Even");

# This code is contributed by mits
```

## C#

```csharp
// C# Program to check if the
// nth is odd or even in a
// sequence where each term
// is sum of previous two term
using System;

// Return if the nth term
// is even or odd.
class GFG
{
public static int findNature(int a,
                             int b, int n)
{
    int[] seq = new int[100];

    seq[0] = a;
    seq[1] = b;

    for (int i = 2; i <= n; i++)
        seq[i] = seq[i - 1] +
                 seq[i - 2];

    // Return true if odd
    if((seq[n] & 1)!=0)
    return 1;
    else
    return 0;
}

// Driver Code
public static void Main()
{
    int a = 2, b = 4;
    int n = 3;
    if(findNature(a, b, n) == 1)
    Console.Write("Odd ");
    else
    Console.Write("Even ");
}
}

// This code is contributed
// by mits
```

## PHP

```php
<?php
// PHP Program to check if the
// nth is odd or even in a
// sequence where each term is
// sum of previous two term
$MAX = 100;

// Return if the nth
// term is even or odd.
function findNature($a, $b, $n)
{
    global $MAX;
    $seq = array_fill(0,$MAX, 0);

    $seq[0] = $a;
    $seq[1] = $b;

    for ($i = 2; $i <= $n; $i++)
        $seq[$i] = $seq[$i - 1] +
                   $seq[$i - 2];

    // Return true if odd
    return ($seq[$n] & 1);
}

// Driver Code
$a = 2;
$b = 4;
$n = 3;

if(findNature($a, $b, $n))
echo "Odd";
else
echo "Even";

// This code is contributed by mits
?>
```

## JavaScript

```javascript
<script>

// Javascript Program to check if the
// nth is odd or even in a
// sequence where each term is sum
// of previous two term
var MAX = 100;

// Return if the nth term is even or odd.
function findNature(a, b, n)
{
    var seq = Array(MAX).fill(0);

    seq[0] = a;
    seq[1] = b;

    for (var i = 2; i <= n; i++)
        seq[i] = seq[i - 1] + seq[i - 2];

    // Return true if odd
    return (seq[n] & 1);
}

// Driven Program
var a = 2, b = 4;
var n = 3;
(findNature(a, b, n) ? (document.write( "Odd"
                                 + " "))
                     : (document.write( "Even"
                                 + " ")));

</script>
```

**Output:**

```
Even
```

**方法二(高效):**
观察，第 n 项的性质(奇数或偶数)取决于前几项，前几项的性质取决于它们的前几项，最后取决于初始值即 `a_0` 和 `a_1`。
那么，我们有四种可能的情况，`a_0` 和 `a_1`:

**情况 1: 当 `a_0` 和 `a_1` 为偶数时**
在这种情况下，序列中的每个值只会为偶数。

**案例二: 当 `a_0` 和 `a_1` 为奇数**
这种情况下，观察 `a_2` 为偶数，`a_3` 为奇数，`a_4` 为奇数等等。所以，我们可以说 `a_i` 是偶数，如果 `i` 是 `3 * k - 1` 的形式，那么就是奇数。

**案例三: 当 `a_0` 为偶数，`a_1` 为奇数**
这种情况下，观察 `a_2` 为奇数，`a_3` 为偶数，`a_4` 和 `a_5` 为奇数，`a_6` 为偶数等等。所以，我们可以说，`a_i` 就算 `i` 是 3 的倍数也是偶数，否则就是奇数。

**情况 4: 当 `a_0` 是奇数，`a_1` 是偶数**
这种情况下，观察 `a_2` 和 `a_3` 是奇数，`a_4` 是偶数，`a_5` 是奇数等等。所以，我们可以说，`a_i` 就是即使 `i` 是 `3*k + 1` 的形式，`k >= 0`，否则奇数。

以下是本办法的实施:

## C++

```cpp
// CPP Program to check if the nth is odd or even in a
// sequence where each term is sum of previous two term
#include <bits/stdc++.h>
using namespace std;

// Return if the nth term is even or odd.
bool findNature(int a, int b, int n)
{
    if (n == 0)
        return (a & 1);

    if (n == 1)
        return (b & 1);

    // If a is even
    if (!(a & 1)) {

        // If b is even
        if (!(b & 1))
            return false;

        // If b is odd
        else
            return (n % 3 != 0);
    }

    // If a is odd
    else {
        // If b is odd
        if (!(b & 1))
            return ((n - 1) % 3 != 0);

        // If b is eve
        else
            return ((n + 1) % 3 != 0);
    }
}

// Driven Program
int main()
{
    int a = 2, b = 4;
    int n = 3;

    (findNature(a, b, n) ? (cout << "Odd"
                                 << " ")
                         : (cout << "Even"
                                 << " "));

    return 0;
}
```

## Java

```java
// Java Program to check if the nth is odd or even in a
// sequence where each term is sum of previous two term

class GFG{
// Return if the nth term is even or odd.
static boolean findNature(int a, int b, int n)
{
    if (n == 0)
        return (a & 1)==1?true:false;

    if (n == 1)
        return (b & 1)==1?true:false;

    // If a is even
    if ((a & 1)==0) {

        // If b is even
        if ((b & 1)==0)
            return false;

        // If b is odd
        else
            return (n % 3 != 0);
    }

    // If a is odd
    else {
        // If b is odd
        if ((b & 1)==0)
            return ((n - 1) % 3 != 0);

        // If b is eve
        else
            return ((n + 1) % 3 != 0);
    }
}

// Driven Program
public static void main(String[] args)
{
    int a = 2, b = 4;
    int n = 3;

    if(findNature(a, b, n))
    System.out.println("Odd");
    else
    System.out.println("Even");

}
}
// This Code is contributed by mits
```

# 判断序列第n项奇偶性的多语言实现

## Python

```python
# Python3 Program to check if the
# nth is odd or even in a
# sequence where each term is
# sum of previous two term

# Return if the nth
# term is even or odd.
def findNature(a, b, n):
    if (n == 0):
        return (a & 1);

    if (n == 1):
        return (b & 1);

    # If a is even
    if ((a & 1) == 0):

        # If b is even
        if ((b & 1) == 0):
            return False;

        # If b is odd
        else:
            return True if(n % 3 != 0) else False;

    # If a is odd
    else:
        # If b is odd
        if ((b & 1) == 0):
            return True if((n - 1) % 3 != 0) else False;

        # If b is eve
        else:
            return True if((n + 1) % 3 != 0) else False;

# Driver Code
a = 2;
b = 4;
n = 3;

if (findNature(a, b, n) == True):
    print("Odd", end = " ");
else:
    print("Even", end = " ");

# This code is contributed by mits
```

## C\#

```csharp
// C# Program to check if the nth is odd or even in a
// sequence where each term is sum of previous two term

class GFG{
// Return if the nth term is even or odd.
static bool findNature(int a, int b, int n)
{
    if (n == 0)
        return (a & 1)==1?true:false;

    if (n == 1)
        return (b & 1)==1?true:false;

    // If a is even
    if ((a & 1)==0) {

        // If b is even
        if ((b & 1)==0)
            return false;

        // If b is odd
        else
            return (n % 3 != 0);
    }

    // If a is odd
    else {
        // If b is odd
        if ((b & 1)==0)
            return ((n - 1) % 3 != 0);

        // If b is eve
        else
            return ((n + 1) % 3 != 0);
    }
}

// Driven Program
static void Main()
{
    int a = 2, b = 4;
    int n = 3;

    if(findNature(a, b, n))
    System.Console.WriteLine("Odd");
    else
    System.Console.WriteLine("Even");

}
}
// This Code is contributed by mits
```

## PHP

```php
<?php
// PHP Program to check if the
// nth is odd or even in a
// sequence where each term is
// sum of previous two term

// Return if the nth
// term is even or odd.
function findNature($a, $b, $n)
{
    if ($n == 0)
        return ($a & 1);

    if ($n == 1)
        return ($b & 1);

    // If a is even
    if (!($a & 1))
    {

        // If b is even
        if (!($b & 1))
            return false;

        // If b is odd
        else
            return ($n % 3 != 0);
    }

    // If a is odd
    else
    {
        // If b is odd
        if (!($b & 1))
            return (($n - 1) % 3 != 0);

        // If b is eve
        else
            return (($n + 1) % 3 != 0);
    }
}

// Driver Code
$a = 2; $b = 4;
$n = 3;

if (findNature($a, $b, $n) == true)
    echo "Odd"," ";
else
    echo "Even"," ";

// This code is contributed by ajit
?>
```

## JavaScript

```javascript
<script>
    // Javascript Program to check if the nth is odd or even in a
    // sequence where each term is sum of previous two term

    // Return if the nth term is even or odd.
    function findNature(a, b, n)
    {
        if (n == 0)
            return (a & 1)==1?true:false;

        if (n == 1)
            return (b & 1)==1?true:false;

        // If a is even
        if ((a & 1)==0) {

            // If b is even
            if ((b & 1)==0)
                return false;

            // If b is odd
            else
                return (n % 3 != 0);
        }

        // If a is odd
        else {
            // If b is odd
            if ((b & 1)==0)
                return ((n - 1) % 3 != 0);

            // If b is eve
            else
                return ((n + 1) % 3 != 0);
        }
    }

    let a = 2, b = 4;
    let n = 3;

    if(findNature(a, b, n))
        document.write("Odd");
    else
        document.write("Even");

// This code is contributed by suresh07.
</script>
```

`Output` :

```
Even
```