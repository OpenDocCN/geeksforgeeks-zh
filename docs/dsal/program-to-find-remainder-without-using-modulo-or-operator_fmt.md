# 不使用模或%运算符求余数的程序

> 原文: [https://www.geeksforgeeks.org/program-to-find-remainder-without-using-modulo-or-operator/](https://www.geeksforgeeks.org/program-to-find-remainder-without-using-modulo-or-operator/)

给定两个数字`num`和`divisor`，当`num`除以`divisor`时，求余数。不允许使用模或`%`运算符。

**例:**

```
Input:  num = 100, divisor = 7
Output: 2

Input:  num = 30, divisor = 9
Output: 3
```

## 方法 1

### C++

```
// C++ program to find remainder without using
// modulo operator
#include <iostream>
using namespace std;

// This function returns remainder of num/divisor
// without using % (modulo) operator
int getRemainder(int num, int divisor)
{
    return (num - divisor * (num / divisor));
}

// Driver program to test above functions
int main()
{
    // cout << 100 %0;
    cout << getRemainder(100, 7);
    return 0;
}
```

### Java

```
// Java program to find remainder without
// using modulo operator
import java.io.*;

class GFG {

    // This function returns remainder of
    // num/divisor without using % (modulo)
    // operator
    static int getRemainder(int num, int divisor)
    {
        return (num - divisor * (num / divisor));
    }

    // Driver program to test above functions
    public static void main(String[] args)
    {

        // print 100 % 0;
        System.out.println(getRemainder(100, 7));
    }
}

// This code is contributed by Sam007.
```

### Python

```
# Python program to find remainder
# without using modulo operator

# This function returns remainder of
# num / divisor without using % (modulo)
# operator
def getRemainder(num, divisor):
    return (num - divisor * (num // divisor))

# Driver program to test above functions
num = 100
divisor = 7
print(getRemainder(num, divisor))

# This code is contributed by Danish Raza
```

### C#

```
// C# program to find remainder without using
// modulo operator
using System;

class GFG {
    // This function returns remainder of
    // num/divisor without using %
    // (modulo) operator
    static int getRemainder(int num, int divisor)
    {
        return (num - divisor * (num / divisor));
    }

    // Driver program to test above functions
    public static void Main()
    {

        // print 100 % 0;
        Console.Write(getRemainder(100, 7));
    }
}

// This code is contributed by Sam007.
```

### PHP

```
<?php
// PHP program to find remainder
// without using modulo operator

// This function returns remainder
// of num/divisor without using
// % (modulo) operator
function getRemainder($num, $divisor)
{
    $t = ($num - $divisor *
         (int)($num / $divisor));
    return $t;
}

// Driver Code
echo getRemainder(100, 7);

// This code is contributed by ajit
?>
```

### JavaScript

```
<script>
// Javascript program to find remainder
// without using modulo operator

// This function returns remainder
// of num/divisor without using
// % (modulo) operator
function getRemainder(num, divisor)
{
    let t = (num - divisor *
         parseInt(num / divisor));
    return t;
}

// Driver Code
document.write(getRemainder(100, 7));

// This code is contributed by _saurabh_jaiswal
</script>
```

**输出:**

```
2
```

这个方法是由比沙尔·库马尔·杜贝贡献的。

## 方法二

想法很简单，我们运行一个循环来寻找小于或等于`num`的`divisor`的最大倍数。一旦我们找到这样一个倍数，我们就从`num`中减去这个倍数来找到除数。

以下是上述思路的实现。感谢 [eleventyone](https://www.geeksforgeeks.org/chalk-studio-interview-experience/#disqus_thread) 在评论中提出这个解决方案。

### C++

```
// C++ program to find remainder without using modulo operator
#include <iostream>
using namespace std;

// This function returns remainder of num/divisor without
// using % (modulo) operator
int getRemainder(int num, int divisor)
{
    // Handle divisor equals to 0 case
    if (divisor == 0) {
        cout << "Error: divisor can't be zero \n";
        return -1;
    }

    // Handle negative values
    if (divisor < 0)
        divisor = -divisor;
    if (num < 0)
        num = -num;

    // Find the largest product of 'divisor' that is smaller
    // than or equal to 'num'
    int i = 1;
    int product = 0;
    while (product <= num) {
        product = divisor * i;
        i++;
    }

    // return remainder
    return num - (product - divisor);
}

// Driver program to test above functions
int main()
{
    // cout << 100 %0;
    cout << getRemainder(100, 7);
    return 0;
}
```

### Java

```
// Java program to find remainder without
// using modulo operator
import java.io.*;

class GFG {

    // This function returns remainder
    // of num/divisor without using %
    // (modulo) operator
    static int getRemainder(int num, int divisor)
    {

        // Handle divisor equals to 0 case
        if (divisor == 0) {
            System.out.println("Error: divisor "
                             + "can't be zero \n");
            return -1;
        }

        // Handle negative values
        if (divisor < 0)
            divisor = -divisor;
        if (num < 0)
            num = -num;

        // Find the largest product of 'divisor'
        // that is smaller than or equal to 'num'
        int i = 1;
        int product = 0;
        while (product <= num) {
            product = divisor * i;
            i++;
        }

        // return remainder
        return num - (product - divisor);
    }

    // Driver program to test above functions
    public static void main(String[] args)
    {

        // print 100 % 0;
        System.out.println(getRemainder(100, 7));
    }
}

// This code is contributed by Sam007.
```

### Python

```
# Python program to find remainder without
# using modulo operator. This function
# returns remainder of num / divisor without
# using % (modulo) operator

def getRemainder(num, divisor):

    # Handle divisor equals to 0 case
    if (divisor == 0):
        return False

    # Handle negative values
    if (divisor < 0):
        divisor = -divisor
    if (num < 0):
        num = -num

    # Find the largest product of 'divisor'
    # that is smaller than or equal to 'num'
    i = 1
    product = 0
    while (product <= num):
            product = divisor * i
            i += 1
    # return remainder
    return num - (product - divisor)

# Driver program to test above functions
num = 100
divisor = 7
print(getRemainder(num, divisor))

# This code is contributed by Danish Raza
```

### C#

```
// C# program to find remainder without
// using modulo operator
using System;

class GFG {

    // This function returns remainder
    // of num/divisor without using %
    // (modulo) operator
    static int getRemainder(int num, int divisor)
    {

        // Handle divisor equals to 0 case
        if (divisor == 0) {
            Console.WriteLine("Error: divisor "
                            + "can't be zero \n");
            return -1;
        }

        // Handle negative values
        if (divisor < 0)
            divisor = -divisor;
        if (num < 0)
            num = -num;

        // Find the largest product of 'divisor'
        // that is smaller than or equal to 'num'
        int i = 1;
        int product = 0;
        while (product <= num) {
            product = divisor * i;
            i++;
        }

        // return remainder
        return num - (product - divisor);
    }

    // Driver program to test above functions
    public static void Main()
    {

        // print 100 %0;
        Console.Write(getRemainder(100, 7));
    }
}

// This code is contributed by Sam007.
```

# 取模运算的多种实现方法

## 方法 1：使用循环和乘法

### PHP

```php
<?php

// php program to find remainder without
// using modulo operator

// This function returns remainder of
// num/divisor without using % (modulo)
// operator

function getRemainder($num, $divisor)
{

    // Handle divisor equals to 0 case
    if ($divisor == 0)
    {
        echo "Error: divisor can't be zero \n";
        return -1;
    }

    // Handle negative values
    if ($divisor < 0) $divisor = -$divisor;
    if ($num < 0)     $num = -$num;

    // Find the largest product of 'divisor'
    // that is smaller than or equal to 'num'
    $i = 1;
    $product = 0;
    while ($product <= $num)
    {
        $product = $divisor * $i;
        $i++;
    }

    // return remainder
    return $num - ($product - $divisor);
}

// Driver program to test above functions
echo getRemainder(100, 7);

// This code is contributed by ajit.
?>
```

### JavaScript

```javascript
// Javascript program to find remainder without
// using modulo operator

// This function returns remainder of
// num/divisor without using % (modulo)
// operator

function getRemainder(num, divisor)
{

    // Handle divisor equals to 0 case
    if (divisor == 0)
    {
        document.write("Error: divisor can't be zero <br>");
        return -1;
    }

    // Handle negative values
    if (divisor < 0) divisor = -divisor;
    if (num < 0)     num = -num;

    // Find the largest product of 'divisor'
    // that is smaller than or equal to 'num'
    let i = 1;
    let product = 0;
    while (product <= num)
    {
        product = divisor * i;
        i++;
    }

    // return remainder
    return num - (product - divisor);
}

// Driver program to test above functions
document.write(getRemainder(100, 7));

// This code is contributed by _saurabh_jaiswal
```

**输出:**

```
100 % 7 = 2
```

本文由希拉克供稿。如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息

## 方法 3：循环减法

继续从分子中减去分母，直到分子小于分母。

### C++

```cpp
// C++ implementation of the approach
#include <iostream>
using namespace std;

// Function to return num % divisor
// without using % (modulo) operator
int getRemainder(int num, int divisor)
{

    // While divisor is smaller
    // than n, keep subtracting
    // it from num
    while (num >= divisor)
        num -= divisor;

    return num;
}

// Driver code
int main()
{
    int num = 100, divisor = 7;
    cout << getRemainder(num, divisor);

    return 0;
}
```

### Java

```java
// A Java implementation of the approach
import java.util.*;

class GFG
{

// Function to return num % divisor
// without using % (modulo) operator
static int getRemainder(int num, int divisor)
{

    // While divisor is smaller
    // than n, keep subtracting
    // it from num
    while (num >= divisor)
        num -= divisor;

    return num;
}

// Driver code
public static void main(String[] args)
{
    int num = 100, divisor = 7;
    System.out.println(getRemainder(num, divisor));
}
}

// This code is contributed by Princi Singh
```

### Python 3

```python
# Python3 implementation of the approach

# Function to return num % divisor
# without using % (modulo) operator
def getRemainder(num, divisor):

    # While divisor is smaller
    # than n, keep subtracting
    # it from num
    while (num >= divisor):
        num -= divisor;

    return num;

# Driver code
if __name__ == '__main__':

    num = 100; divisor = 7;
    print(getRemainder(num, divisor));

# This code is contributed by Princi Singh
```

### C#

```csharp
// C# implementation of the approach
using System;

class GFG
{

// Function to return num % divisor
// without using % (modulo) operator
static int getRemainder(int num, int divisor)
{

    // While divisor is smaller
    // than n, keep subtracting
    // it from num
    while (num >= divisor)
        num -= divisor;

    return num;
}

// Driver code
public static void Main(String[] args)
{
    int num = 100, divisor = 7;
    Console.WriteLine(getRemainder(num, divisor));
}
}

// This code is contributed by PrinciRaj1992
```

### JavaScript

```javascript
// Javascript implementation of the approach

// Function to return num % divisor
// without using % (modulo) operator
function getRemainder(num, divisor)
{

    // While divisor is smaller
    // than n, keep subtracting
    // it from num
    while (num >= divisor)
        num -= divisor;

    return num;
}

// Driver code
let num = 100, divisor = 7;
document.write(getRemainder(num, divisor));

// This code is contributed by _saurabh_jaiswal
```

**输出:**

```
2
```