# 找出只能用数字 3、4 构成且最大长度为 n 的数字的个数

> 原文:[https://www . geeksforgeeks . org/find-the-count-of-numbers-that-can-be-formed-using-digits-3-4-only-and-having-length-at-max-n/](https://www.geeksforgeeks.org/find-the-count-of-numbers-that-can-be-formed-using-digits-3-4-only-and-having-length-at-max-n/)

给定一个数 `n`，找出这些数的个数，这些数只能用数字 3 和 4 构成，长度最大为 `n`。

**例:**

```
Input : N = 2
Output : 6
Explanation : 3, 4, 33, 34, 43, 44 
are numbers having length 2 and digits 3 and 4 only.

Input : N = 1
Output : 2
Explanation : 3, 4 are the only such numbers.
```

**接近:**
长度 1 有 2 个数字。他们分别是 3 和 4。长度为 2 的数字有 4 个。他们是 33，34，43 和 44。长度为 3 的数字有 8 个。它们是 333，334，343，344，433，434，443，444。长度每增加 1，数字就会增加 2 倍。
很容易证明:对于前一长度的任何数字，可以附加 3 或 4，所以前一长度的一个数字产生下一长度的两个数字。
那么对于长度 `N`，这样的长度 `N` 的数的量正好是 `2^N`，但是在问题中，我们需要长度不大于 `N` 的数的个数，我们来总结一下。`2^1 = 2`，`2^1 + 2^2 = 2 + 4 = 6`，`2^1+2^2+2^3= 2+4+8 = 14`，`2^1+2^2+2^3+2^4= 2+4+8+16 = 30`。
人们可以注意到，之前所有 2 的幂的和等于下一个 2 的幂减去第一个 2 的幂。所以问题的答案是 `2^(N+1) – 2`。

以下是上述方法的实施:

## C++

```cpp
// Cpp program to find the count of numbers that
// can be formed using digits 3, 4 only and
// having length at max N.
#include <bits/stdc++.h>
using namespace std;

// Function to find the count of numbers that
// can be formed using digits 3, 4 only and
// having length at max N.
long long numbers(int n)
{
    return (long long)(pow(2, n + 1)) - 2;
}

// Driver code
int main()
{
    int n = 2;

    cout << numbers(n);

    return 0;
}
```

## Java 语言

```java
// Java program to find the count of numbers that
// can be formed using digits 3, 4 only and
// having length at max N.

class GFG
{

// Function to find the count of numbers that
// can be formed using digits 3, 4 only and
// having length at max N.
static long numbers(int n)
{
    return (long)(Math.pow(2, n + 1)) - 2;
}

// Driver code
public static void main(String args[])
{
    int n = 2;

    System.out.println( numbers(n));
}
}

// This code is contributed by Arnab Kundu
```

## Python 3

```python
# Python3 program to find the count of
# numbers that can be formed using digits
# 3, 4 only and having length at max N.

# Function to find the count of numbers
# that can be formed using digits 3, 4
# only and having length at max N.
def numbers(n):
    return pow(2, n + 1) - 2

# Driver code
n = 2
print(numbers(n))

# This code is contributed
# by Shrikant13
```

## C#

```csharp
// C# program to find the count of numbers that
// can be formed using digits 3, 4 only and
// having length at max N.
using System;

class GFG
{

// Function to find the count of numbers that
// can be formed using digits 3, 4 only and
// having length at max N.
static long numbers(int n)
{
    return (long)(Math.Pow(2, n + 1)) - 2;
}

// Driver code
static void Main()
{
    int n = 2;

    Console.WriteLine( numbers(n));
}
}

// This code is contributed by mits
```

## PHP

```php
<?php
// PHP program to find the count of
// numbers that can be formed using
// digits 3, 4 only and having length
// at max N.

// Function to find the count of numbers
// that can be formed using digits 3, 4 only
// and having length at max N.
function numbers($n)
{
    return (pow(2, $n + 1)) - 2;
}

// Driver code
$n = 2;

echo numbers($n);

// This code is contributed
// by Akanksha Rai
?>
```

## JavaScript

```javascript
<script>
// javascript program to find the count of numbers that
// can be formed using digits 3, 4 only and
// having length at max N.
    // Function to find the count of numbers that
    // can be formed using digits 3, 4 only and
    // having length at max N.
    function numbers(n) {
        return  (Math.pow(2, n + 1)) - 2;
    }

    // Driver code

        var n = 2;

        document.write(numbers(n));

// This code is contributed by Princi Singh
</script>
```

**Output:**

```
6
```