# 特殊筛子中未标记整数的数量

> 原文：[https://www.geeksforgeeks.org/number-unmarked-integers-special-sieve/](https://www.geeksforgeeks.org/number-unmarked-integers-special-sieve/)

## 问题描述

给定一个包含从 `2` 到 `N` 的数字的数组 `A`。对其进行特殊类型的筛选。
筛选程序如下：

1.  创建一个数组，其中的元素是从 `2` 到 `N` 的连续整数，并将数组中的每个元素标记为未标记。
2.  让一个整数 `Q = N`，标记 `Q` 除了 `Q` 本身在数组中的所有适当因子。
3.  找到未标记的小于 `Q` 的最大数字，给它赋值 `Q`，从第 2 步开始重复。如果没有更多未标记的元素，则停止。

筛选后求未标记整数的个数。

## 示例

**例 1：**

```
Input : N = 5 
Output : Number of unmarked elements = 3
Explanation : We create array A[] = { 2, 3, 4, 5 }.
2 is marked as it is a proper divisor of 4.
```

**例 2：**

```
Input : N = 4
Output : Number of unmarked elements = 2
```

## 方法分析

**天真方法：**
一个基本方法是运行两个循环。通过检查 `a[i] % Q = 0`，遍历整个数组的外循环和从 `2` 到 `Q` 遍历以取消标记 `Q` 的所有适当除数的内循环。
**时间复杂度：** `O(N^2)`

**高效方法：**
简单的观察表明，其实没有必要在这里做筛选，取而代之，`N` 的值将决定答案。
**情况 1：** 如果 `N` 为奇数，则未标记元素数为 `(N/2) + 1`。
**情况 2：** 如果 `N` 为偶数，则未标记元素的数量为 `(N/2)`。
**时间复杂度：** `O(1)`

**示例详解：**

> 输入：`N = 5`
> 输出：`3`
> `A[] = { 2, 3, 4, 5 }`
> 步骤：
> 1. `Q = 5`：标记 `Q` 的所有适当除数，这里没有元素，所以每个元素都没有标记。
> 2. `Q = 4`：标记 `Q` 的所有适当除数。这里 `2` 被标记，未标记的元素是 `{3, 4, 5}`。
> 3. `Q = 3`：现在不能再做标记了，就此打住。
> 所以未标记的元素个数是 `3`，即 `{3, 4, 5}`。
> 如果 `N` 为奇数，结果为 `(N/2)+1 = (5/2)+1 = 2+1 = 3`。

> 输入：`N = 4`
> 输出：`2`
> `A[] = { 2, 3, 4 }`
> 步骤：
> 1. `Q = 4`：标记 `Q` 的所有适当除数。所以这里 `2` 被标记，未标记的元素是 `{3, 4}`。
> 2. `Q = 3`：现在不能再做标记了，就此打住。
> 所以筛选后未标记元素的数量为 `{3, 4}`，即 `2`。
> 如果 `N` 为偶数，结果应为 `(N/2) = (4/2) = 2`。

## 代码实现

### C++

```cpp
// C++ Program to determine the
// number of unmarked integers in
// a special sieve
#include <bits/stdc++.h>
using namespace std;

int countUnmarked(int N)
{
    if (N % 2 == 0)
       return N/2;
    else
       return N/2 + 1;
}

// Driver Code
int main()
{
    int N = 4;
    cout << "Number of unmarked elements: "
         << countUnmarked(N) << endl;
    return 0;
}
```

### Java

```java
// Java Program to determine
// the number of unmarked
// integers in a special sieve
import java.io.*;

class GFG
{
    static int countUnmarked(int N)
    {
        if (N % 2 == 0)
            return N / 2;
        else
            return N / 2 + 1;
    }

    // Driver Code
    public static void main (String[] args)
    {
        int N = 4;
        System.out.println("Number of unmarked " +
                           "elements: " +
                           countUnmarked(N));
    }
}

// This code is contributed
// by anuj_67.
```

### Python 3

```python
# Python3 Program to determine
# the number of unmarked
# integers in a special sieve
def countUnmarked(N):
    if (N % 2 == 0):
        return N / 2;
    else:
        return N / 2 + 1;

# Driver Code
N = 4;
print("Number of unmarked elements:",
      int(countUnmarked(N)));

# This code is contributed
# by mits
```

### C#

```csharp
// C# Program to determine
// the number of unmarked
// integers in a special sieve
using System;

class GFG
{
    static int countUnmarked(int N)
    {
        if (N % 2 == 0)
            return N / 2;
        else
            return N / 2 + 1;
    }

    // Driver Code
    public static void Main ()
    {
        int N = 4;
        Console.WriteLine("Number of unmarked " +
                          "elements: " +
                          countUnmarked(N));
    }
}

// This code is contributed
// by anuj_67.
```

### PHP

```php
<?php
// PHP Program to determine
// the number of unmarked
// integers in a special sieve

function countUnmarked($N)
{
    if ($N % 2 == 0)
        return $N / 2;
    else
        return $N / 2 + 1;
}

// Driver Code
$N = 4;
echo "Number of unmarked elements: ",
     countUnmarked($N);

// This code is contributed
// by anuj_67.
?>
```

### JavaScript

```javascript
<script>
// javascript Program to determine
// the number of unmarked
// integers in a special sieve
function countUnmarked(N) {
    if (N % 2 == 0)
        return N / 2;
    else
        return N / 2 + 1;
}

// Driver Code
var N = 4;
document.write("Number of unmarked " +
               "elements: " + countUnmarked(N));

// This code is contributed by todaysgaurav
</script>
```

**输出：**

```
Number of unmarked elements: 2
```