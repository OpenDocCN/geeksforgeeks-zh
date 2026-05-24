# 集合上对称关系的个数

原文：[https://www.geeksforgeeks.org/number-symmetric-relations-set/](https://www.geeksforgeeks.org/number-symmetric-relations-set/)

给定一个数 `n`，找出前 `n` 个自然数 `{1, 2, ..n}` 上的对称关系总数。

示例：

```
Input  : n = 2
Output : 8
Given set is {1, 2}. Below are all symmetric relation.
{}
{(1, 1)}, 
{(2, 2)},
{(1, 1), (2, 2)}, 
{(1, 2), (2, 1)} 
{(1, 1), (1, 2), (2, 1)},
{(2, 2), (1, 2), (2, 1)}, 
{(1, 1), (1, 2), (2, 1), (1, 2)} 

Input  : n = 3
Output : 64
```

集合 `A` 上的一个关系 `R` 被说成是对称的，如果 `xRy` 蕴含 `yRx` 对于每一对 `x, y ∈ A`。或者等价地，如果 `(x, y) ∈ R`，那么 `(y, x) ∈ R` 对于每一对 `x, y`。

对称关系总数为 `2^(n(n+1)/2)`。

这个公式是怎么推导的？

如果矩阵中每个单元格 `(i, j)` 的值与单元格 `(j, i)` 相同，则关系 `R` 是对称的。对角线上的值可以任意选择。

![MATRIX4](img/aeec87811a5adde64545d2bfcffbf9c9.png)

- 有 `n` 个对角线值，对角线值的总可能组合数为 `2^n`。
- 有 `n^2 – n` 个非对角线值。我们只能为其中的一半独立选择值，因为当我们为单元格 `(i, j)` 选择一个值时，单元格 `(j, i)` 会得到相同的值。
- 所以非对角线值的组合数为 `2^((n^2 – n)/2)`。
- 整体组合数为 `2^n * 2^((n^2 – n)/2) = 2^(n(n+1)/2)`。

## C++

```cpp
// C++ program to count total symmetric relations
// on a set of natural numbers.
#include <bits/stdc++.h>

// function find the square of n
unsigned int countSymmetric(unsigned int n)
{
    // Base case
    if (n == 0)
        return 1;

   // Return 2^(n(n + 1)/2)
   return 1 << ((n * (n + 1))/2);
}

// Driver code
int main()
{
    unsigned int n = 3;

    printf("%u", countSymmetric(n));
    return 0;
}
```

## Java

```java
// Java program to count total symmetric
// relations on a set of natural numbers.
import java.io.*;
import java.util.*;

class GFG {

    // function find the square of n
    static int countSymmetric(int n)
    {
        // Base case
        if (n == 0)
            return 1;

    // Return 2^(n(n + 1)/2)
    return 1 << ((n * (n + 1)) / 2);
    }

    // Driver code
    public static void main (String[] args)
    {
        int n = 3;
        System.out.println(countSymmetric(n));
    }
}

// This code is contributed by Nikita Tiwari.
```

## Python 3

```python
# Python 3 program to count
# total symmetric relations
# on a set of natural numbers.

# function find the square of n
def countSymmetric(n) :
    # Base case
    if (n == 0) :
        return 1

    # Return 2^(n(n + 1)/2)
    return (1 << ((n * (n + 1))//2))

# Driver code

n = 3
print(countSymmetric(n))

# This code is contributed
# by Nikita Tiwari.
```

## C#

```csharp
// C# program to count total symmetric
// relations on a set of natural numbers.
using System;

class GFG {

    // function find the square of n
    static int countSymmetric(int n)
    {
        // Base case
        if (n == 0)
            return 1;

    // Return 2^(n(n + 1)/2)
    return 1 << ((n * (n + 1)) / 2);
    }

    // Driver code
    public static void Main ()
    {
        int n = 3;
        Console.WriteLine(countSymmetric(n));
    }
}

// This code is contributed by vt_m.
```

## PHP

```php
<?php
// PHP program to count total symmetric
// relations on a set of natural numbers.

// function find the square of n
function countSymmetric($n)
{
    // Base case
    if ($n == 0)
        return 1;

    // Return 2^(n(n + 1)/2)
    return 1 << (($n * ($n + 1))/2);
}

    // Driver code
    $n = 3;
    echo(countSymmetric($n));

// This code is contributed by vt_m.
?>
```

## JavaScript

```javascript
<script>

// JavaScript program to count total symmetric
// relations on a set of natural numbers.

// function find the square of n
    function countSymmetric(n)
    {
        // Base case
        if (n == 0)
            return 1;

    // Return 2^(n(n + 1)/2)
    return 1 << ((n * (n + 1)) / 2);
    }

// Driver Code

        let n = 3;
        document.write(countSymmetric(n));

</script>
```

**输出:**

```
64
```