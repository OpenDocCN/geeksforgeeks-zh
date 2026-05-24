# 找到用数字 X 和 Y 组成的第 n 个偶数长度回文号

> 原文：[https://www.geeksforgeeks.org/find-nth-even-length-palindromic-number-formed-using-digits-x-and-y/](https://www.geeksforgeeks.org/find-nth-even-length-palindromic-number-formed-using-digits-x-and-y/)

给定一个整数 `N`，任务是找到偶数长度的第 `N` 个偶数回文号，并且只包含数字 `X` 和 `Y`，其中 `X, Y > 0`。

## 示例

**输入：** `N = 9`，`X = 4`，`Y = 5`
**输出：** `454454`
**解释：**
使用 4 和 5 的偶数长度回文数字为：
`44`、`55`、`4444`、`4554`、`5445`、`5555`、`444444`、`445544`、`454454`、…
上述系列的第 9 项 = `454454`

**输入：** `N = 6`，`X = 1`，`Y = 2`
**输出：** `2222`
**解释：**
使用 1 和 2 的偶数长度回文数字是：
`11`、`22`、`1111`、`1221`、`2112`、`2222`、`111111`、`112211`、`121121`、……
上述系列的第 6 项 = `2222`

## 方法

使用 `X` 和 `Y` 的偶数长度回文数字为：
```
XX, YY, XXXX, XYYX, YXXY, YYYY, XXXXXX, XXYYXX, ...
```

上述顺序可以观察为：
```
XX,       -> 长度 (L) = 2
YY,       -> 长度 (L) = 2

XXXX,     -> 长度 (L) = 4
XYYX,     -> 长度 (L) = 4
YXXY,     -> 长度 (L) = 4
YYYY,     -> 长度 (L) = 4

XXXXXX,   -> 长度 (L) = 6
XXYYXX,   -> 长度 (L) = 6
XYXXYX,   -> 长度 (L) = 6
XYYYYX,   -> 长度 (L) = 6
YXXXXY,   -> 长度 (L) = 6
YXYYXY,   -> 长度 (L) = 6
YYXXYY,   -> 长度 (L) = 6
YYYYYY,   -> 长度 (L) = 6

XXXXXXXX, -> 长度 (L) = 8
...
```

如果我们把任何一个术语分成两半，后半部分正好是前半部分的反向。
**例：**
```
取术语 XXYYXX

将其分成两半
XXYYXX = XXY | YXX

所以 YXX 就是 XXY 的反向
```

只取术语的左半部分，令 `X = 0`，`Y = 1` 得到二进制字符串，长度 `L` 的数字可以看到形成一个从 0 到 `(2^(L/2) – 1)` 的整数序列，取为**秩 (R)**。因此 `0 ≤ R ≤ 2^(L/2) – 1`。
因此顺序可观察如下：
```
L -> 左半部分 -> 二进制字符串 -> 秩 (十进制)

2 -> X    -> 0             -> 0
2 -> Y    -> 1             -> 1

4 -> XX   -> 00            -> 0
4 -> XY   -> 01            -> 1
4 -> YX   -> 10            -> 2
4 -> YY   -> 11            -> 3

6 -> XXX  -> 000           -> 0
6 -> XXY  -> 001           -> 1
6 -> XYX  -> 010           -> 2
6 -> XYY  -> 011           -> 3
6 -> YXX  -> 100           -> 4
6 -> YXY  -> 101           -> 5
6 -> YYX  -> 110           -> 6
6 -> YYY  -> 111           -> 7

8 -> XXXX -> 0000          -> 0
...
```

因此，对于所需的第 `N` 项：
*   所需第 `N` 个术语的**长度 (L)**：
    `L = 2 * (ceil(log2(N + 2)) - 1)`
*   **所需第 `N` 个术语的秩 (R)**：
    `R = N - 2^(L/2) + 1`
*   **所需第 `N` 项的前半部分** = `R` 在 `L/2` 位的二进制表示，将 0 替换为 `X`，将 1 替换为 `Y`
*   **所需第 `N` 项的后半部分** = 前半部分的反向

以下是上述方法的实现：

## C++

```cpp
// C++ program to find nth even
// palindromic number of only even
// length composing of 4's and 5's.
#include <bits/stdc++.h>
using namespace std;

// Utility function to compute
// n'th palindrome number
string solve(int n, char x, char y)
{
    // Calculate the length from above
    // formula as discussed above
    int length = ceil(log2(n + 2)) - 1;

    // Calculate rank for length L
    int rank = n - (1 << length) + 1;

    string left = "", right = "";

    for (int i = length - 1; i >= 0; i--) {

        // Mask to check if i't bit
        // is set or not
        int mask = 1 << i;

        // If bit is set append '5' else append '4'
        bool bit = mask & rank;

        if (bit) {
            left += y;
            right += y;
        }
        else {
            left += x;
            right += x;
        }
    }

    reverse(right.begin(), right.end());

    return left + right;
}

// Driver Code
int main()
{
    int n = 23;
    char x = '4', y = '5';
    string ans = solve(n, x, y);
    cout << ans << '\n';

    return 0;
}
```

## Java

```java
// Java program to find nth even
// palindromic number of only even
// length composing of 4's and 5's.
import java.util.*;

class GFG
{

    // Utility function to compute
    // n'th palindrome number
    static String solve(int n, char x, char y)
    {
        // Calculate the length from above
        // formula as discussed above
        int length = (int)Math.ceil(Math.log(n + 2) /
                                    Math.log(2)) - 1;

        // Calculate rank for length L
        int rank = n - (1 << length) + 1;

        String left = "", right = "";

        for (int i = length -1 ; i >= 0; i--)
        {

            // Mask to check if i't bit
            // is set or not
            int mask = (1 << i);

            // If bit is set append '5' else append '4'
            int bit = mask & rank;

            if (bit > 0)
            {
                left += y;
                right += y;
            }
            else
            {
                left += x;
                right += x;
            }
        }

        StringBuilder sb = new StringBuilder(right);
        sb.reverse();

        right = sb.toString();

        String res = left + right;
        return res;
    }

    // Driver Code
    public static void main (String[] args)
    {
        int n = 23;
        char x = '4', y = '5';
        String ans = solve(n, x, y);
        System.out.println(ans);
    }
}

// This code is contributed by AnkitRai01
```

## Python 3

```python
# Python3 program to find nth even
# palindromic number of only even
# length composing of 4's and 5's.
from math import ceil, log2

# Utility function to compute
# n'th palindrome number
def solve(n, x, y) :

    # Calculate the length from above
    # formula as discussed above
    length = ceil(log2(n + 2)) - 1;

    # Calculate rank for length L
    rank = n - (1 << length) + 1;

    left = ""; right = "";

    for i in range(length - 1 , -1, -1):

        # Mask to check if i't bit
        # is set or not
        mask = (1 << i);

        # If bit is set append '5'
        # else append '4'
        bit = (mask & rank);

        if (bit) :
            left += y;
            right += y;

        else :
            left += x;
            right += x;

    right = right[::-1];

    res = left + right;
    return res;

# Driver Code
if __name__ == "__main__" :

    n = 23;
    x = '4';
    y = '5';
    ans = solve(n, x, y);
    print(ans);

# This code is contributed by kanugargng
```

## C#

```csharp
// C# program to find nth even
// palindromic number of only even
// length composing of 4's and 5's.
using System;

class GFG
{

    // Utility function to compute
    // n'th palindrome number
    static String solve(int n, char x, char y)
    {
        // Calculate the length from above
        // formula as discussed above
        int length = (int)Math.Ceiling(Math.Log(n + 2) /
                                       Math.Log(2)) - 1;

        // Calculate rank for length L
        int rank = n - (1 << length) + 1;

        String left = "", right = "";

        for (int i = length -1; i >= 0; i--)
        {

            // Mask to check if i't bit
            // is set or not
            int mask = (1 << i);

            // If bit is set append '5'
            // else append '4'
            int bit = mask & rank;

            if (bit > 0)
            {
                left += y;
                right += y;
            }
            else
            {
                left += x;
                right += x;
            }
        }

        right = reverse(right);
        String res = left + right;
        return res;
    }

    static String reverse(String input)
    {
        char[] a = input.ToCharArray();
        int l, r = 0;
        r = a.Length - 1;

        for (l = 0; l < r; l++, r--)
        {
            // Swap values of l and r
            char temp = a[l];
            a[l] = a[r];
            a[r] = temp;
        }
        return String.Join("", a);
    }

    // Driver Code
    public static void Main(String[] args)
    {
        int n = 23;
        char x = '4', y = '5';
        String ans = solve(n, x, y);
        Console.WriteLine(ans);
    }
}

// This code is contributed by 29AjayKumar
```

# C# 实现

```csharp
// Driver Code
public static void Main (String[] args)
{
    int n = 23;
    char x = '4', y = '5';
    String ans = solve(n, x, y);
    Console.WriteLine(ans);
}

// This code is contributed by Rajput-Ji
```

# JavaScript 实现

```javascript
// Javascript program to find nth even
// palindromic number of only even
// length composing of 4's and 5's.

// Utility function to compute
// n'th palindrome number
function solve(n, x, y)
{
    // Calculate the length from above
    // formula as discussed above
    var length = Math.ceil(Math.log2(n + 2)) - 1;

    // Calculate rank for length L
    var rank = n - (1 << length) + 1;

    var left = "", right = "";

    for (var i = length - 1; i >= 0; i--) {

        // Mask to check if i't bit
        // is set or not
        var mask = 1 << i;

        // If bit is set append '5' else append '4'
        var bit = mask & rank;

        if (bit) {
            left += y;
            right += y;
        }
        else {
            left += x;
            right += x;
        }
    }

    right = right.split('').reverse().join('');

    return left + right;
}

// Driver Code
var n = 23;
var x = '4', y = '5';
var ans = solve(n, x, y);
document.write( ans + "<br>");
```

**输出**

**时间复杂度:** `O(n)`，其中 `n` 是字符串的长度。