# 位数之和为 N 的平方的最小数

> 原文：[https://www.geeksforgeeks.org/smallest-number-whose-sum-of-digits-is-square-of-n/](https://www.geeksforgeeks.org/smallest-number-whose-sum-of-digits-is-square-of-n/)

给定一个整数 `N`，任务是找到数字之和为 `N^2` 的最小数。

**例：**

> **输入：** `N = 4`
> **输出：** 79
> `2^4 = 16`
> 79 位数字之和 = 7+9 = 16
> **输入：** `N = 6`
> **输出：** 9999
> `2^10 = 1024` 有 4 位数字

**逼近：** 思路是找到数字之和为 `n` 的平方的最小数的通称，也就是

```
// First Few terms 
First Term = 1 // N = 1
Second Term = 4 // N = 2
Third Term = 9 // N = 3
Fourth Term = 79 // N = 4
.
.
Nth Term:
```

```
*** QuickLaTeX cannot compile formula:

*** Error message:
Error: Nothing to show, formula is empty
```

```
(n^2 % 9 + 1) * 10 ^ {⌊ n^2/9 ⌋} - 1
```

以下是上述方法的实现：

## C++

```cpp
// C++ implementation of the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to return smallest
// number whose sum of digits is n^2
int smallestNum(int n)
{
    cout<<pow(10, n * n / 9)<<endl;
    return (n * n % 9 + 1)
           * pow(10, n * n / 9)
           - 1;
}

// Driver Code
int main()
{
    int n = 4;
    cout << smallestNum(n);

    return 0;
}
```

## Java

```java
// Java implementation of the above approach
import java.util.*;

class GFG{

// Function to return smallest
// number whose sum of digits is n^2
static int smallestNum(int n)
{
    return (int)((n * n % 9 + 1) *
         Math.pow(10, n * n / 9) - 1);
}

// Driver Code
public static void main(String[] args)
{
    int n = 4;

    System.out.print(smallestNum(n));
}
}

// This code is contributed by Rajput-Ji
```

## Python 3

```python
# Python implementation of the above approach

# Function to return smallest
# number whose sum of digits is n^2
def smallestNum(n):

    return ((n * n % 9 + 1)  *
          pow(10, int(n * n / 9)) - 1)

# Driver Code

# Given N
N = 4

print(smallestNum(N))

# This code is contributed by Vishal Maurya.
```

## C#

```csharp
// C# implementation of the above approach
using System;

class GFG{

// Function to return smallest
// number whose sum of digits is n^2
static int smallestNum(int n)
{
    return (int)((n * n % 9 + 1) *
         Math.Pow(10, n * n / 9) - 1);
}

// Driver Code
public static void Main(String[] args)
{
    int n = 4;

    Console.Write(smallestNum(n));
}
}

// This code is contributed by Rajput-Ji
```

## JavaScript

```javascript
<script>
// Javascript implementation of the above approach

    // Function to return smallest
    // number whose sum of digits is n^2
    function smallestNum( n) {
        return parseInt (n * n % 9 + 1) * Math.pow(10, parseInt(n*n / 9)) -1;
    }

    // Driver Code

        let n = 4;

        document.write(smallestNum(n));

// This code contributed by aashish1995
</script>
```

**输出：**

```
79
```