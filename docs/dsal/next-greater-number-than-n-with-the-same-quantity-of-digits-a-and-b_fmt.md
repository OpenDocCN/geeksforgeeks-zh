# 下一个大于 N 的数字，位数 A 和 B 相同

> 原文: [https://www.geeksforgeeks.org/next-greater-number-than-n-with-the-same-quantity-of-digits-a-and-b/](https://www.geeksforgeeks.org/next-greater-number-than-n-with-the-same-quantity-of-digits-a-and-b/)

给定一个数字`N`和两位数`A`和`B`。任务是找到最少的不小于`N`的数字，其中包含相同数量的数字`A`和`B`。
**注**: `N <= 10^7`
**例:**

> **输入** : `N = 4500`，`A = 4`，`B = 7`
> **输出** : `4747`
> 大于 4500 的数字，数字‘4’和数字‘7’数量相同，为 4747。
> **输入** : `N = 99999999`，`A = 6`，`B = 7`
> **输出** : `6666677777`

下面是解决这个问题的分步算法:

1.  如果`N`的长度是奇数，那么结果数的长度将是`N+1`，因为`A`和`B`的数量必须相等。
2.  如果`N`的长度是偶数，那么结果数的长度将是`N`或`N+2`。
3.  我们将通过逐个追加`A`和`B`来递归生成数字，并在下一次递归调用中取两者中的最小值。
4.  最后返回大于或等于`N`的最小数字。

以下是上述思路的实现:

## C++

```cpp
// C++ program to find next greater Number
// than N with the same quantity of
// digits A and B

#include <bits/stdc++.h>
using namespace std;

// Recursive function to find the required number
long findNumUtil(long res, int a, int aCount, int b, int bCount, int n)
{
    if (res > 1e11)
        return 1e11;

    // If the resulting number is >= n and
    // count of a = count of b, return the number
    if (aCount == bCount && res >= n)
        return res;

    // select minimum of two and call the function again
    return min(findNumUtil(res * 10 + a, a, aCount + 1, b, bCount, n),
               findNumUtil(res * 10 + b, a, aCount, b, bCount + 1, n));
}

// Function to find the number next greater Number
// than N with the same quantity of
// digits A and B
int findNum(int n, int a, int b)
{
    int result = 0;
    int aCount = 0;
    int bCount = 0;

    return findNumUtil(result, a, aCount, b, bCount, n);
}

// Driver code
int main()
{
    int N = 4500;
    int A = 4;
    int B = 7;

    cout << findNum(N, A, B);

    return 0;
}
```

## Java

```java
// Java program to find next greater Number
// than N with the same quantity of
// digits A and B

public class GFG {

    // Recursive function to find the required number
    static long findNumUtil(long res, int a, int aCount, int b, int bCount, int n)
    {
        if (res > 1e11)
            return (long) 1e11;

        // If the resulting number is >= n and
        // count of a = count of b, return the number
        if (aCount == bCount && res >= n)
            return res;

        // select minimum of two and call the function again
        return Math.min(findNumUtil(res * 10 + a, a, aCount + 1, b, bCount, n),
                   findNumUtil(res * 10 + b, a, aCount, b, bCount + 1, n));
    }

    // Function to find the number next greater Number
    // than N with the same quantity of
    // digits A and B
    static int findNum(int n, int a, int b)
    {
        int result = 0;
        int aCount = 0;
        int bCount = 0;

        return (int) findNumUtil(result, a, aCount, b, bCount, n);
    }

    // Driver code
    public static void main(String args[])
    {
           int N = 4500;
            int A = 4;
            int B = 7;

            System.out.println(findNum(N, A, B));

    }
    // This Code is contributed by ANKITRAI1
}
```

## Python 3

```python
# Python 3 program to find next greater
# Number than N with the same quantity of
# digits A and B

# Recursive function to find the
# required number
def findNumUtil(res, a, aCount, b, bCount, n):
    if (res > 1e11):
        return 1e11

    # If the resulting number is >= n
    # and count of a = count of b,
    # return the number
    if (aCount == bCount and res >= n):
        return res

    # select minimum of two and call
    # the function again
    return min(findNumUtil(res * 10 + a,
                           a, aCount + 1, b, bCount, n),
               findNumUtil(res * 10 + b, a,
                           aCount, b, bCount + 1, n))

# Function to find the number next
# greater Number than N with the
# same quantity of digits A and B
def findNum(n, a, b):
    result = 0
    aCount = 0
    bCount = 0

    return findNumUtil(result, a, aCount,
                             b, bCount, n)

# Driver code
if __name__ == '__main__':
    N = 4500
    A = 4
    B = 7

    print(findNum(N, A, B))

# This code is contributed by
# Sanjit_Prasad
```

## C#

```csharp
// C# program to find next greater Number
// than N with the same quantity of
// digits A and B
using System;

class GFG
{

// Recursive function to find the required number
static long findNumUtil(long res, int a, int aCount,
                        int b, int bCount, int n)
{
    if (res > 1e11)
        return (long) 1e11;

    // If the resulting number is >= n and
    // count of a = count of b, return the number
    if (aCount == bCount && res >= n)
        return res;

    // select minimum of two and call
    // the function again
    return Math.Min(findNumUtil(res * 10 + a, a,
                                aCount + 1, b, bCount, n),
            findNumUtil(res * 10 + b, a, aCount,
                             b, bCount + 1, n));
}

// Function to find the number next
// greater Number than N with the
// same quantity of digits A and B
static int findNum(int n, int a, int b)
{
    int result = 0;
    int aCount = 0;
    int bCount = 0;

    return (int) findNumUtil(result, a, aCount,
                                     b, bCount, n);
}

// Driver code
public static void Main()
{
    int N = 4500;
    int A = 4;
    int B = 7;

    Console.WriteLine(findNum(N, A, B));
}
}

// This code is contributed by Shashank
```

## PHP

```php
<?php
// PHP program to find next greater Number
// than N with the same quantity of
// digits A and B

// Recursive function to find the required number
function findNumUtil($res, $a, $aCount, $b, $bCount, $n)
{
    if ($res > 100000000000)
        return 10000000000;

    // If the resulting number is >= n and
    // count of a = count of b, return the number
    if ($aCount == $bCount && $res >= $n)
        return $res;

    // select minimum of two and call the function again
    return min(findNumUtil($res * 10 + $a, $a, $aCount + 1, $b, $bCount, $n),
            findNumUtil($res * 10 + $b, $a, $aCount, $b, $bCount + 1, $n));
}

// Function to find the number next greater Number
// than N with the same quantity of
// digits A and B
function findNum($n, $a, $b)
{
    $result = 0;
    $aCount = 0;
    $bCount = 0;

    return findNumUtil($result, $a, $aCount, $b, $bCount, $n);
}

// Driver code

    $N = 4500;
    $A = 4;
    $B = 7;

    echo findNum($N, $A, $B);

// This Code is contributed by mits
?>
```

## JavaScript

```javascript
<script>
    // Javascript program to find next greater Number
    // than N with the same quantity of
    // digits A and B

    // Recursive function to find the required number
    function findNumUtil(res, a, aCount, b, bCount, n)
    {
        if (res > 1e11)
            return 1e11;

        // If the resulting number is >= n and
        // count of a = count of b, return the number
        if (aCount == bCount && res >= n)
            return res;

        // select minimum of two and call
        // the function again
        return Math.min(findNumUtil(res * 10 + a, a,
                                    aCount + 1, b, bCount, n),
                findNumUtil(res * 10 + b, a, aCount,
                             b, bCount + 1, n));
    }

    // Function to find the number next
    // greater Number than N with the
    // same quantity of digits A and B
    function findNum(n, a, b)
    {
        let result = 0;
        let aCount = 0;
        let bCount = 0;

        return findNumUtil(result, a, aCount,
                                         b, bCount, n);
    }

    let N = 4500;
    let A = 4;
    let B = 7;

    document.write(findNum(N, A, B));

    // This code is contributed by divyesh072019.
</script>
```

**Output:**

```
4747
```