# 居中四面体数

> 原文：`https://www.geeksforgeeks.org/centered-tetrahedral-number/`

给我们整数 `n`，我们需要求第 `n` 个中心四面体数。

**描述：** 中心四面体数是一个代表四面体的中心形数。

[**四面体数：**](https://www.geeksforgeeks.org/tetrahedral-numbers/) 如果一个数可以表示为一个有三角形底和三条边的金字塔，称为四面体，那么这个数就被称为四面体数。第 `n` 个四面体数是前 `n` 个[三角数](https://www.geeksforgeeks.org/triangular-numbers/)的和。

**前几个居中的四面体数**系列是：
1、5、15、35、69、121、195、295、425、589……

中心四面体数的数学第 `n` 项：

**例：**

```
Input : n = 3
Output : 35

Input : n = 9
Output : 589
```

下面是上面公式的实现。

## C++

```cpp
// C++ Program to find nth
// Centered tetrahedral number
#include <bits/stdc++.h>
using namespace std;

// Function to find centered
// Centered tetrahedral number
int centeredTetrahedralNumber(int n)
{
    // Formula to calculate nth
    // Centered tetrahedral number
    // and return it into main function.
    return (2 * n + 1) * (n * n + n + 3) / 3;
}

// Driver Code
int main()
{
    int n = 6;

    cout << centeredTetrahedralNumber(n);

    return 0;
}
```

## Java

```java
// Java Program to find nth Centered
// tetrahedral number
import java.io.*;

class GFG {

    // Function to find centered
    // Centered tetrahedral number
    static int centeredTetrahedralNumber(int n)
    {

        // Formula to calculate nth
        // Centered tetrahedral number
        // and return it into main function.
        return (2 * n + 1) * (n * n + n + 3) / 3;
    }

    // Driver Code

    public static void main (String[] args)
    {
        int n = 6;

        System.out.println(
                   centeredTetrahedralNumber(n));
    }
}

// This code is contributed by anuj_67.
```

## Python

```python
# Python program to find nth
# Centered tetrahedral number

# Function to calculate
# Centered tetrahedral number

def centeredTetrahedralNumber(n):

    # Formula to calculate nth
    # Centered tetrahedral number
    # and return it into main function

    return (2 * n + 1) * (n * n + n + 3) // 3

# Driver Code
n = 6
print(centeredTetrahedralNumber(n))

# This code is contributed by ajit
```

## C#

```csharp
// C# Program to find nth Centered
// tetrahedral number
using System;

class GFG {

    // Function to find centered
    // Centered tetrahedral number
    static int centeredTetrahedralNumber(int n)
    {

        // Formula to calculate nth
        // Centered tetrahedral number
        // and return it into main function.
        return (2 * n + 1) * (n * n + n + 3) / 3;
    }

    // Driver Code

    public static void Main ()
    {
        int n = 6;

        Console.WriteLine(
                centeredTetrahedralNumber(n));
    }
}

// This code is contributed by anuj_67.
```

## PHP

```php
<?php
// PHP Program to find nth
// Centered tetrahedral number

// Function to find centered
// Centered tetrahedral number
function centeredTetrahedralNumber($n)
{
    // Formula to calculate nth
    // Centered tetrahedral number
    // and return it into main function.
    return (2 * $n + 1) *
           ($n * $n + $n + 3) / 3;
}

// Driver Code
$n = 6;

echo centeredTetrahedralNumber($n);

// This code is contributed by anuj_67.
?>
```

## JavaScript

```javascript
<script>

// Javascript program to find nth Centered
// tetrahedral number

// Function to find centered
// Centered tetrahedral number
function centeredTetrahedralNumber(n)
{

    // Formula to calculate nth
    // Centered tetrahedral number
    // and return it into main function.
    return (2 * n + 1) * (n * n + n + 3) / 3;
}

// Driver Code

// Given Number
var n = 6;

document.write(centeredTetrahedralNumber(n));

// This code is contributed by Kirti

</script>
```

**Output：**

```

```

**时间复杂度：** `O(1)`
**辅助空间：** `O(1)`