# 如何打开数字中的特定位？

> 原文：[https://www.geeksforgeeks.org/turn-particular-bit-number-2/](https://www.geeksforgeeks.org/turn-particular-bit-number-2/)

给定一个数字 `n` 和值 `k`，打开 `n` 中的第 `k` 位。
示例：

```
Input:  n = 4, k = 2
Output: 6

Input:  n = 3, k = 3
Output: 7

Input:  n = 64, k = 4
Output: 72

Input:  n = 64, k = 5
Output: 80
```

思路是用按位 `<<` 和 `|` 运算符。使用表达式 `(1 << (k - 1))`，我们得到一个除了第 `k` 位为 1 外其他位都为 0 的数字。如果将这个表达式与 `n` 进行按位或（`|`）运算，我们得到一个数字，其所有位都与 `n` 相同，除了第 `k` 位被置为 1。
下面是上面思路的实现。

## C++

```cpp
// CPP program to turn on a particular bit
#include <iostream>
using namespace std;

// Returns a number that has all bits same as n
// except the k'th bit which is made 1
int turnOnK(int n, int k)
{
    // k must be greater than 0
    if (k <= 0)
        return n;

    // Do | of n with a number with all
    // unset bits except the k'th bit
    return (n | (1 << (k - 1)));
}

// Driver program to test above function
int main()
{
    int n = 4;
    int k = 2;
    cout << turnOnK(n, k);
    return 0;
}
```

## Java

```java
// Java program to turn on a particular
// bit
class GFG {

    // Returns a number that has all
    // bits same as n except the k'th
    // bit which is made 1
    static int turnOnK(int n, int k)
    {

        // k must be greater than 0
        if (k <= 0)
            return n;

        // Do | of n with a number with
        // all unset bits except the
        // k'th bit
        return (n | (1 << (k - 1)));
    }

    // Driver program to test above
    // function
    public static void main(String [] args)
    {
        int n = 4;
        int k = 2;
        System.out.print(turnOnK(n, k));
    }
}

// This code is contributed by Smitha
```

## Python 3

```python
# Python 3 program to turn on a
# particular bit

# Returns a number that has all
# bits same as n except the k'th
# bit which is made 1
def turnOnK(n, k):

    # k must be greater than 0
    if (k <= 0):
        return n

    # Do | of n with a number
    # with all unset bits except
    # the k'th bit
    return (n | (1 << (k - 1)))

# Driver program to test above
# function
n = 4
k = 2
print(turnOnK(n, k))

# This code is contributed by
# Smitha
```

## C#

```csharp
// C# program to turn on a particular
// bit
using System;

class GFG {

    // Returns a number that has all
    // bits same as n except the k'th
    // bit which is made 1
    static int turnOnK(int n, int k)
    {

        // k must be greater than 0
        if (k <= 0)
            return n;

        // Do | of n with a number
        // with all unset bits except
        // the k'th bit
        return (n | (1 << (k - 1)));
    }

    // Driver program to test above
    // function
    public static void Main()
    {
        int n = 4;
        int k = 2;
        Console.Write(turnOnK(n, k));
    }
}

// This code is contributed by Smitha
```

## PHP

```php
<?php
// PHP program to turn on a particular bit

// Returns a number that has
// all bits same as n except
// the k'th bit which is made 1
function turnOnK($n, $k)
{

    // k must be greater than 0
    if ($k <= 0)
        return $n;

    // Do | of n with a number with all
    // unset bits except the k'th bit
    return ($n | (1 << ($k - 1)));
}

    // Driver Code
    $n = 4;
    $k = 2;
    echo turnOnK($n, $k);

// This code is contributed by m_kit
?>
```

## JavaScript

```javascript
<script>
    // Javascript program to turn on a particular bit

    // Returns a number that has all
    // bits same as n except the k'th
    // bit which is made 1
    function turnOnK(n, k)
    {

        // k must be greater than 0
        if (k <= 0)
            return n;

        // Do | of n with a number
        // with all unset bits except
        // the k'th bit
        return (n | (1 << (k - 1)));
    }

    let n = 4;
    let k = 2;
    document.write(turnOnK(n, k));

// This code is contributed by suresh07.
</script>
```

**Output:**

```
6
```