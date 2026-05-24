# 检查字符串中的字母是否构成回文（O(1)额外空间）

> 原文：[https://www.geeksforgeeks.org/check-if-the-characters-in-a-string-form-a-palindrome-in-o1-extra-space/](https://www.geeksforgeeks.org/check-if-the-characters-in-a-string-form-a-palindrome-in-o1-extra-space/)

给定一个字符串`str`。字符串可能包含**小写字母、特殊字符、数字**，甚至**空格**。任务是检查字符串中是否只有字母形成回文组合，而不使用任何额外的空间。
**注意**：不允许使用多余的空间来解决这个问题。此外，字符串中的字母都是小写的，字符串可能包含特殊字符、数字，甚至空格和小写字母。

**示例**：

> **输入**：`str = "m a 343 la y a l am"`
> **输出**：YES
> 字符串中的字符组成序列“马拉雅拉姆语”，是回文。
>
> **输入**：`str = "malayalam"`
> **输出**：YES

## 方法

*   创建两个实用函数来获取字符串中字符的第一个和最后一个位置。
*   开始遍历字符串，每次都要找到第一个和最后一个字符的位置。
*   如果每次迭代的第一个和最后一个字符都相同，并且字符串完全遍历，则打印“YES”，否则打印“NO”。

下面是上述方法的实现：

## C++

```cpp
// CPP program to check if the characters in
// the given string forms a Palindrome in
// O(1) extra space
#include <iostream>
using namespace std;

// Utility function to get the position of
// first character in the string
int firstPos(string str, int start, int end)
{
    int firstChar = -1;

    // Get the position of first character
    // in the string
    for (int i = start; i <= end; i++) {
        if (str[i] >= 'a' && str[i] <= 'z') {
            firstChar = i;
            break;
        }
    }

    return firstChar;
}

// Utility function to get the position of
// last character in the string
int lastPos(string str, int start, int end)
{
    int lastChar = -1;

    // Get the position of last character
    // in the string
    for (int i = start; i >= end; i--) {
        if (str[i] >= 'a' && str[i] <= 'z') {
            lastChar = i;
            break;
        }
    }

    return lastChar;
}

// Function to check if the characters in
// the given string forms a Palindrome in
// O(1) extra space
bool isPalindrome(string str)
{
    int firstChar = 0, lastChar = str.length() - 1;
    bool ch = true;

    for (int i = 0; i < str.length(); i++) {
        firstChar = firstPos(str, firstChar, lastChar);
        lastChar = lastPos(str, lastChar, firstChar);

        // break, when all letters are checked
        if (lastChar < 0 || firstChar < 0)
            break;
        if (str[firstChar] == str[lastChar]) {
            firstChar++;
            lastChar--;
            continue;
        }

        // if mismatch found, break the loop
        ch = false;
        break;
    }

    return (ch);
}

// Driver code
int main()
{
    string str = "m     a  343 la y a l am";
    if (isPalindrome(str))
        cout << "YES";
    else
        cout << "NO";

    return 0;
}
```

## Java

```java
// Java program to check if
// the characters in the given
// string forms a Palindrome
// in O(1) extra space
import java.io.*;

class GFG
{

// Utility function to get
// the position of first
// character in the string
static int firstPos(String str,
                    int start,
                    int end)
{
    int firstChar = -1;

    // Get the position of
    // first character in
    // the string
    for(int i = start; i <= end; i++)
    {
        if(str.charAt(i) >= 'a'&&
        str.charAt(i) <= 'z')
        {
            firstChar = i;
            break;
        }
    }

    return firstChar;
}

// Utility function to get
// the position of last
// character in the string
static int lastPos(String str,
                int start,
                int end)
{
    int lastChar = -1;

    // Get the position of last
    // character in the string
    for(int i = start; i >= end; i--)
    {
        if(str.charAt(i) >= 'a'&&
        str.charAt(i) <= 'z')
        {
            lastChar = i;
            break;
        }
    }

    return lastChar;
}

// Function to check if the
// characters in the given
// string forms a Palindrome
// in O(1) extra space
static boolean isPalindrome(String str)
{
    int firstChar = 0,
        lastChar = str.length() - 1;
    boolean ch = true;

    for (int i = 0; i < str.length(); i++)
    {
        firstChar = firstPos(str, firstChar,
                                lastChar);
        lastChar = lastPos(str, lastChar,
                                firstChar);

        // break, when all
        // letters are checked
        if (lastChar < 0 || firstChar < 0)
            break;
        if (str.charAt(firstChar) ==
            str.charAt(lastChar))
        {
            firstChar++;
            lastChar--;
            continue;
        }

        // if mismatch found,
        // break the loop
        ch = false;
        break;
    }

        return ch;

}

// Driver code
public static void main (String[] args)
{
    String str = "m a 343 la y a l am";

    if(isPalindrome(str))
        System.out.print("YES");
    else
        System.out.println("NO");
}
}

// This code is contributed
// by inder_verma.
```

## Python 3

```python
# Python 3 program to check if the characters
# in the given string forms a Palindrome in
# O(1) extra space

# Utility function to get the position of
# first character in the string
def firstPos(str, start, end):

    firstChar = -1

    # Get the position of first character
    # in the string
    for i in range(start, end + 1):
        if (str[i] >= 'a' and str[i] <= 'z') :
            firstChar = i
            break

    return firstChar

# Utility function to get the position of
# last character in the string
def lastPos(str, start, end):

    lastChar = -1

    # Get the position of last character
    # in the string
    for i in range(start, end - 1, -1) :
        if (str[i] >= 'a' and str[i] <= 'z') :
            lastChar = i
            break

    return lastChar

# Function to check if the characters in
# the given string forms a Palindrome in
# O(1) extra space
def isPalindrome(str):

    firstChar = 0
    lastChar = len(str) - 1
    ch = True

    for i in range(len(str)) :
        firstChar = firstPos(str, firstChar, lastChar);
        lastChar = lastPos(str, lastChar, firstChar);

        # break, when all letters are checked
        if (lastChar < 0 or firstChar < 0):
            break
        if (str[firstChar] == str[lastChar]):
            firstChar += 1
            lastChar -= 1
            continue

        # if mismatch found, break the loop
        ch = False
        break

    return (ch)

# Driver code
if __name__ == "__main__":

    str = "m     a 343 la y a l am"
    if (isPalindrome(str)):
        print("YES")
    else:
        print("NO")

# This code is contributed by ita_c
```

# 检查回文字符串的实现

## C\#

以下C#程序以O(1)的额外空间检查给定字符串中的字符是否构成回文。

```csharp
// C# program to check if
// the characters in the given
// string forms a Palindrome
// in O(1) extra space
using System;

class GFG
{

// Utility function to get
// the position of first
// character in the string
static int firstPos(string str,
                    int start,
                    int end)
{
    int firstChar = -1;

    // Get the position of
    // first character in
    // the string
    for(int i = start; i <= end; i++)
    {
        if(str[i] >= 'a'&&
           str[i] <= 'z')
        {
            firstChar = i;
            break;
        }
    }

    return firstChar;
}

// Utility function to get
// the position of last
// character in the string
static int lastPos(string str,
                   int start,
                   int end)
{
    int lastChar = -1;

    // Get the position of last
    // character in the string
    for(int i = start; i >= end; i--)
    {
        if(str[i] >= 'a'&&
           str[i] <= 'z')
        {
            lastChar = i;
            break;
        }
    }

    return lastChar;
}

// Function to check if the
// characters in the given
// string forms a Palindrome
// in O(1) extra space
static bool isPalindrome(string str)
{
    int firstChar = 0,
        lastChar = str.Length - 1;
    bool ch = true;

    for (int i = 0; i < str.Length; i++)
    {
        firstChar = firstPos(str, firstChar,
                                  lastChar);
        lastChar = lastPos(str, lastChar,
                                firstChar);

        // break, when all
        // letters are checked
        if (lastChar < 0 || firstChar < 0)
            break;
        if (str[firstChar] ==
            str[lastChar])
        {
            firstChar++;
            lastChar--;
            continue;
        }

        // if mismatch found,
        // break the loop
        ch = false;
        break;
    }

        return ch;
}

// Driver code
public static void Main ()
{
    string str = "m a 343 la y a l am";

    if(isPalindrome(str))
        Console.WriteLine("YES");
    else
        Console.WriteLine("NO");
}
}

// This code is contributed
// by inder_verma.
```

## PHP

以下PHP程序以O(1)的额外空间检查给定字符串中的字符是否构成回文。

```php
<?php
// PHP program to check if the
// characters in the given
// string forms a Palindrome
// in O(1) extra space

// Utility function to get the
// position of first character
// in the string
function firstPos($str, $start, $end)
{
    $firstChar = -1;

    // Get the position of first
    // character in the string
    for ($i = $start; $i <= $end; $i++)
    {
        if ($str[$i] >= 'a' and
            $str[$i] <= 'z')
        {
            $firstChar = $i;
            break;
        }
    }

    return $firstChar;
}

// Utility function to get the
// position of last character
// in the string
function lastPos($str, $start, $end)
{
    $lastChar = -1;

    // Get the position of last
    // character in the string
    for ( $i = $start; $i >= $end; $i--)
    {
        if ($str[$i] >= 'a' and
            $str[$i] <= 'z')
        {
            $lastChar = $i;
            break;
        }
    }

    return $lastChar;
}

// Function to check if the
// characters in the given
// string forms a Palindrome
// in O(1) extra space
function isPalindrome($str)
{
    $firstChar = 0;
    $lastChar = count($str) - 1;
    $ch = true;

    for ($i = 0; $i < count($str); $i++)
    {
        $firstChar = firstPos($str, $firstChar,
                                    $lastChar);
        $lastChar = lastPos($str, $lastChar,
                                  $firstChar);

        // break, when all letters are checked
        if ($lastChar < 0 or $firstChar < 0)
            break;
        if ($str[$firstChar] == $str[$lastChar])
        {
            $firstChar++;
            $lastChar--;
            continue;
        }

        // if mismatch found,
        // break the loop
        $ch = false;
        break;
    }

    return ($ch);
}

// Driver code
$str = "m a 343 la y a l am";
if (isPalindrome($str))
    echo "YES";
else
    echo "NO";

// This code is contributed
// by inder_verma.
?>
```

## JavaScript

以下JavaScript程序以O(1)的额外空间检查给定字符串中的字符是否构成回文。

```javascript
<script>
// Javascript program to check if
// the characters in the given
// string forms a Palindrome
// in O(1) extra space

// Utility function to get
// the position of first
// character in the string
function firstPos(str,start,end)
{
    let firstChar = -1;

    // Get the position of
    // first character in
    // the string
    for(let i = start; i <= end; i++)
    {
        if(str[i] >= 'a'&&
        str[i] <= 'z')
        {
            firstChar = i;
            break;
        }
    }

    return firstChar;
}

// Utility function to get
// the position of last
// character in the string
function lastPos(str,start,end)
{
    let lastChar = -1;

    // Get the position of last
    // character in the string
    for(let i = start; i >= end; i--)
    {
        if(str[i] >= 'a'&&
        str[i] <= 'z')
        {
            lastChar = i;
            break;
        }
    }

    return lastChar;
}

// Function to check if the
// characters in the given
// string forms a Palindrome
// in O(1) extra space
function isPalindrome(str)
{
    let firstChar = 0,
        lastChar = str.length - 1;
    let ch = true;

    for (let i = 0; i < str.length; i++)
    {
        firstChar = firstPos(str, firstChar,
                                lastChar);
        lastChar = lastPos(str, lastChar,
                                firstChar);

        // break, when all
        // letters are checked
        if (lastChar < 0 || firstChar < 0)
            break;
        if (str[firstChar] ==
            str[lastChar])
        {
            firstChar++;
            lastChar--;
            continue;
        }

        // if mismatch found,
        // break the loop
        ch = false;
        break;
    }

        return ch;
}

// Driver code
let str = "m a 343 la y a l am";
if(isPalindrome(str))
    document.write("YES");
else
    document.write("NO");

// This code is contributed by avanitrachhadiya2155
</script>
```

**输出：**

```
YES
```