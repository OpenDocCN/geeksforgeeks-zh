# 数字二进制表示中模式的出现

> 原文：[https://www.geeksforgeeks.org/occurrences-of-a-pattern-in-binary-representation-of-a-number/](https://www.geeksforgeeks.org/occurrences-of-a-pattern-in-binary-representation-of-a-number/)

给定一个字符串`pat`和一个整数`N`，任务是在`N`的二进制表示中找到模式`pat`的出现次数。

**举例:**

> **输入:** `N = 2`，`pat = "101"`
> **输出:** 0
> 模式“101”不出现在二进制表示的 2 (10)中。
> **输入:** `N = 10`，`pat = "101"`
> **输出:** 1
> 10 的二进制表示为 1010，给定的模式只出现一次。

**天真方法:** 将数字转换为其二进制字符串表示，然后使用[模式匹配算法](https://www.geeksforgeeks.org/kmp-algorithm-for-pattern-searching/)检查模式在二进制表示中出现的次数。

**高效方法:**

1.  将二进制模式转换为十进制表示。
2.  取一个整数`all_one`，其二进制表示由所有设置的位组成(等于模式中的位数)。
3.  现在执行`N & all_one`将只保留最后一个`k`位不变(其他位将为 0)，其中`k`是模式中的位数。
4.  现在如果`N == pattern`，则意味着`N`最终在其二进制表示中包含了该模式。所以更新`count = count + 1`。
5.  将`N`右移 1，重复前两步，直到`N >= pattern && N > 0`。
6.  最后打印`count`。

以下是上述方法的实现:

## C++

```cpp
// C++ program to find the number of times
// pattern p occurred in binary representation
// on n.
#include <bits/stdc++.h>
using namespace std;

// Function to return the count of occurrence
// of pat in binary representation of n
int countPattern(int n, string pat)
{
    // To store decimal value of the pattern
    int pattern_int = 0;

    int power_two = 1;

    // To store a number that has all ones in
    // its binary representation and length
    // of ones equal to length of the pattern
    int all_ones = 0;

    // Find values of pattern_int and all_ones
    for (int i = pat.length() - 1; i >= 0; i--) {
        int current_bit = pat[i] - '0';
        pattern_int += (power_two * current_bit);
        all_ones = all_ones + power_two;
        power_two = power_two * 2;
    }

    int count = 0;
    while (n && n >= pattern_int) {

        // If the pattern occurs in the last
        // digits of n
        if ((n & all_ones) == pattern_int) {
            count++;
        }

        // Right shift n by 1 bit
        n = n >> 1;
    }
    return count;
}

// Driver code
int main()
{
    int n = 500;
    string pat = "10";
    cout << countPattern(n, pat);
}
```

## Java

```java
// Java program to find the number of times
// pattern p occurred in binary representation
// on n.
import java.util.*;

class solution
{

// Function to return the count of occurrence
// of pat in binary representation of n
static int countPattern(int n, String pat)
{
    // To store decimal value of the pattern
    int pattern_int = 0;

    int power_two = 1;

    // To store a number that has all ones in
    // its binary representation and length
    // of ones equal to length of the pattern
    int all_ones = 0;

    // Find values of pattern_int and all_ones
    for (int i = pat.length() - 1; i >= 0; i--) {
        int current_bit = pat.charAt(i) - '0';
        pattern_int += (power_two * current_bit);
        all_ones = all_ones + power_two;
        power_two = power_two * 2;
    }

    int count = 0;
    while (n!=0 && n >= pattern_int) {

        // If the pattern occurs in the last
        // digits of n
        if ((n & all_ones) == pattern_int) {
            count++;
        }

        // Right shift n by 1 bit
        n = n >> 1;
    }
    return count;
}

// Driver code
public static void main(String args[])
{
    int n = 500;
    String pat = "10";
    System.out.println(countPattern(n, pat));
}
}
```

## Python 3

```python
# Python 3 program to find the number of times
# pattern p occurred in binary representation
# on n.

# Function to return the count of occurrence
# of pat in binary representation of n
def countPattern(n, pat):

    # To store decimal value of the pattern
    pattern_int = 0

    power_two = 1

    # To store a number that has all ones in
    # its binary representation and length
    # of ones equal to length of the pattern
    all_ones = 0

    # Find values of pattern_int and all_ones
    i = len(pat) - 1
    while(i >= 0):
        current_bit = ord(pat[i]) - ord('0')
        pattern_int += (power_two * current_bit)
        all_ones = all_ones + power_two
        power_two = power_two * 2
        i -= 1

    count = 0
    while (n != 0 and n >= pattern_int):

        # If the pattern occurs in the last
        # digits of n
        if ((n & all_ones) == pattern_int):
            count += 1

        # Right shift n by 1 bit
        n = n >> 1

    return count

# Driver code
if __name__ == '__main__':
    n = 500
    pat = "10"
    print(countPattern(n, pat))

# This code is contributed by
# Surendra_Gangwar
```

## C#

```csharp
// C# program to find the number of times
// pattern p occurred in binary representation
// on n.
using System ;

class GFG
{

// Function to return the count of occurrence
// of pat in binary representation of n
static int countPattern(int n, string pat)
{
    // To store decimal value of the pattern
    int pattern_int = 0;

    int power_two = 1;

    // To store a number that has all ones in
    // its binary representation and length
    // of ones equal to length of the pattern
    int all_ones = 0;

    // Find values of pattern_int and all_ones
    for (int i = pat.Length - 1; i >= 0; i--)
    {
        int current_bit = pat[i] - '0';
        pattern_int += (power_two * current_bit);
        all_ones = all_ones + power_two;
        power_two = power_two * 2;
    }

    int count = 0;
    while (n != 0 && n >= pattern_int)
    {

        // If the pattern occurs in the last
        // digits of n
        if ((n & all_ones) == pattern_int)
        {
            count++;
        }

        // Right shift n by 1 bit
        n = n >> 1;
    }
    return count;
}

// Driver code
public static void Main()
{
    int n = 500;
    string pat = "10";
    Console.WriteLine(countPattern(n, pat));
}
}

// This code is contributed by Ryuga
```

## PHP

```php
<?php
// PHP program to find the number of times
// pattern pat occurred in binary representation
// of n.

// Function to return the count of occurrence
// of pat in binary representation of n
function countPattern($n, $pat)
{
    // To store decimal value of the pattern
    $pattern_int = 0;

    $power_two = 1;

    // To store a number that has all ones in
    // its binary representation and length
    // of ones equal to length of the pattern
    $all_ones = 0;

    // Find values of $pattern_int and $all_ones
    for ($i = strlen($pat) - 1; $i >= 0; $i--)
    {
        $current_bit = $pat[$i] - '0';
        $pattern_int += ($power_two * $current_bit);
        $all_ones = $all_ones + $power_two;
        $power_two = $power_two * 2;
    }

    $count = 0;
    while ($n && $n >= $pattern_int)
    {

        // If the pattern occurs in the last
        // digits of $n
        if (($n & $all_ones) == $pattern_int)
        {
            $count++;
        }

        // Right shift $n by 1 bit
        $n = $n >> 1;
    }
    return $count;
}

// Driver code
$n = 500;
$pat = "10";
echo countPattern($n, $pat);

// This code is contributed by ihritik
?>
```

## java 描述语言

```html
<script>
// Javascript program to find the number of times
// pattern p occurred in binary representation
// on n.

// Function to return the count of occurrence
// of pat in binary representation of n
function countPattern(n, pat) {
    // To store decimal value of the pattern
    let pattern_int = 0;
    let power_two = 1;
    // To store a number that has all ones in
    // its binary representation and length
    // of ones equal to length of the pattern
    let all_ones = 0;

    // Find values of pattern_int and all_ones
    for (let i = pat.length - 1; i >= 0; i--) {
        let current_bit = pat.charAt(i) - '0';
        pattern_int += (power_two * current_bit);
        all_ones = all_ones + power_two;
        power_two = power_two * 2;
    }

    let count = 0;
    while (n != 0 && n >= pattern_int) {
        // If the pattern occurs in the last
        // digits of n
        if ((n & all_ones) == pattern_int) {
            count++;
        }
        // Right shift n by 1 bit
        n = n >> 1;
    }
    return count;
}

// Driver Code
let n = 500;
let pat = "10";
document.write(countPattern(n, pat));
</script>
```

### Output:

```

```

### 时间复杂度: O(N)
T3】辅助空间: O(1)