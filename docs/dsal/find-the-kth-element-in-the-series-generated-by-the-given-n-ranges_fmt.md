# 在给定的 N 个范围生成的序列中找到第 k 个元素

> 原文：[https://www.geeksforgeeks.org/find-the-kth-element-in-the-series-generated-by-the-given-n-ranges/](https://www.geeksforgeeks.org/find-the-kth-element-in-the-series-generated-by-the-given-n-ranges/)

给定 **N** 个非重叠范围 `L[]` 和 `R[]`，其中每个范围在前一个范围结束后开始，即 `L[i] > R[i-1]` 对于所有有效的 `i`。任务是在所有给定范围内的元素按升序排序后形成的序列中找到第 **K** 个元素。

**示例：**

> **输入：** `L[] = {1, 8, 21}`，`R[] = {4, 10, 23}`，`K = 6`
> **输出：** 9
> 生成的序列将是 1, 2, 3, 4, 8, 9, 10, 21, 22, 23，第 6 个元素是 9。
>
> **输入：** `L[] = {2, 11, 31}`，`R[] = {7, ...}`

**方法：** 思路是用[二分搜索法](https://www.geeksforgeeks.org/binary-search/)。一个数组 `total` 来存储到第 `i` 个索引的整数数量，现在借助这个数组找出第 `k` 个整数所在的索引。假设索引是 `j`，现在计算第 `k` 个最小整数在区间 `L[j]` 到 `R[j]` 中的位置，并使用二分搜索法找到第 `k` 个最小整数，其中 `low` 将是 `L[j]` 而 `high` 将是 `R[j]`。

以下是上述方法的实现：

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the kth element
// of the required series
int getKthElement(int n, int k, int L[], int R[])
{
    int l = 1;
    int h = n;

    // To store the number of integers that lie
    // upto the ith index
    int total[n + 1];

    total[0] = 0;

    // Compute the number of integers
    for (int i = 0; i < n; i++) {
        total[i + 1] = total[i] + (R[i] - L[i]) + 1;
    }

    // Stores the index, lying from 1
    // to n,
    int index = -1;

    // Using binary search, find the index
    // in which the kth element will lie
    while (l <= h) {
        int m = (l + h) / 2;

        if (total[m] > k) {
            index = m;
            h = m - 1;
        }
        else if (total[m] < k)
            l = m + 1;
        else {
            index = m;
            break;
        }
    }

    l = L[index - 1];
    h = R[index - 1];

    // Find the position of the kth element
    // in the interval in which it lies
    int x = k - total[index - 1];

    while (l <= h) {
        int m = (l + h) / 2;

        if ((m - L[index - 1]) + 1 == x) {
            return m;
        }

        else if ((m - L[index - 1]) + 1 > x)
            h = m - 1;

        else
            l = m + 1;
    }
}

// Driver code
int main()
{
    int L[] = { 1, 8, 21 };
    int R[] = { 4, 10, 23 };
    int n = sizeof(L) / sizeof(int);

    int k = 6;

    cout << getKthElement(n, k, L, R);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
class GFG
{

// Function to return the kth element
// of the required series
static int getKthElement(int n, int k,
                         int L[], int R[])
{
    int l = 1;
    int h = n;

    // To store the number of integers that lie
    // upto the ith index
    int total[] = new int[n + 1];

    total[0] = 0;

    // Compute the number of integers
    for (int i = 0; i < n; i++)
    {
        total[i + 1] = total[i] +
                      (R[i] - L[i]) + 1;
    }

    // Stores the index, lying from 1
    // to n,
    int index = -1;

    // Using binary search, find the index
    // in which the kth element will lie
    while (l <= h)
    {
        int m = (l + h) / 2;

        if (total[m] > k)
        {
            index = m;
            h = m - 1;
        }
        else if (total[m] < k)
            l = m + 1;
        else
        {
            index = m;
            break;
        }
    }

    l = L[index - 1];
    h = R[index - 1];

    // Find the position of the kth element
    // in the interval in which it lies
    int x = k - total[index - 1];

    while (l <= h)
    {
        int m = (l + h) / 2;

        if ((m - L[index - 1]) + 1 == x)
        {
            return m;
        }

        else if ((m - L[index - 1]) + 1 > x)
            h = m - 1;

        else
            l = m + 1;
    }
    return k;
}

// Driver code
public static void main(String[] args)
{
    int L[] = { 1, 8, 21 };
    int R[] = { 4, 10, 23 };
    int n = L.length;

    int k = 6;

    System.out.println(getKthElement(n, k, L, R));
}
}

// This code is contributed by Code_Mech
```

## Python 3

```python
# Python3 implementation of the approach

# Function to return the kth element
# of the required series
def getKthElement(n, k, L, R):
    l = 1
    h = n

    # To store the number of integers that lie
    # upto the ith index
    total=[0 for i in range(n + 1)]

    total[0] = 0

    # Compute the number of integers
    for i in range(n):
        total[i + 1] = total[i] + (R[i] - L[i]) + 1

    # Stores the index, lying from 1
    # to n,
    index = -1

    # Using binary search, find the index
    # in which the kth element will lie
    while (l <= h):
        m = (l + h) // 2

        if (total[m] > k):
            index = m
            h = m - 1
        elif (total[m] < k):
            l = m + 1
        else :
            index = m
            break

    l = L[index - 1]
    h = R[index - 1]

    # Find the position of the kth element
    # in the interval in which it lies
    x = k - total[index - 1]

    while (l <= h):
        m = (l + h) // 2

        if ((m - L[index - 1]) + 1 == x):
            return m

        elif ((m - L[index - 1]) + 1 > x):
            h = m - 1

        else:
            l = m + 1

# Driver code

L=[ 1, 8, 21]
R=[4, 10, 23]
n = len(L)

k = 6

print(getKthElement(n, k, L, R))

# This code is contributed by mohit kumar
```

## C#

```csharp
// C# implementation of the approach
using System;

class GFG
{

// Function to return the kth element
// of the required series
static int getKthElement(int n, int k,
                        int[] L, int[] R)
{
    int l = 1;
    int h = n;

    // To store the number of integers that lie
    // upto the ith index
    int[] total = new int[n + 1];

    total[0] = 0;

    // Compute the number of integers
    for (int i = 0; i < n; i++)
    {
        total[i + 1] = total[i] +
                    (R[i] - L[i]) + 1;
    }

    // Stores the index, lying from 1
    // to n,
    int index = -1;

    // Using binary search, find the index
    // in which the kth element will lie
    while (l <= h)
    {
        int m = (l + h) / 2;

        if (total[m] > k)
        {
            index = m;
            h = m - 1;
        }
        else if (total[m] < k)
            l = m + 1;
        else
        {
            index = m;
            break;
        }
    }

    l = L[index - 1];
    h = R[index - 1];

    // Find the position of the kth element
    // in the interval in which it lies
    int x = k - total[index - 1];

    while (l <= h)
    {
        int m = (l + h) / 2;

        if ((m - L[index - 1]) + 1 == x)
        {
            return m;
        }

        else if ((m - L[index - 1]) + 1 > x)
            h = m - 1;

        else
            l = m + 1;
    }
    return k;
}

// Driver code
public static void Main()
{
    int[] L = { 1, 8, 21 };
    int[] R = { 4, 10, 23 };
    int n = L.Length;

    int k = 6;

    Console.WriteLine(getKthElement(n, k, L, R));
}
}

// This code is contributed by Code_Mech
```

# 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

## PHP 实现

```php
<?php
// PHP implementation of the approach

// Function to return the kth element
// of the required series
function getKthElement($n, $k, $L, $R)
{
    $l = 1;
    $h = $n;

    // To store the number of integers that lie
    // upto the ith index
    $total = array();

    $total[0] = 0;

    // Compute the number of integers
    for ($i = 0; $i < $n; $i++)
    {
        $total[$i + 1] = $total[$i] +
                        ($R[$i] - $L[$i]) + 1;
    }

    // Stores the index, lying from 1
    // to n,
    $index = -1;

    // Using binary search, find the index
    // in which the kth element will lie
    while ($l <= $h)
    {
        $m = floor(($l + $h) / 2);

        if ($total[$m] > $k)
        {
            $index = $m;
            $h = $m - 1;
        }
        else if ($total[$m] < $k)
            $l = $m + 1;
        else
        {
            $index = $m;
            break;
        }
    }

    $l = $L[$index - 1];
    $h = $R[$index - 1];

    // Find the position of the kth element
    // in the interval in which it lies
    $x = $k - $total[$index - 1];

    while ($l <= $h)
    {
        $m = floor(($l + $h) / 2);

        if (($m - $L[$index - 1]) + 1 == $x)
        {
            return $m;
        }

        else if (($m - $L[$index - 1]) + 1 > $x)
            $h = $m - 1;

        else
            $l = $m + 1;
    }
}

// Driver code
$L = array( 1, 8, 21 );
$R = array( 4, 10, 23 );
$n = count($L);

$k = 6;

echo getKthElement($n, $k, $L, $R);

// This code is contributed by Ryuga
?>
```

## JavaScript 实现

```javascript
<script>
// Javascript implementation of the approach

// Function to return the kth element
// of the required series
function getKthElement(n,k,L,R)
{
    let l = 1;
    let h = n;

    // To store the number of integers that lie
    // upto the ith index
    let total = new Array(n + 1);

    total[0] = 0;

    // Compute the number of integers
    for (let i = 0; i < n; i++)
    {
        total[i + 1] = total[i] +
                      (R[i] - L[i]) + 1;
    }

    // Stores the index, lying from 1
    // to n,
    let index = -1;

    // Using binary search, find the index
    // in which the kth element will lie
    while (l <= h)
    {
        let m = Math.floor((l + h) / 2);

        if (total[m] > k)
        {
            index = m;
            h = m - 1;
        }
        else if (total[m] < k)
            l = m + 1;
        else
        {
            index = m;
            break;
        }
    }

    l = L[index - 1];
    h = R[index - 1];

    // Find the position of the kth element
    // in the interval in which it lies
    let x = k - total[index - 1];

    while (l <= h)
    {
        let m = Math.floor((l + h) / 2);

        if ((m - L[index - 1]) + 1 == x)
        {
            return m;
        }

        else if ((m - L[index - 1]) + 1 > x)
            h = m - 1;

        else
            l = m + 1;
    }
    return k;
}

// Driver code
let L = [1, 8, 21 ];
let R = [ 4, 10, 23 ];
let n = L.length;
let k = 6;

document.write(getKthElement(n, k, L, R));

// This code is contributed by patel2127
</script>
```

**输出：**

```

```

## 复杂度分析

**时间复杂度:** `O(N)`
**辅助空间:** `O(N)`