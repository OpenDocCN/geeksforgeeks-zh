# 尼科马修斯定理（第 k 组奇数正数之和）

> 原文：[https://www.geeksforgeeks.org/sum-k-th-group-odd-positive-numbers/](https://www.geeksforgeeks.org/sum-k-th-group-odd-positive-numbers/)

正奇数按升序排列为 1，3，5，7，9，11，13，15，17，19，…并分组为 (1)、(3, 5)、(7, 9, 11)、(13, 15, 17, 19)、…。等等。
因此，第一组是 (1)，第二组是 (3, 5)，第三组是 (7, 9, 11) 等。一般来说，第 `k` 组包含序列的下 `k` 个元素。
给定 `k`，求第 `k` 组的和。

**举例：**

```
Input : k = 3
Output : 27
3rd group is (7, 9, 11) and the sum is 27.

Input : k = 1
Output : 1
```

## 方法 1：O(n)

思路是找到第 `k` 组的第一个元素。
例如：

*   第一组的第一个元素是 1，这是第一个奇数。
*   第二组的第一个元素是 3，这是第 2 个奇数。
*   第三组的第一个元素是 7，这是第 4 个奇数。
*   第 4 组的第一个元素是 13，这是第 7 个奇数。
*   等等。

一般来说，第 `k` 组的第一个元素是第 `n` 个奇数，其中 `n = (1+2+3+……+(k–1))+1`。
现在，我们知道，第 `n` 个奇数是 `2n–1`。这给了我们第一个 `k` 组的元素。我们也知道群中有 `k` 个元素，所以我们可以通过简单地从 `2n–1` 向上计数，乘以 2，再乘以 `k`，然后将它们全部相加来找到它们的和。这给了我们一个线性时间解。

### C++

```cpp
// CPP program to find sum of k-th group of
// positive odd integers.
#include <bits/stdc++.h>
using namespace std;

// Return the sum of k-th group of positive
// odd integers.
int kthgroupsum(int k)
{
    // Finding first element of kth group.
    int cur = (k * (k - 1)) + 1;
    int sum = 0;

    // Finding the sum.
    while (k--) {
        sum += cur;
        cur += 2;
    }

    return sum;
}

// Driver code
int main()
{
    int k = 3;
    cout << kthgroupsum(k) << endl;
    return 0;
}
```

### Java

```java
// Java code to find sum of k-th group
// of positive odd integers.
import java.util.Arrays;
import java.util.Collections;

class GFG
{
    // Return the sum of k-th group
    // of positive odd integers.
    public static int kthgroupsum(int k)
    {
        // Finding first element of kth group.
        int cur = (k * (k - 1)) + 1;
        int sum = 0;

        // Finding the sum.
        while (k-- > 0)
        {
            sum += cur;
            cur += 2;
        }

        return sum;
    }

    // Driver program to test above methods
    public static void main(String[] args)
    {
        int k = 3;
        System.out.print(kthgroupsum(k));
    }
}

// This code is contributed by Chhavi
```

### Python 3

```python
# Python3 code to find sum of k-th group
# of positive odd integers.

# Return the sum of k-th group of
# positive odd integers.
def kthgroupsum( k ):

    # Finding first element of kth group.
    cur = int((k * (k - 1)) + 1)
    sum = 0

    # Finding the sum.
    while k:
        sum += cur
        cur += 2
        k=k-1

    return sum

# Driver code
k = 3
print(kthgroupsum(k))

# This code is contributed by "Sharad_Bhardwaj".
```

### C#

```csharp
// C# code to find sum of k-th group
// of positive odd integers.
using System;

class GFG {

    // Return the sum of k-th group
    // of positive odd integers.
    public static int kthgroupsum(int k)
    {

        // Finding first element of kth group.
        int cur = (k * (k - 1)) + 1;
        int sum = 0;

        // Finding the sum.
        while (k-- > 0) {
            sum += cur;
            cur += 2;
        }

        return sum;
    }

    // Driver program to test above methods
    public static void Main()
    {
        int k = 3;

        Console.WriteLine(kthgroupsum(k));
    }
}

// This code is contributed by vt_m.
```

### PHP

```php
<?php
// PHP program to find
// sum of k-th group of
// positive odd integers.

// Return the sum of
// k-th group of positive
// odd integers.
function kthgroupsum($k)
{

    // Finding first element
    // of kth group.
    $cur = ($k * ($k - 1)) + 1;
    $sum = 0;

    // Finding the sum.
    while ($k--)
    {
        $sum += $cur;
        $cur += 2;
    }
    return $sum;
}

// Driver code
$k = 3;
echo kthgroupsum($k) ;

// This code is contributed by anuj_67.
?>
```

### JavaScript

```javascript
<script>
// javascript program to find
// sum of k-th group of
// positive odd integers.

// Return the sum of
// k-th group of positive
// odd integers.
function kthgroupsum(k)
{

    // Finding first element
    // of kth group.
    let cur = (k * (k - 1)) + 1;
    let sum = 0;

    // Finding the sum.
    while (k--)
    {
        sum += cur;
        cur += 2;
    }
    return sum;
}

// Driver code
let k = 3;
document.write(kthgroupsum(k));

// This code is contributed by _saurabh_jaiswal.
</script>
```

**输出：**

```
27
```

## 方法二：O(1)

一个比较棘手的解决办法就是找 `k^3`。很容易观察到，`k` 组的和将是 `k^3`。
以下是本办法的实施：

### C++

```cpp
// Efficient CPP program to find sum of k-th
// group of positive odd integers.
#include <bits/stdc++.h>
using namespace std;

// Return the sum of kth group of positive
// odd integer.
int kthgroupsum(int k)
{
    return k * k * k;
}

// Driven Program
int main()
{
    int k = 3;
    cout << kthgroupsum(k) << endl;
    return 0;
}
```

### Java

```java
// Efficient Java code to find sum of k-th
// group of positive odd integers.
import java.util.Arrays;
import java.util.Collections;

class GFG
{
    // Return the sum of kth group of
    // positive odd integer.
    public static int kthgroupsum(int k)
    {
        return k * k * k;
    }

    // Driver program to test above methods
    public static void main(String[] args)
    {
        int k = 3;
        System.out.print( kthgroupsum(k));
    }
}

// This code is contributed by Chhavi
```

### Python 3

```python
# Efficient Python code to find sum of
# k-th group of positive odd integers.

# Return the sum of kth group of positive
# odd integer.
def kthgroupsum( k ):
    return k * k * k

# Driver code
k = 3
print(kthgroupsum(k))

# This code is contributed by "Sharad_Bhardwaj".
```

### C#

```csharp
// Efficient C# code to find sum of k-th
// group of positive odd integers.
using System;

class GFG {

    // Return the sum of kth group of
    // positive odd integer.
    public static int kthgroupsum(int k)
    {
        return k * k * k;
    }

    // Driver program to test above methods
    public static void Main()
    {
        int k = 3;

        Console.WriteLine(kthgroupsum(k));
    }
}

// This code is contributed by vt_m.
```

### PHP

```php
<?php
// Efficient PHP program to
// find sum of k-th group of
// positive odd integers.

// Return the sum of kth group
// of positive odd integer.
function kthgroupsum( $k)
{
    return $k * $k *$k;
}

// Driven Code
$k = 3;
echo kthgroupsum($k);

// This code is contributed by anuj_67.
?>
```

### JavaScript

```javascript
<script>
// Efficient Javascript program to
// find sum of k-th group of
// positive odd integers.

// Return the sum of kth group
// of positive odd integer.
function kthgroupsum(k)
{
    return k * k * k;
}

// Driven Code
let k = 3;
document.write(kthgroupsum(k));

// This code is contributed by _saurabh_jaiswal.
</script>
```

**输出：**

```
27
```