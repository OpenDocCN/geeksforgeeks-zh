# 有效反转数字位的程序

> 原文：[https://www.geeksforgeeks.org/program-to-invert-bits-of-a-number-efficiently/](https://www.geeksforgeeks.org/program-to-invert-bits-of-a-number-efficiently/)

给定一个非负整数 `N`。任务是反转数字 `N` 的位，并打印反转位后得到的数字的十进制等效值。
**注**：领先 0 不考虑。

## 示例

```
Input : 11
Output : 4
(11)10 = (1011)2
After inverting the bits, we get:
(0100)2 = (4)10.

Input : 20
Output : 11
(20)10 = (10100)2.
After inverting the bits, we get:
(01011)2 = (11)10.
```

类似的问题已经在[中讨论过了，反转一个数的实际位](https://www.geeksforgeeks.org/invert-actual-bits-number/)。
本文讨论了一种使用按位运算符的有效方法。下面是解决问题的分步算法：

## 算法

1.  计算给定数字的总位数。这可以通过计算完成：
    ```
    X = log2N
    ```
    其中 `N` 是给定的数字，`X` 是 `N` 的总位数。

2.  下一步是生成一个具有 `X` 位且所有位都置位的数字。即，*11111….X-times*。这可以通过计算完成：
    ```
    Step-1: M = 1 << X
    Step-2: M = M | (M-1)
    ```
    其中，`M` 是设置了所有位的所需 `X` 位数字。

3.  最后一步是计算 `M` 与 `N` 的逐位异或，这将是我们的答案。

## 实现

以下是上述方法的实现：

### C++

```cpp
// C++ program to invert actual bits
// of a number.
#include <bits/stdc++.h>

using namespace std;

// Function to invert bits of a number
int invertBits(int n)
{
    // Calculate number of bits of N-1;
    int x = log2(n) ;

    int m = 1 << x;

    m = m | m - 1;

    n = n ^ m;

    return n;
}

// Driver code
int main()
{
    int n = 20;

    cout << invertBits(n);

    return 0;
}
```

### Java

```java
// Java program to invert
// actual bits of a number.
import java.util.*;

class GFG
{
// Function to invert
// bits of a number
static int invertBits(int n)
{
    // Calculate number of bits of N-1;
    int x = (int)(Math.log(n) /
                  Math.log(2)) ;

    int m = 1 << x;

    m = m | m - 1;

    n = n ^ m;

    return n;
}

// Driver code
public static void main(String[] args)
{
    int n = 20;

    System.out.print(invertBits(n));
}
}

// This code is contributed by Smitha
```

### Python 3

```python
# Python3 program to invert actual
# bits of a number.
import math

# Function to invert bits of a number
def invertBits(n):

    # Calculate number of bits of N-1
    x = int(math.log(n, 2))

    m = 1 << x

    m = m | m - 1

    n = n ^ m

    return n

# Driver code
n = 20

print(invertBits(n))

# This code is contributed 29AjayKumar
```

### C#

```csharp
// C# program to invert
// actual bits of a number.
using System;

public class GFG
{
// Function to invert
// bits of a number
static int invertBits(int n)
{
    // Calculate number of bits of N-1;
    int x = (int)(Math.Log(n) /
                  Math.Log(2)) ;

    int m = 1 << x;

    m = m | m - 1;

    n = n ^ m;

    return n;
}

// Driver code
public static void Main()
{
    int n = 20;

    Console.Write(invertBits(n));
}
}

// This code is contributed by Subhadeep
```

### PHP

```php
<?php
// PHP program to invert actual
// bits of a number.

// Function to invert bits
// of a number
function invertBits($n)
{
    // Calculate number of
    // bits of N-1;
    $x = log($n, 2);

    $m = 1 << $x;

    $m = $m | $m - 1;

    $n = $n ^ $m;

    return $n;
}

// Driver code
$n = 20;

echo(invertBits($n));

// This code is contributed
// by mits
?>
```

### JavaScript

```javascript
<script>

// Javascript program to invert actual bits
// of a number.

// Function to invert bits of a number
function invertBits(n)
{
    // Calculate number of bits of N-1;
    let x = parseInt(Math.log(n) / Math.log(2)) ;

    let m = 1 << x;

    m = m | m - 1;

    n = n ^ m;

    return n;
}

// Driver code
    let n = 20;

    document.write(invertBits(n));

</script>
```

**输出：**

```
11
```

**时间复杂度**：`O(log2n)`
**辅助空间**：`O(1)`