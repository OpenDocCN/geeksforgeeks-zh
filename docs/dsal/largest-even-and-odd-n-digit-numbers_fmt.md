# 最大偶数和奇数 N 位数

> 原文: [https://www.geeksforgeeks.org/largest-even-and-odd-n-digit-numbers/](https://www.geeksforgeeks.org/largest-even-and-odd-n-digit-numbers/)

给定一个整数 `N`，任务是找出最大的偶数和奇数 N 位数。

**例:**

> **输入:** `N = 4`
> **输出:**
> 偶数= 9998
> 奇数= 9999
> **输入:** `N = 2`
> **输出:**
> 偶数= 98
> 奇数= 99

**进场:**

*   最大的 `N` 位偶数将是 `(10^N) - 2`，因为 `N` 不同值的系列将是 **8，98，998，9998，…..**
*   同样，最大的 `N` 位奇数将是 `(10^N) - 1` 系列 **9，99，999，9999，…..**

以下是上述方法的实现:

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to print the largest n-digit
// even and odd numbers
void findNumbers(int n)
{
    int odd = pow(10, n) - 1;
    int even = odd - 1;
    cout << "Even = " << even << endl;
    cout << "Odd = " << odd;
}

// Driver code
int main()
{
    int n = 4;
    findNumbers(n);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
class GFG {

    // Function to print the largest n-digit
    // even and odd numbers
    static void findNumbers(int n)
    {
        int odd = (int)Math.pow(10, n) - 1;
        int even = odd - 1;
        System.out.println("Even = " + even);
        System.out.print("Odd = " + odd);
    }

    // Driver code
    public static void main(String args[])
    {
        int n = 4;
        findNumbers(n);
    }
}
```

## C\#

```csharp
// C# implementation of the approach
using System;
class GFG {

    // Function to print the largest n-digit
    // even and odd numbers
    static void findNumbers(int n)
    {
        int odd = (int)Math.Pow(10, n) - 1;
        int even = odd - 1;
        Console.WriteLine("Even = " + even);
        Console.Write("Odd = " + odd);
    }

    // Driver code
    public static void Main()
    {
        int n = 4;
        findNumbers(n);
    }
}
```

## Python 3

```python
# Python3 implementation of the approach

# Function to print the largest n-digit
# even and odd numbers
def findNumbers(n):

    odd = pow(10, n) - 1
    even = odd - 1
    print("Even = ", even)
    print("Odd = ", odd)

# Driver code
n = 4
findNumbers(n)

# This code is contributed by ihritik
```

## PHP

```php
<?php
// PHP implementation of the approach

// Function to print the largest n-digit
// even and odd numbers
function findNumbers($n)
{
    $odd = pow(10, $n) - 1;
    $even = $odd - 1;
    echo "Even = $even \n";
    echo "Odd = $odd";
}

// Driver code
$n = 4 ;
findNumbers($n);

// This code is contributed by ihritik
?>
```

## JavaScript

```javascript
<script>

   // Javascript implementation of the approach

   // Function to print the largest n-digit
   // even and odd numbers
   function findNumbers(n)
   {
       var odd = Math.pow(10, n) - 1;
       var even = odd - 1;
       document.write("Even = " + even+"<br>");
       document.write("Odd = " + odd);
   }

   // Driver code
   var n = 4;
   findNumbers(n);

   // This code is contributed by rrrtnx.
</script>
```

**Output:**

```
Even = 9998
Odd = 9999
```