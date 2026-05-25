# 最多可被 2 或 5 整除的数的和

> 原文：[https://www.geeksforgeeks.org/sum-of-the-numbers-upto-n-that-are-divisible-by-2-or-5/](https://www.geeksforgeeks.org/sum-of-the-numbers-upto-n-that-are-divisible-by-2-or-5/)

给定一个数 `n`，任务是找出从 1 到 `n` 中所有能被 2 或 5 整除的数的和。

**示例：**

```
Input: n = 2
Output: 2

Input: n = 5
Output: 11
```

## 朴素方法

一种天真的方法是迭代从 1 到 `n` 的所有数字，并检查它是否能被 2 或 5 整除。如果它是可分的，那么就把这个数加到我们需要的和上。这种方法的时间复杂度为 `O(n)`。

## 高效方法

1.  首先找出能被 2 整除的数字。这些数字构成一个等差数列（AP），其：
    *   首项 `a = 2`
    *   公差 `d = 2`
    *   项数 `count = n / 2`
    *   和 `Sum_2 = (count * (2 * a + (count - 1) * d)) / 2`

2.  其次，找出能被 5 整除的数。这些数字构成一个等差数列（AP），其：
    *   首项 `a = 5`
    *   公差 `d = 5`
    *   项数 `count = n / 5`
    *   和 `Sum_5 = (count * (2 * a + (count - 1) * d)) / 2`

3.  然后，找出能被 2 和 5 同时整除的数（即能被 10 整除）。这些数构成一个等差数列（AP），其：
    *   首项 `a = 10`
    *   公差 `d = 10`
    *   项数 `count = n / 10`
    *   和 `Sum_10 = (count * (2 * a + (count - 1) * d)) / 2`

4.  因为我们必须找到可被 2 或 5 整除的数的和，根据容斥原理，所需的总和为：
    `sum = Sum_2 + Sum_5 - Sum_10`

## 代码实现

以下是上述方法的实现：

### C++

```cpp
// C++ implementation of above approach
#include <bits/stdc++.h>
#define ll long long int
using namespace std;

// Function to find the sum
ll findSum(int n)
{
    ll sum2, sum5, sum10;

    // sum2 is sum of numbers divisible by 2
    sum2 = ((n / 2) * (4 + (n / 2 - 1) * 2)) / 2;

    // sum5 is sum of number divisible by 5
    sum5 = ((n / 5) * (10 + (n / 5 - 1) * 5)) / 2;

    // sum10 of numbers divisible by 2 and 5
    sum10 = ((n / 10) * (20 + (n / 10 - 1) * 10)) / 2;

    return sum2 + sum5 - sum10;
}

// Driver code
int main()
{
    int n = 5;

    cout << findSum(n) << endl;
    return 0;
}
```

### Java

```java
// Java implementation of above approach
import java.lang.*;
import java.util.*;

class GFG
{
    // Function to find the sum
    static long findSum(int n)
    {
        long sum2, sum5, sum10;

        // sum2 is sum of numbers divisible by 2
        sum2 = ((n / 2) * (4 + (n / 2 - 1) * 2)) / 2;

        // sum5 is sum of number divisible by 5
        sum5 = ((n / 5) * (10 + (n / 5 - 1) * 5)) / 2;

        // sum10 of numbers divisible by 2 and 5
        sum10 = ((n / 10) * (20 + (n / 10 - 1) * 10)) / 2;

        return sum2 + sum5 - sum10;
    }

    // Driver code
    public static void main (String[] args)
    {
        int n = 5;
        System.out.println(findSum(n));
    }
}

// This code is contributed by Raj
```

### Python 3

```python
# Python3 implementation of above approach

# Function to find the sum
def findSum(n):
    # sum2 is sum of numbers divisible by 2
    sum2 = ((n // 2) * (4 + (n // 2 - 1) * 2)) // 2

    # sum5 is sum of number divisible by 5
    sum5 = ((n // 5) * (10 + (n // 5 - 1) * 5)) // 2

    # sum10 of numbers divisible by 2 and 5
    sum10 = ((n // 10) * (20 + (n // 10 - 1) * 10)) // 2

    return sum2 + sum5 - sum10

# Driver code
if __name__=='__main__':
    n = 5
    print(int(findSum(n)))

# this code is contributed by Shivi_Aggarwal
```

### C#

```csharp
// C# implementation of above approach
using System;

class GFG
{
    // Function to find the sum
    static long findSum(int n)
    {
        long sum2, sum5, sum10;

        // sum2 is sum of numbers divisible by 2
        sum2 = ((n / 2) * (4 + (n / 2 - 1) * 2)) / 2;

        // sum5 is sum of number divisible by 5
        sum5 = ((n / 5) * (10 + (n / 5 - 1) * 5)) / 2;

        // sum10 of numbers divisible by 2 and 5
        sum10 = ((n / 10) * (20 + (n / 10 - 1) * 10)) / 2;

        return sum2 + sum5 - sum10;
    }

    // Driver code
    public static void Main()
    {
        int n = 5;
        Console.WriteLine(findSum(n));
    }
}

// This code is contributed by inder_verma
```

### PHP

```php
<?php
// PHP implementation of above approach

// Function to find the sum
function findSum($n)
{
    // sum2 is sum of numbers divisible by 2
    $sum2 = ((int)($n / 2) * (4 + ((int)($n / 2) - 1) * 2)) / 2;

    // sum5 is sum of number divisible by 5
    $sum5 = ((int)($n / 5) * (10 + ($n / 5 - 1) * 5)) / 2;

    // sum10 of numbers divisible by 2 and 5
    $sum10 = ((int)($n / 10) * (20 + ($n / 10 - 1) * 10)) / 2;

    return $sum2 + $sum5 - $sum10;
}

// Driver Code
$n = 5;
echo findSum($n);

// This code is contributed by Raj
?>
```

### JavaScript

```javascript
<script>
// Javascript implementation of above approach

// Function to find the sum
function findSum(n)
{
    var sum2, sum5, sum10;

    // sum2 is sum of numbers divisible by 2
    sum2 = parseInt((parseInt(n / 2) *
    (4 + (parseInt(n / 2) - 1) * 2)) / 2);

    // sum5 is sum of number divisible by 5
    sum5 = parseInt((parseInt(n / 5) *
    (10 + (parseInt(n / 5) - 1) * 5)) / 2);

    // sum10 of numbers divisible by 2 and 5
    sum10 = parseInt((parseInt(n / 10) *
    (20 + (parseInt(n / 10) - 1) * 10)) / 2);

    return sum2 + sum5 - sum10;
}

// Driver code
var n = 5;
document.write(findSum(n));
</script>
```

**输出：**

```
11
```