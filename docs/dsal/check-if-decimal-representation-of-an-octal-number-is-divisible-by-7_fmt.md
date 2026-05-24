# 检查八进制数的十进制表示是否能被 7 整除

> 原文: [https://www.geeksforgeeks.org/check-if-decimal-representation-of-an-octal-number-is-divisible-by-7/](https://www.geeksforgeeks.org/check-if-decimal-representation-of-an-octal-number-is-divisible-by-7/)

给定一个八进制数 `N`，任务是编写一个程序来检查给定八进制数 `N` 的十进制表示是否能被 7 整除。

**例**:

```
Input: N = 112
Output: NO
Equivalent Decimal = 74
7410 = 7 * 101 + 4 * 100
1128 = 1 * 82 + 1 * 81 + 2 * 80

Input: N = 25
Output: YES
Decimal Equivalent = 21
```

想法是注意，`8 % 7` 将返回 `1`。因此，当我们扩展八进制表示并取其模 `7` 时，单个项中 `8` 的所有幂将减少到 `1`。所以，如果八进制表示中所有数字的和能被 `7` 整除，那么相应的十进制数就能被 `7` 整除。

以下是上述方法的实现:

## C++

```cpp
// CPP program to check if Decimal representation
// of an Octal number is divisible by 7 or not

#include <bits/stdc++.h>
using namespace std;

// Function to check Divisibility
int check(int n)
{
    int sum = 0;

    // Sum of all individual digits
    while (n != 0) {
        sum += n % 10;
        n = n / 10;
    }

    // Condition
    if (sum % 7 == 0)
        return 1;
    else
        return 0;
}

// Driver Code
int main()
{
    // Octal number
    int n = 25;

    (check(n) == 1) ? cout << "YES"
                    : cout << "NO";

    return 0;
}
```

## Java

```java
// Java program to check if Decimal
// representation of an Octal number
// is divisible by 7 or not
import java.util.*;
import java.lang.*;
import java.io.*;

class GFG
{

// Function to check Divisibility
static int check(int n)
{
    int sum = 0;

    // Sum of all individual digits
    while (n != 0)
    {
        sum += n % 10;
        n = n / 10;
    }

    // Condition
    if (sum % 7 == 0)
        return 1;
    else
        return 0;
}

// Driver Code
public static void main(String args[])
{
    // Octal number
    int n = 25;

    String s=(check(n) == 1) ?
                       "YES" : "NO";
    System.out.println(s);
}
}

// This code is contributed
// by Subhadeep
```

## Python 3

```python
# Python 3 program to check if
# Decimal representation of an
# Octal number is divisible by
# 7 or not

# Function to check Divisibility
def check(n):

    sum = 0

    # Sum of all individual digits
    while n != 0 :
        sum += n % 10
        n = n // 10

    # Condition
    if sum % 7 == 0 :
        return 1
    else:
        return 0

# Driver Code
if __name__ == "__main__":
    # Octal number
    n = 25

    print(("YES") if check(n) == 1
                  else print("NO"))

# This code is contributed
# by ChitraNayal
```

## C#

```csharp
// C# program to check if Decimal
// representation of an Octal
// number is divisible by 7 or not
using System;

class GFG
{

    // Function to check Divisibility
    static int check(int n)
    {
            int sum = 0;

        // Sum of all individual digits
        while (n != 0)
        {
            sum += n % 10;
            n = n / 10;
        }

    // Condition
    if (sum % 7 == 0)
        return 1;
    else
        return 0;
}

// Driver Code
public static void Main(String []args)
{
    // Octal number
    int n = 25;

    String s=(check(n) == 1) ?
                       "YES" : "NO";
    Console.WriteLine(s);
}
}

// This code is contributed
// by Kirti_Mangal
```

## PHP

```php
<?php
// PHP program to check if
// Decimal representation of
// an Octal number is divisible
// by 7 or not

// Function to check Divisibility
function check($n)
{
    $sum = 0;

    // Sum of all individual digits
    while ($n != 0)
    {
        $sum += $n % 10;
        $n = (int)($n / 10);
    }

    // Condition
    if ($sum % 7 == 0)
        return 1;
    else
        return 0;
}

// Driver Code

// Octal number
$n = 25;

(check($n) == 1) ?
  print("YES\n") :
   print("NO\n");

// This Code is contributed
// by mits
?>
```

## JavaScript

```javascript
<script>

// Javascript program to check if Decimal representation
// of an Octal number is divisible by 7 or not

// Function to check Divisibility
function check(n)
{
    let sum = 0;

    // Sum of all individual digits
    while (n != 0) {
        sum += n % 10;
        n = Math.floor(n / 10);
    }

    // Condition
    if (sum % 7 == 0)
        return 1;
    else
        return 0;
}

// Driver Code

    // Octal number
    let n = 25;

    (check(n) == 1) ? document.write("YES")
                    : document.write("NO");

// This code is contributed by Mayank Tyagi

</script>
```

**Output:**

```
YES
```