# 检查给定形式的非常大数是否为 3 的倍数。

> 原文: [https://www.geeksforgeeks.org/check-whether-large-number-given-form-multiple-3/](https://www.geeksforgeeks.org/check-whether-large-number-given-form-multiple-3/)

考虑一个很长的 `K` 位数 `N`，数字 `d0`，`d1`，…，`dK-1`（以十进制表示；`d0` 为最高有效位，`dK-1` 为最低有效位）。这个数字太大了，不能明确给出或写下来；取而代之的是，只给出它的起始数字和构造剩余数字的方法。
具体给你 `d0` 和 `d1`；对于每个 `i ≥ 2`，`di` 是所有前面（更有效）数字的和，模 10，更正式地——
确定 `N` 是否为 3 的倍数。

> **约束:**
> `2 ≤ K ≤ 10^12`
> `1 ≤ d0 ≤ 9`
> `0 ≤ d1 ≤ 9`

**示例:**

```
Input : K = 13, d0 = 8, d1 = 1
Output : YES
```

**说明:** 整数 `N` 是 `8198624862486`，可被 3 整除，所以答案是肯定的。

```
Input :  K = 5, d0 = 3, d1 = 4
Output : NO
```

**说明:** 整数 `N` 是 `34748`，不能被 3 整除，所以答案是否定的。

## 方法 1（蛮力）

我们可以应用蛮力方法，利用迭代构造数时给出的条件（前面数的和以 10 为模）计算整数 `N`，并检查该数是否能被 3 整除。但是由于位数 (`K`) 可以大到 `10^12`，我们不能将其存储为整数，因为它将非常大于 `long long int` 的最大范围。因此，下面是确定 `N` 是否是 3 的倍数的有效方法。

## 方法 2（高效）

解决方案背后的关键思想是，在长度为 4 的周期中，数字在一段时间后开始重复。首先，我们将找到所有数字的和，然后确定它是否能被 3 整除。

> 我们知道 `d0` 和 `d1`。
> `d2 = (d0 + d1) % 10`
> `d3 = (d2 + d1 + d0) % 10 = (2 * (d0 + d1)) % 10`
> 类似地，
> `d4 = (d3 + d2 + d1 + d0) % 10 = (4 * (d0 + d1)) % 10`
> `d5 = (d4 + d3 + d2 + d1 + d0) % 10 = (8 * (d0 + d1)) % 10`
> `d6 = (d5 + d4 + d3 + d2 + d1 + d0) % 10 = (16 * (d0 + d1)) % 10 = (6 * (d0 + d1)) % 10`
> `d7 = (d6 + d5 + d4 + d3 + d2 + d1 + d0) % 10 = (32 * (d0 + d1)) % 10 = (2 * (d0 + d1)) % 10`

如果我们继续在 `di` 上寻找，我们会看到结果只是围绕相同的值（2，4，8，6）循环。
此处循环长度为 4，`d2` 不在循环中。因此，在 `d2` 之后，周期开始形成，长度为 4，从（2，4，8，6）中的任何值开始，但是以相同的顺序给出连续四个数字的总和 `S = 2 + 4 + 8 + 6 = 20`。因此，整数的位数总和为 `= d0 + d1 + d2 + S * (k – 3) / 4 + x`，其中前三个术语将由 `d0`、`d1`、`d2` 涵盖，之后的 4 组将由 `S` 涵盖。但由于 `(k – 3)` 可能不是 4 的倍数，剩下的一些数字将被 `x` 覆盖，`x` 可以通过运行一个循环来计算，因为这些项的数量将小于 4。

例如**当 `K = 13` 时，**
**位数之和 `= d0 + d1 + d2 + S * (13 – 3) / 4 + x = d0 + d1 + d2 + S * 2 + x`，**
其中第一个 `S` 将有 `d3`，`d4`，`d5`，`d6`，第二个 `S` 将有 `d7`，`d8`，`d9`，`d10`，和
`x = d11 + d12`

*   `d11 = 2 * (d0 + d1) % 10`
*   `d12 = 4 * (d0 + d1) % 10`

以下是上述想法的实现:

### C++

```cpp
// CPP Program to determine if
// number N of given form is
// divisible by 3 or not
#include <bits/stdc++.h>
using namespace std;

// function returns true if number N is
// divisible by 3 otherwise false,
// dig0 - most significant digit
// dig1 - 2nd most significant digit
// K - number of digits
bool multipleOfThree(int K, int dig0, int dig1)
{
    // sum of digits
    long long int sum = 0;

    // store the sum of first two digits
    // modulo 10 in a temporary variable
    int temp = (dig0 + dig1) % 10;

    sum = dig0 + dig1;

    // if the number N is a two digit number
    if (K == 2) {
        if (sum % 3 == 0)
            return true;
        else
            return false;
    }

    // add temp to sum to get the sum
    // of first three digits which are
    // not a part of cycle
    sum += temp;

    // get the number of groups in cycle
    long long int numberofGroups = (K - 3) / 4;

    // get the remaining number of digits
    int remNumberofDigits = (K - 3) % 4;

    // if temp = 5 or temp = 0 then sum of each group will
    // be 0
    if (temp == 5 || temp == 0)
        sum += (numberofGroups * 0);

    else
        // add sum of 20 for each group (2, 4, 8, 6)
        sum += (numberofGroups * 20);

    // find the remaining sum of remaining digits
    for (int i = 0; i < remNumberofDigits; i++) {
        temp = (2 * temp) % 10;
        sum += temp;
    }

    // check if it is divisible by 3 or not
    if (sum % 3 == 0)
        return true;
    else
        return false;
}

// Driver Code
int main()
{
    int K = 5, dig0 = 3, dig1 = 4;
    if (multipleOfThree(K, dig0, dig1))
        cout << "YES" << endl;
    else
        cout << "NO" << endl;

    K = 10;
    dig0 = 3;
    dig1 = 2;
    if (multipleOfThree(K, dig0, dig1))
        cout << "YES" << endl;
    else
        cout << "NO" << endl;
    return 0;
}
```

### Java

```java
// Java Program to determine if
// number N of given form is
// divisible by 3 or not
import java.io.*;

public class GFG {

    // function returns true if number N is
    // divisible by 3 otherwise false,
    // dig0 - most significant digit
    // dig1 - 2nd most significant digit
    // K - number of digits
    static boolean multipleOfThree(int K, int dig0,
                                   int dig1)
    {

        // sum of digits
        long sum = 0;

        // store the sum of first two digits
        // modulo 10 in a temporary variable
        int temp = (dig0 + dig1) % 10;

        sum = dig0 + dig1;

        // if the number N is a two digit number
        if (K == 2) {
            if (sum % 3 == 0)
                return true;
            else
                return false;
        }

        // add temp to sum to get the sum
        // of first three digits which are
        // not a part of cycle
        sum += temp;

        // get the number of groups in cycle
        long numberofGroups = (K - 3) / 4;

        // get the remaining number of digits
        int remNumberofDigits = (K - 3) % 4;

        // add sum of 20 for each group (2, 4, 8, 6)
        sum += (numberofGroups * 20);

        // find the remaining sum of
        // remaining digits
        for (int i = 0; i < remNumberofDigits; i++) {
            temp = (2 * temp) % 10;
            sum += temp;
        }

        // check if it is divisible by 3 or not
        if (sum % 3 == 0)
            return true;
        else
            return false;
    }

    // Driver Code
    static public void main(String[] args)
    {
        int K = 5, dig0 = 3, dig1 = 4;
        if (multipleOfThree(K, dig0, dig1))
            System.out.println("Yes");
        else
            System.out.println("No");
    }
}

// This code is contributed by vt_m.
```

### Python 3

```python
# Python 3 Program to determine if
# number N of given form is
# divisible by 3 or not

# function returns true if number N
# is divisible by 3 otherwise false,
# dig0 - most significant digit
# dig1 - 2nd most significant digit
# K - number of digits

def multipleOfThree(K, dig0, dig1):

    # sum of digits
    sum = 0

    # store the sum of first two digits
    # modulo 10 in a temporary variable
    temp = (dig0 + dig1) % 10

    sum = dig0 + dig1

    # if the number N is a
    # two digit number
    if (K == 2):
        if (sum % 3 == 0):
            return True
        else:
            return False

    # add temp to sum to get the sum
    # of first three digits which are
    # not a part of cycle
    sum += temp

    # get the number of groups in cycle
    numberofGroups = (K - 3) // 4

    # get the remaining number of digits
    remNumberofDigits = (K - 3) % 4

    # add sum of 20 for each
    # group (2, 4, 8, 6)
    sum += (numberofGroups * 20)

    # find the remaining sum of
    # remaining digits
    for i in range(remNumberofDigits):
        temp = (2 * temp) % 10
        sum += temp

    # check if it is divisible
    # by 3 or not
    if (sum % 3 == 0):
        return True
    else:
        return False

# Driver Code
if __name__ == "__main__":
    K = 5
    dig0 = 3
    dig1 = 4
    if (multipleOfThree(K, dig0, dig1)):
        print("Yes")
    else:
        print("No")

# This code is contributed by ChitraNayal
```

## C#

```
// C# Program to determine if
// number N of given form is
// divisible by 3 or not
using System;

class GFG {

    // function returns true if number N is
    // divisible by 3 otherwise false,
    // dig0 - most significant digit
    // dig1 - 2nd most significant digit
    // K - number of digits
    static bool multipleOfThree(int K, int dig0, int dig1)
    {
        // sum of digits
        long sum = 0;

        // store the sum of first two digits
        // modulo 10 in a temporary variable
        int temp = (dig0 + dig1) % 10;

        sum = dig0 + dig1;

        // if the number N is
        // a two digit number
        if (K == 2) {
            if (sum % 3 == 0)
                return true;
            else
                return false;
        }

        // add temp to sum to get the sum
        // of first three digits which are
        // not a part of cycle
        sum += temp;

        // get the number of groups in cycle
        long numberofGroups = (K - 3) / 4;

        // get the remaining number of digits
        int remNumberofDigits = (K - 3) % 4;

        // add sum of 20 for each group (2, 4, 8, 6)
        sum += (numberofGroups * 20);

        // find the remaining sum of
        // remaining digits
        for (int i = 0; i < remNumberofDigits; i++) {
            temp = (2 * temp) % 10;
            sum += temp;
        }

        // check if it is divisible by 3 or not
        if (sum % 3 == 0)
            return true;
        else
            return false;
    }

    // Driver Code
    static public void Main(String[] args)
    {
        int K = 5, dig0 = 3, dig1 = 4;
        if (multipleOfThree(K, dig0, dig1))
            Console.WriteLine("Yes");
        else
            Console.WriteLine("No");
    }
}

// This code is contributed by vt_m.
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php
// PHP Program to determine if number N
// of given form is divisible by 3 or not

// function returns true if number N
// is divisible by 3 otherwise false,
// dig0 - most significant digit
// dig1 - 2nd most significant digit
// K - number of digits
function multipleOfThree($K, $dig0, $dig1)
{
    // sum of digits
    $sum = 0;

    // store the sum of first two digits
    // modulo 10 in a temporary variable
    $temp = ($dig0 + $dig1) % 10;

    $sum = $dig0 + $dig1;

    // if the number N is a
    // two digit number
    if ($K == 2)
        if ($sum % 3 == 0)
            return true;
        else
            return false;

    // add temp to sum to get the sum
    // of first three digits which are
    // not a part of cycle
    $sum += $temp;

    // get the number of groups in cycle
    $numberofGroups = (int)(($K - 3) / 4);

    // get the remaining number of digits
    $remNumberofDigits = ($K - 3) % 4;

    // add sum of 20 for each
    // group (2, 4, 8, 6)
    $sum += ($numberofGroups * 20);

    // find the remaining sum of
    // remaining digits
    for ($i = 0; $i < $remNumberofDigits; $i++)
    {
        $temp = (2 * $temp) % 10;
        $sum += $temp;
    }

    // check if it is divisible
    // by 3 or not
    if ($sum % 3 == 0)
        return true;
    else
        return false;
}

// Driver Code
$K = 5;
$dig0 = 3;
$dig1 = 4;
if (multipleOfThree($K, $dig0, $dig1))
    print("Yes");
else
    print("No");

// This code is contributed by mits
?>
```

## java 描述语言

```
<script>

// JavaScript Program to determine if
// number N of given form is
// divisible by 3 or not

// function returns true if number N is
// divisible by 3 otherwise false,
// dig0 - most significant digit
// dig1 - 2nd most significant digit
// K - number of digits
function multipleOfThree(K, dig0, dig1)
{
    // sum of digits
    let sum = 0;

    // store the sum of first two digits
    // modulo 10 in a temporary variable
    let temp = (dig0 + dig1) % 10;

    sum = dig0 + dig1;

    // if the number N is a two digit number
    if (K == 2) {
        if (sum % 3 == 0)
            return true;
        else
            return false;
    }

    // add temp to sum to get the sum
    // of first three digits which are
    // not a part of cycle
    sum += temp;

    // get the number of groups in cycle
    let numberofGroups = parseInt((K - 3) / 4);

    // get the remaining number of digits
    let remNumberofDigits = (K - 3) % 4;

    // if temp = 5 or temp = 0 then sum of each group will
    // be 0
    if (temp == 5 || temp == 0)
        sum += (numberofGroups * 0);

    else
        // add sum of 20 for each group (2, 4, 8, 6)
        sum += (numberofGroups * 20);

    // find the remaining sum of remaining digits
    for (let i = 0; i < remNumberofDigits; i++) {
        temp = (2 * temp) % 10;
        sum += temp;
    }

    // check if it is divisible by 3 or not
    if (sum % 3 == 0)
        return true;
    else
        return false;
}

// Driver Code
    let K = 5, dig0 = 3, dig1 = 4;
    if (multipleOfThree(K, dig0, dig1))
        document.write("YES<br>");
    else
        document.write("NO<br>");

    K = 10;
    dig0 = 3;
    dig1 = 2;
    if (multipleOfThree(K, dig0, dig1))
        document.write("YES<br>");
    else
        document.write("NO<br>");

</script>
```

**Output**

```
NO
NO
```

**时间复杂度:** `O(1)`
**辅助空间:** `O(1)`