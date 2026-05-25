# 从 2 到 n-1 不同基数写的数字总和

> 原文：[https://www.geeksforgeeks.org/sum-of-digits-written-in-different-bases-from-2-to-n-1/](https://www.geeksforgeeks.org/sum-of-digits-written-in-different-bases-from-2-to-n-1/)

给定一个数 `n`，求从 2 到 `n-1` 的不同基数表示的 `n` 位数之和。

**例：**

```
Input : 5
Output : 2 3 2
Representation of 5 is 101, 12, 11 in bases 2 , 3 , 4 .

Input : 7
Output : 3 3 4 3 2
```

1.  因为给定问题要求不同基数的各位数字之和，我们首先需要计算给定数字在不同基数下的表示，然后将这些表示中的每一位数字相加。
2.  因此，为了计算每个数字的表示，我们将给定数字对想要表示的基数取模。
3.  然后，我们必须将所有这些模值相加，因为得到的模值就代表了该基数下的各位数字。
4.  最后，这些模值的和就给出了该数字在对应基数下的各位数字之和。

以下是这种方法的实现方式。

## C++

```cpp
// CPP program to find sum of digits of
// n in different bases from 2 to n-1.
#include <bits/stdc++.h>
using namespace std;

// function to calculate sum of
// digit for a given base
int solve(int n, int base)
{
    // Sum of digits
    int result = 0 ;

    // Calculating the number (n) by
    // taking mod with the base and adding
    // remainder to the result and
    // parallelly reducing the num value .
    while (n > 0)
    {
        int remainder = n % base ;
        result = result + remainder ;
        n = n / base;
    }

    // returning the result
    return result ;
}

void printSumsOfDigits(int n)
{
    // function calling for multiple bases
    for (int base = 2 ; base < n ; ++base)   
        cout << solve(n, base) <<" ";
}

// Driver program
int main()
{
    int n = 8;
    printSumsOfDigits(n);
    return 0;
}
```

## Java 语言

```java
// Java program to find sum of digits of
// n in different bases from 2 to n-1.
class GFG
{
// function to calculate sum of
// digit for a given base
static int solve(int n, int base)
{
    // Sum of digits
    int result = 0 ;

    // Calculating the number (n) by
    // taking mod with the base and adding
    // remainder to the result and
    // parallelly reducing the num value .
    while (n > 0)
    {
        int remainder = n % base ;
        result = result + remainder ;
        n = n / base;
    }

    // returning the result
    return result ;
}

static void printSumsOfDigits(int n)
{
    // function calling for multiple bases
    for (int base = 2 ; base < n ; ++base)
        System.out.print(solve(n, base)+" ");
}

// Driver Code
public static void main(String[] args)
{
    int n = 8;
    printSumsOfDigits(n);
}
}
// This code is contributed by Smitha
```

## Python 3

```python
# Python program to find sum of digits of
# n in different bases from 2 to n-1.

# def to calculate sum of
# digit for a given base
def solve(n, base) :

    # Sum of digits
    result = 0

    # Calculating the number (n) by
    # taking mod with the base and adding
    # remainder to the result and
    # parallelly reducing the num value .
    while (n > 0) :

        remainder = n % base
        result = result + remainder 
        n = int(n / base)

    # returning the result
    return result

def printSumsOfDigits(n) :

    # def calling for
    # multiple bases
    for base in range(2, n) :
        print (solve(n, base), end=" ")

# Driver code
n = 8
printSumsOfDigits(n)

# This code is contributed by Manish Shaw
# (manishshaw1)
```

## C#

```csharp
// C# program to find the sum of digits of
// n in different bases from 2 to n-1.
using System;

class GFG
{
// function to calculate sum of
// digit for a given base
static int solve(int n, int base1)
{
    // Sum of digits
    int result = 0 ;

    // Calculating the number (n) by
    // taking mod with the base1 and adding
    // remainder to the result and
    // parallelly reducing the num value .
    while (n > 0)
    {
        int remainder = n % base1 ;
        result = result + remainder ;
        n = n / base1;
    }

    // returning the result
    return result ;
}

static void printSumsOfDigits(int n)
{
    // function calling for multiple base1s
    for (int base1 = 2 ; base1 < n ; ++base1)
        Console.Write(solve(n, base1)+" ");
}

// Driver Code
public static void Main()
{
    int n = 8;
    printSumsOfDigits(n);
}
}
// This code is contributed by Smitha
```

## PHP

```php
<?php
// PHP program to find sum of digits of
// n in different bases from 2 to n-1.

// function to calculate sum of
// digit for a given base
function solve($n, $base)
{

    // Sum of digits
    $result = 0 ;

    // Calculating the number (n) by
    // taking mod with the base and adding
    // remainder to the result and
    // parallelly reducing the num value .
    while ($n > 0)
    {
        $remainder = $n % $base ;
        $result = $result + $remainder ;
        $n = $n / $base;
    }

    // returning the result
    return $result ;
}

function printSumsOfDigits($n)
{

    // function calling for
    // multiple bases
    for ($base = 2 ; $base < $n ; ++$base)
    {
        echo(solve($n, $base));
        echo(" ");
    }
}

// Driver code
$n = 8;
printSumsOfDigits($n);

// This code is contributed by Ajit.
?>
```

## JavaScript

```javascript
<script>

// JavaScript program to find sum of digits of
// n in different bases from 2 to n-1.

    // function to calculate sum of
    // digit for a given base
    function solve(n , base) {
        // Sum of digits
        var result = 0;

        // Calculating the number (n) by
        // taking mod with the base and adding
        // remainder to the result and
        // parallelly reducing the num value .
        while (n > 0) {
            var remainder = n % base;
            result = result + remainder;
            n = parseInt(n / base);
        }

        // returning the result
        return result;
    }

    function printSumsOfDigits(n) {
        // function calling for multiple bases
        for (base = 2; base < n; ++base)
            document.write(solve(n, base) + " ");
    }

    // Driver Code

        var n = 8;
        printSumsOfDigits(n);

// This code contributed by Rajput-Ji

</script>
```

**输出：**

```
1 4 2 4 3 2 
```