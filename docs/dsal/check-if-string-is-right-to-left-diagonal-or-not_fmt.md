# 检查字符串是否从右向左倾斜

> 原文: [https://www.geeksforgeeks.org/check-if-string-is-right-to-left-diagonal-or-not/](https://www.geeksforgeeks.org/check-if-string-is-right-to-left-diagonal-or-not/)

给定完美平方长度的字符串 `str`。任务是检查给定的字符串是否是从右到左的对角线。如果是从右向左的对角线，则打印 `"Yes"` 否则打印 `"No"`。

> 让字符串为 `"abcdefghi"`。可以分解为:
> ```
> abc
> def
> ghi
> ```
> 如果字符 `c`、`e` 和 `g` 相等，则给定的字符串是从右到左的对角线，否则不是。
>
> 意思是，首先把字符串分成一个方块，检查从右到左对角线的所有字符是否相同。如果相同，则打印 `"Yes"`，否则打印 `"No"`。

**例:**

> **输入:** `str = "abcxabxcaxbcxabc"`
> **输出:** Yes
> **说明:** 断开方框中的字符串，见下图
> ```
> abcx
> abxc
> axbc
> xabc
> ```
> 所以，左右对角线有相同的字符。
>
> **输入:** `str = "abcdxabcxdbxcdaxbcdd"`
> **输出:** No
> **说明:** 将方块中的字符串断开，见下图
> ```
> abcdx
> abcdxd
> abxcd
> axbcd
> axbcd
> ```
> 所以，从右到左的对角线还没有相同的字符。

**方法:** 按照下面给出的步骤解决问题

*   计算字符串的 `长度`。
*   检查 `长度` 是否为任意数字的完美平方。
*   如果不是正方，则打印 `"No"`。
*   否则继续下面的步骤
    *   让长度是 `k` 的完美平方。
    *   检查索引 `k-1`、`2k-1`、`3k-1`…等等。
    *   如果所有索引的字符都相同
        *   打印 `"Yes"`。
    *   其他
        *   打印 `"No"`。

下面是上述方法的实现:

## C++

```cpp
// C++ program to Check if the
// given string is right to
// left diagonal or not
#include <bits/stdc++.h>
using namespace std;

// Function to check if the given
// string is right to left diagonal or not
int is_rtol(string s)
{
    int tmp = sqrt(s.length()) - 1;

    char first = s[tmp];

    // Iterate over string
    for (int pos = tmp;
         pos < s.length() - 1; pos += tmp) {

        // If character is not same as
        // the first character then
        // return false
        if (s[pos] != first) {
            return false;
        }
    }

    return true;
}

// Driver Code
int main()
{
    // Given String str
    string str = "abcxabxcaxbcxabc";

    // Function Call
    if (is_rtol(str)) {
        cout << "Yes" << endl;
    }
    else {
        cout << "No" << endl;
    }

    return 0;
}
```

## Java

```java
// Java program to check if the
// given string is right to
// left diagonal or not
import java.io.*;

class GFG{

// Function to check if the given
// string is right to left diagonal or not
public static boolean is_rtol(String s)
{
    int tmp = (int)(Math.sqrt(s.length())) - 1;
    char first = s.charAt(tmp);

    // Iterate over string
    for(int pos = tmp; pos < s.length() - 1;
            pos += tmp)
    {

        // If character is not same as
        // the first character then
        // return false
        if (s.charAt(pos) != first)
        {
            return false;
        }
    }
    return true;
}

// Driver Code
public static void main(String args[])
{

    // Given String str
    String str = "abcxabxcaxbcxabc";

    // Function call
    if (is_rtol(str))
    {
        System.out.print("Yes");
    }
    else
    {
        System.out.print("No");
    }
}
}

// This code is contributed by grand_master
```

## Python 3

```python
# Python3 program to Check if the
# given is right to
# left diagonal or not
from math import sqrt, floor, ceil

# Function to check if the given
# is right to left diagonal or not
def is_rtol(s):

    tmp = floor(sqrt(len(s))) - 1

    first = s[tmp]

    # Iterate over string
    for pos in range(tmp, len(s) - 1, tmp):

        # If character is not same as
        # the first character then
        # return false
        if (s[pos] != first):
            return False

    return True

# Driver Code
if __name__ == '__main__':

    # Given String str
    str = "abcxabxcaxbcxabc"

    # Function Call
    if (is_rtol(str)):
        print("Yes")
    else:
        print("No")

# This code is contributed by Mohit Kumar
```

## C#

```csharp
// C# program to check if the
// given string is right to
// left diagonal or not
using System;

class GFG{

// Function to check if the given
// string is right to left diagonal or not
public static bool is_rtol(String s)
{
    int tmp = (int)(Math.Sqrt(s.Length)) - 1;
    char first = s[tmp];

    // Iterate over string
    for(int pos = tmp; pos < s.Length - 1;
            pos += tmp)
    {

        // If character is not same as
        // the first character then
        // return false
        if (s[pos] != first)
        {
            return false;
        }
    }
    return true;
}

// Driver Code
public static void Main(String []args)
{

    // Given String str
    String str = "abcxabxcaxbcxabc";

    // Function call
    if (is_rtol(str))
    {
        Console.Write("Yes");
    }
    else
    {
        Console.Write("No");
    }
}
}

// This code is contributed by amal kumar choubey
```

## JavaScript

```javascript
<script>
    // Javascript program to check if the
    // given string is right to
    // left diagonal or not

    // Function to check if the given
    // string is right to left diagonal or not
    function is_rtol(s)
    {
        let tmp = (Math.sqrt(s.length)) - 1;
        let first = s[tmp];

        // Iterate over string
        for(let pos = tmp; pos < s.length - 1; pos += tmp)
        {

            // If character is not same as
            // the first character then
            // return false
            if (s[pos] != first)
            {
                return false;
            }
        }
        return true;
    }

    // Given String str
    let str = "abcxabxcaxbcxabc";

    // Function call
    if (is_rtol(str))
    {
        document.write("Yes");
    }
    else
    {
        document.write("No");
    }

// This code is contributed by divyeshrabadiya07.
</script>
```

**Output:**

```
Yes
```

`时间复杂度`: O(N)

`辅助空间`: O(1)