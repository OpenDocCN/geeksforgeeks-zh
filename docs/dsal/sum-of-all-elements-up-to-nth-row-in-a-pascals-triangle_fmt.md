# 帕斯卡三角形中直到第 n 行的所有元素的总和

> 原文: [https://www.geeksforgeeks.org/sum-of-all-elements-up-to-nth-row-in-a-pascals-triangle/](https://www.geeksforgeeks.org/sum-of-all-elements-up-to-nth-row-in-a-pascals-triangle/)

给定一个行号 `n`，任务是计算每一行直到第 `n` 行的所有元素之和。

**例:**

```
Input  : 2
Output : 7 
Explanation:  row 0 have element 1
              row 1 have elements 1, 1
              row 2 have elements 1, 2, 1
              so, sum will be ((1) + (1 + 1) + (1 + 2 + 1)) = 7

Input  : 4
Output : 31
Explanation:  row 0 have element 1
              row 1 have elements 1, 1
              row 2 have elements 1, 2, 1
              row 3 have elements 1, 3, 3, 1
              row 4 have elements 1, 4, 6, 4, 1
              so, sum will be ((1) + (1 + 1) + (1 + 2 + 1)
              + (1 + 3 + 3 + 1) + (1 + 4 + 6 + 4 + 1)) = 31
```

下面是帕斯卡三角形有 11 行的例子:

```
                             Pascal's triangle

0th row                             1                                
1st row                           1   1                              
2nd row                         1   2   1                            
3rd row                       1   3   3   1                          
4th row                     1   4   6   4   1                        
5th row                   1   5   10  10  5   1                     
6th row                 1   6   15  20  15  6   1                   
7th row               1   7   21  35  35  21  7   1                  
8th row             1  8   28   56  70   56  28  8  1                
9th row           1   9  36  84  126  126  84  36  9  1              
10th row        1  10  45  120 210  256  210 120 45 10  1            
```

## 天真方法

在帕斯卡三角形中，一行的每个条目都是二项式系数值。因此，一个简单的解决方案是生成第 `n` 行之前的所有行元素并添加它们。但是这种方法会有 `O(n^3)` 的时间复杂度。但是，它可以优化到 `O(n^2)` 的时间复杂度。参考以下文章生成帕斯卡三角形的元素:

*   [帕斯卡的三角](https://www.geeksforgeeks.org/pascal-triangle/)

## 更好的解决方案

我们来看看帕斯卡的三角模式

```
                                                               sum of elements in ith row
0th row                             1                                1    -> 2^0
1st row                           1   1                              2    -> 2^1
2nd row                         1   2   1                            4    -> 2^2
3rd row                       1   3   3   1                          8    -> 2^3
4th row                     1   4   6   4   1                        16   -> 2^4
5th row                   1   5   10  10  5   1                      32   -> 2^5
6th row                 1   6   15  20  15  6   1                    64   -> 2^6
7th row               1   7   21  35  35  21  7   1                  128  -> 2^7
8th row             1  8   28   56  70   56  28  8  1                256  -> 2^8
9th row           1   9  36  84  126  126  84  36  9  1              512  -> 2^9
10th row        1  10  45  120 210  256  210 120 45 10  1            1024 -> 2^10
```

如上图所示，第 `i` 行的元素之和等于 `2^i`。现在，通过 2 的幂次相加，可以很容易地计算出第 `n` 行的所有元素的总和。

以下是上述方法的实施:

### C++

```cpp
// C++ program to find sum of all elements
// upto nth row in Pascal triangle.
#include <bits/stdc++.h>
using namespace std;

// Function to find sum of all elements
// upto nth row.
long long int calculateSum(int n)
{

    // Initialize sum with 0
    long long int sum = 0;

    // Loop to calculate power of 2
    // upto n and add them
    for (int row = 0; row < n; row++) {
        sum = sum + (1 << row);
    }

    return sum;
}

// Driver function
int main()
{
    int n = 10;
    cout << " Sum of all elements:" << calculateSum(n);
    return 0;
}
```

### Java

```java
// Java program to find sum of all elements
// upto nth row in Pascal triangle.
import java.io.*;

class GFG {

    // Function to find sum of all elements
    // upto nth row.
    static long calculateSum(int n)
    {

        // Initialize sum with 0
        long sum = 0;

        // Loop to calculate power of 2
        // upto n and add them
        for (int row = 0; row < n; row++) {
            sum = sum + (1 << row);
        }

        return sum;
    }

    // Driver code
    public static void main(String[] args)
    {
        int n = 10;
        System.out.println("Sum of all elements:"
                           + calculateSum(n));
    }
}
```

### Python 3

```python
# Python program to find sum of all elements
# upto nth row in Pascal triangle.

# Function to find sum of all elements
# upto nth row.
def calculateSum(n) :

    # Initialize sum with 0
    sum = 0

    # Loop to calculate power of 2
    # upto n and add them
    for row in range(n):
        sum = sum + (1 << row)

    return sum

# Driver code   
n = 10
print("Sum of all elements:", calculateSum(n))
```

### C#

```csharp
// C# program to find sum of all elements
// upto nth row in Pascal triangle.
using System;

public class GFG {

    // Function to find sum of all elements
    // upto nth row.
    static long calculateSum(int n)
    {

        // Initialize sum with 0
        long sum = 0;

        // Loop to calculate power of 2
        // upto n and add them
        for (int row = 0; row < n; row++) {
            sum = sum + (1 << row);
        }

        return sum;
    }

    static public void Main()
    {
        int n = 10;
        Console.WriteLine("Sum of all elements:"
                          + calculateSum(n));
    }
}
```

### PHP

```php
<?php
// PHP program to find sum of
// all elements upto nth row
// in Pascal triangle.

// Function to find sum of
// all elements upto nth row.
function calculateSum($n)
{

    // Initialize sum with 0
    $sum = 0;

    // Loop to calculate power
    // of 2 upto n and add them
    for ($row = 0; $row < $n; $row++)
    {
        $sum = $sum + (1 << $row);
    }

    return $sum;
}

// Driver Code
$n = 10;
echo " Sum of all elements : " .
               calculateSum($n);

// This code is contributed by Mahadev.
?>
```

### JavaScript

```javascript
<script>
// Javascript program to find sum of
// all elements upto nth row
// in Pascal triangle.

// Function to find sum of
// all elements upto nth row.
function calculateSum(n)
{

    // Initialize sum with 0
    let sum = 0;

    // Loop to calculate power
    // of 2 upto n and add them
    for (let row = 0; row < n; row++)
    {
        sum = sum + (1 << row);
    }

    return sum;
}

// Driver Code
let n = 10;
document.write(" Sum of all elements : " + calculateSum(n));

// This code is contributed by _saurabh_jaiswal.
</script>
```

**Output:**

```
Sum of all elements:1023
```

**时间复杂度:** `O(n)`

## 高效解

> `2^n` 可以表示为
> `2^n = (2^0 + 2^1 + 2^2 + 2^3 + ... + 2^(n-1)) + 1`
> **例如:**
> `2^6 = (2^0 + 2^1 + 2^2 + 2^3 + 2^4 + 2^5) + 1`
> `64 = (1 + 2 + 4 + 8 + 16 + 32) + 1`

因此，计算 `2^n` 而不是计算 2 的每一次幂直到 `(n–1)`，从上面的例子中，2 的幂直到 `(n–1)` 的和将是 `(2^n – 1)`。

### C++

```cpp
// C++ program to find sum of all elements
// upto nth row in Pascal triangle.
#include <bits/stdc++.h>
using namespace std;

// Function to find sum of all elements
// upto nth row.
long long int calculateSum(int n)
{

    // Initialize sum with 0
    long long int sum = 0;

    // Calculate 2^n
    sum = 1 << n;

    return (sum - 1);
}

// Driver function
int main()
{

    int n = 10;
    cout << " Sum of all elements:" << calculateSum(n);
    return 0;
}
```

### Java

```java
// Java program to find sum of all elements
// upto nth row in Pascal triangle.
import java.io.*;

class GFG {

    // Function to find sum of all elements
    // upto nth row.
    static long calculateSum(int n)
    {

        // Initialize sum with 0
        long sum = 0;

        // Calculate 2^n
        sum = 1 << n;

        return (sum - 1);
    }

    // Driver code
    public static void main(String[] args)
    {
        int n = 10;
        System.out.println("Sum of all elements:"
                           + calculateSum(n));
    }
}
```

## 蟒蛇 3

```python
# Python3 program to find sum of all elements
# upto nth row in Pascal triangle.

# Function to find sum of all elements
# upto nth row.
def calculateSum(n) :

    # Initialize sum with 0
    sum = 0

    # Calculate 2 ^ n
    sum = 1 << n;

    return (sum - 1)

# Driver unicode
n = 10
print("Sum of all elements:", calculateSum(n))
```

## C#

```csharp
// C# program to find sum of all elements
// upto nth row in Pascal triangle.
using System;

public class GFG {

    // Function to find sum of all elements
    // upto nth row.
    static long calculateSum(int n)
    {

        // Initialize sum with 0
        long sum = 0;

        // Calculate 2^n
        sum = 1 << n;

        return (sum - 1);
    }

    // Driver code
    static public void Main()
    {
        int n = 10;
        Console.WriteLine("Sum of all elements:"
                          + calculateSum(n));
    }
}
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```php
<?php
// PHP program to find sum
// of all elements upto nth
// row in Pascal triangle.

// Function to find
// sum of all elements
// upto nth row.

function calculateSum($n)
{
    // Initialize sum with 0
    $sum = 0;

    // Calculate 2^n
    $sum = 1 << $n;

    return ($sum - 1);
}

// Driver Code
$n = 10;
echo " Sum of all elements:" ,
             calculateSum($n);

// This code is contributed
// by akt_mit
?>
```

## java 描述语言

```javascript
// Javascript program to find sum
// of all elements upto nth
// row in Pascal triangle.

// Function to find
// sum of all elements
// upto nth row.

function calculateSum(n)
{
    // Initialize sum with 0
    sum = 0;

    // Calculate 2^n
    sum = 1 << n;

    return (sum - 1);
}

// Driver Code
let n = 10;
document.write(" Sum of all elements:" + calculateSum(n));

// This code is contributed _saurabh_jaiswal
```

**Output:**

```
Sum of all elements:1023
```

**时间复杂度:** O(1)