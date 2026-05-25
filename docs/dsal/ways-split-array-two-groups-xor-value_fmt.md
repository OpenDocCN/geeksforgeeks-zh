# 将数组拆分成两组相同异或值的方法

> 原文：[https://www.geeksforgeeks.org/ways-split-array-two-groups-xor-value/](https://www.geeksforgeeks.org/ways-split-array-two-groups-xor-value/)

给定一个由 `n` 个整数组成的数组 `A`。任务是计算将给定数组元素分成两个不相交组的方法的数量，使得每组元素的异或相等。

示例：

```
Input : A[] = { 1, 2, 3 }
Output : 3
{(1), (2, 3)}, {(2), (1, 3)}, {(3), (1, 2)} 
are three ways with equal XOR value of two
groups.

Input :  A[] = { 5, 2, 3, 2 }
Output : 0
```

让我们将第一组中所有元素之间的异或表示为 `G1`，将第二组中所有元素之间的异或表示为 `G2`。现在，以下关系总是正确的：`G1⊕G2 = A1⊕A2⊕...⊕An`。
所以对于 `G1 = G2`，数组 `A` 的所有元素之间的异或等于 `0`。那么，在这种情况下，答案将是 `(2^n – 2) / 2 = (2^(n-1) – 1)`。在第二种情况下，当所有元素之间的异或不是 `0` 时，我们不能拆分数组。答案将是 `0`。

## C++

```cpp
// CPP Program to count number of ways to split
// array into two groups such that each group
// has equal XOR value
#include<bits/stdc++.h>
using namespace std;

// Return the count number of ways to split
// array into two groups such that each group
// has equal XOR value.
int countgroup(int a[], int n)
{
  int xs = 0;
  for (int i = 0; i < n; i++)
    xs = xs ^ a[i];

  // We can split only if XOR is 0. Since
  // XOR of all is 0, we can consider all
  // subsets as one group.
  if (xs == 0)
    return (1 << (n-1)) - 1;

  return 0;
}

// Driver Program
int main()
{
  int a[] = { 1, 2, 3 };
  int n = sizeof(a)/sizeof(a[0]);
  cout << countgroup(a, n) << endl;
  return 0;
}
```

## Java

```java
// Java Program to count number of ways
// to split array into two groups such
// that each group has equal XOR value
import java.io.*;
import java.util.*;

class GFG {

// Return the count number of ways to split
// array into two groups such that each group
// has equal XOR value.
static int countgroup(int a[], int n) {
    int xs = 0;
    for (int i = 0; i < n; i++)
    xs = xs ^ a[i];

    // We can split only if XOR is 0. Since
    // XOR of all is 0, we can consider all
    // subsets as one group.
    if (xs == 0)
    return (1 << (n - 1)) - 1;

    return 0;
}

// Driver program
public static void main(String args[]) {
    int a[] = {1, 2, 3};
    int n = a.length;
    System.out.println(countgroup(a, n));
}
}

// This code is contributed by Nikita Tiwari.
```

## Python 3

```python
# Python3 code to count number of ways
# to split array into two groups such
# that each group has equal XOR value

# Return the count of number of ways
# to split array into two groups such
# that each group has equal XOR value.
def countgroup(a, n):
    xs = 0
    for i in range(n):
        xs = xs ^ a[i]

    # We can split only if XOR is 0.
    # Since XOR of all is 0, we can
    # consider all subsets as one group.
    if xs == 0:
        return (1 << (n-1)) - 1

    return 0

# Driver Program
a = [1, 2, 3]
n = len(a)
print(countgroup(a, n))

# This code is contributed by "Sharad_Bhardwaj".
```

## C#

```csharp
// C# Program to count number of ways
// to split array into two groups such
// that each group has equal XOR value
using System;

class GFG {

    // Return the count number of ways to split
    // array into two groups such that each group
    // has equal XOR value.
    static int countgroup(int[] a, int n)
    {
        int xs = 0;
        for (int i = 0; i < n; i++)
            xs = xs ^ a[i];

        // We can split only if XOR is 0. Since
        // XOR of all is 0, we can consider all
        // subsets as one group.
        if (xs == 0)
            return (1 << (n - 1)) - 1;

        return 0;
    }

    // Driver program
    public static void Main()
    {
        int[] a = { 1, 2, 3 };
        int n = a.Length;
        Console.WriteLine(countgroup(a, n));
    }
}

// This code is contributed by vt_m.
```

## PHP

```php
<?php
// PHP Program to count number
// of ways to split array into
// two groups such that each 
// group has equal XOR value

// Return the count number of
// ways to split array into
// two groups such that each 
// grouphas equal XOR value.
function countgroup($a, $n)
{
    $xs = 0;
    for ($i = 0; $i < $n; $i++)
        $xs = $xs ^ $a[$i];

    // We can split only if XOR is 0. Since
    // XOR of all is 0, we can consider all
    // subsets as one group.
    if ($xs == 0)
        return (1 << ($n - 1)) - 1;

    return 0;
}

// Driver Code
$a = array(1, 2, 3);
$n = count($a);
echo countgroup($a, $n);

// This code is contributed by anuj_67.
?>
```

## JavaScript

```javascript
<script>

      // JavaScript Program to count number of ways to split
      // array into two groups such that each group
      // has equal XOR value

      // Return the count number of ways to split
      // array into two groups such that each group
      // has equal XOR value.
      function countgroup(a, n) {
        var xs = 0;
        for (var i = 0; i < n; i++) xs = xs ^ a[i];

        // We can split only if XOR is 0. Since
        // XOR of all is 0, we can consider all
        // subsets as one group.
        if (xs == 0) return (1 << (n - 1)) - 1;
      }

      // Driver Program

      var a = [1, 2, 3];
      var n = a.length;
      document.write(countgroup(a, n) + "<br>");

</script>
```

**输出：**

```
3
```