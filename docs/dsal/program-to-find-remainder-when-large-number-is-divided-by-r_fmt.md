# 当大数除以 r 时求余数的程序

> 原文：[https://www.geeksforgeeks.org/program-to-find-remainder-when-large-number-is-divided-by-r/](https://www.geeksforgeeks.org/program-to-find-remainder-when-large-number-is-divided-by-r/)

给定一个数 `N`，任务是当 `N` 除以 `R`（一个两位数）时求余数。数字的输入可能非常大。

`例：`

```
Input: N = 13589234356546756, R = 13
Output: 11

Input: N = 3435346456547566345436457867978, R = 17
Output: 13
```

*   从左到右逐个获取 `n` 的数字。
*   对于每个数字，如果它小于 `r`，则与下一个数字组合。
*   如果任何点的组合达到 `r` 或更大，则取余数并存储。
*   对所有数字从左到右重复上述步骤。

下面是实现上述方法的程序：

## C++

```cpp
// CPP implementation to find Remainder
// when a large Number is divided by R

#include <bits/stdc++.h>
using namespace std;

// Function to Return Remainder
int Remainder(string str, int R)
{
    // len is variable to store the
    // length of Number string.
    int len = str.length();

    int Num, Rem = 0;

    // loop that find Remainder
    for (int i = 0; i < len; i++) {

        Num = Rem * 10 + (str[i] - '0');
        Rem = Num % R;
    }

    // Return the remainder
    return Rem;
}

// Driver code
int main()
{

    // Get the large number as string
    string str = "13589234356546756";

    // Get the divisor R
    int R = 13;

    // Find and print the remainder
    cout << Remainder(str, R);

    return 0;
}
```

## Java

```java
// Java implementation to find Remainder
// when a large Number is divided by R

class GFG
{
    // Function to Return Remainder
    static int Remainder(String str, int R)
    {
        // len is variable to store the
        // length of Number string.
        int len = str.length();

        int Num, Rem = 0;

        // loop that find Remainder
        for (int i = 0; i < len; i++) {

            Num = Rem * 10 + (str.charAt(i) - '0');
            Rem = Num % R;
        }

        // Return the remainder
        return Rem;
    }

    // Driver code
    public static void main( String [] args)
    {

        // Get the large number as string
        String str = "13589234356546756";

        // Get the divisor R
        int R = 13;

        // Find and print the remainder
        System.out.println(Remainder(str, R));

    }
}

// This code is contributed
// by ihritik
```

## Python 3

```python
# Python 3 implementation to
# find Remainder when a large
# Number is divided by R

# Function to Return Remainder
def Remainder(str, R):

    # len is variable to store the
    # length of Number string.
    l = len(str)

    Rem = 0

    # loop that find Remainder
    for i in range(l):

        Num = Rem * 10 + (ord(str[i]) -
                          ord('0'))
        Rem = Num % R

    # Return the remainder
    return Rem

# Driver code
if __name__ == "__main__":

    # Get the large number
    # as string
    str = "13589234356546756"

    # Get the divisor R
    R = 13

    # Find and print the remainder
    print(Remainder(str, R))

# This code is contributed
# by ChitraNayal
```

## C#

```csharp
// C# implementation to find
// Remainder when a large
// Number is divided by R
using System;

class GFG
{

// Function to Return Remainder
static int Remainder(String str,
                     int R)
{
    // len is variable to store the
    // length of Number string.
    int len = str.Length;

    int Num, Rem = 0;

    // loop that find Remainder
    for (int i = 0; i < len; i++)
    {
        Num = Rem * 10 + (str[i] - '0');
        Rem = Num % R;
    }

    // Return the remainder
    return Rem;
}

// Driver code
public static void Main()
{

    // Get the large number as string
    String str = "13589234356546756";

    // Get the divisor R
    int R = 13;

    // Find and print the remainder
    Console.WriteLine(Remainder(str, R));
}
}

// This code is contributed
// by Subhadeep
```

## PHP

```php
<?php
// PHP implementation to find Remainder
// when a large Number is divided by R

// Function to Return Remainder
function Remainder($str, $R)
{
    // len is variable to store the
    // length of Number string.
    $len = strlen($str);

    $Num = 0; $Rem = 0;

    // loop that find Remainder
    for ($i = 0; $i < $len; $i++)
    {

        $Num = $Rem * 10 + ($str[$i] - '0');
        $Rem = $Num % $R;
    }

    // Return the remainder
    return $Rem;
}

// Driver code

// Get the large number as string
$str = "13589234356546756";

// Get the divisor R
$R = 13;

// Find and print the remainder
echo Remainder($str, $R);

// This code is contributed
// by Akanksha Rai(Abby_akku)
```

## JavaScript

```javascript
<script>

// Javascript implementation to find Remainder
// when a large Number is divided by R

// Function to Return Remainder
function Remainder(str, R)
{
    // len is variable to store the
    // length of Number string.
    var len = str.length;

    var Num, Rem = 0;

    // loop that find Remainder
    for (var i = 0; i < len; i++) {

        Num = Rem * 10 + (str[i] - '0');
        Rem = Num % R;
    }

    // Return the remainder
    return Rem;
}

// Driver code
// Get the large number as string
var str = "13589234356546756";
// Get the divisor R
var R = 13;
// Find and print the remainder
document.write(Remainder(str, R));

// This code is contributed by noob2000.
</script>
```

`输出：`

```
11
```

`时间复杂度：` `O(L)`，其中 `L` 是字符串的长度

`辅助空间：` `O(L)`