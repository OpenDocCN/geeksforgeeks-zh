# 根据给定条件检查两个字符串是否相等

> 原文: [https://www.geeksforgeeks.org/check-whether-two-strings-are-equivalent-or-not-according-to-given-condition/](https://www.geeksforgeeks.org/check-whether-two-strings-are-equivalent-or-not-according-to-given-condition/)

给定两根同等大小的字符串 `A` 和 `B`。两个字符串相等当且仅当以下任一条件成立：
1.  它们都相等。或者，
2.  如果我们把字符串 `A` 分成两个大小相同的连续子字符串 `A1` 和 `A2`，把字符串 `B` 分成两个大小相同的连续子字符串 `B1` 和 `B2`，那么下面的一个条件应该是正确的：
    *   `A1` 递归等价于 `B1`，且 `A2` 递归等价于 `B2`
    *   `A1` 递归等价于 `B2`，且 `A2` 递归等价于 `B1`

检查给定的字符串是否等价。打印 `YES` 或 `NO`。

## 示例

> **输入:** `A = "aaba"`, `B = "abaa"`
> **输出:** `YES`
> **说明:** 由于条件 1 不成立，我们可以把字符串 `A` 分成 `"aaba" = "aa" + "ba"`，把字符串 `B` 分成 `"abaa" = "ab" + "aa"`。这里，第 2 个子条件成立，其中 `A1` 等于 `B2`，`A2` 递归等于 `B1`。
>
> **输入:** `A = "AABB"`, `B = "abab"`
> **输出:** `NO`

## 解决方案

### 天真解决方案
一个简单的解决方案是考虑所有可能的场景。首先检查两个字符串是否相等，若相等则返回 `YES`；否则将字符串分开，检查是否 `A1 == B1` 且 `A2 == B2`，或 `A1 == B2` 且 `A2 == B1`。这个解决方案的时间复杂度是 `O(n^2)`，其中 `n` 是字符串的大小。

### 高效解决方案
我们来定义一下对字符串 `s` 的如下操作：我们可以把它分成两半，如果愿意的话可以互换。此外，我们可以递归地将这个操作应用于它的两个部分。通过仔细观察，我们可以看到，如果在对某个字符串 `A` 应用操作之后，我们可以得到 `B`，那么在对 `B` 应用操作之后，我们也可以得到 `A`。并且对于给定的两个字符串，我们可以递归地找到从它们可以得到的字典序最小的字符串。如果得到的字符串相等，答案是 `YES`，否则是 `NO`。例如，`"aaba"` 的最小字典序字符串是 `"aaab"`。`"abaa"` 的最小字典序字符串也是 `"aaab"`。因此这两者是等价的。

以下是上述办法的实现。

## C++

```cpp
// CPP Program to find whether two strings
// are equivalent or not according to given
// condition
#include <bits/stdc++.h>
using namespace std;

// This function returns the least lexicographical
// string obtained from its two halves
string leastLexiString(string s)
{
    // Base Case - If string size is 1
    if (s.size() & 1)
        return s;

    // Divide the string into its two halves
    string x = leastLexiString(s.substr(0,
                                        s.size() / 2));
    string y = leastLexiString(s.substr(s.size() / 2));

    // Form least lexicographical string
    return min(x + y, y + x);
}

bool areEquivalent(string a, string b)
{
  return (leastLexiString(a) == leastLexiString(b));
}

// Driver Code
int main()
{
    string a = "aaba";
    string b = "abaa";
    if (areEquivalent(a, b))
        cout << "YES" << endl;
    else
        cout << "NO" << endl;

    a = "aabb";
    b = "abab";
    if (areEquivalent(a, b))
        cout << "YES" << endl;
    else
        cout << "NO" << endl;
    return 0;
}
```

## Java

```java
// Java Program to find whether two strings
// are equivalent or not according to given
// condition
class GfG
{
    // This function returns the least lexicographical
    // String obtained from its two halves
    static String leastLexiString(String s)
    {
        // Base Case - If String size is 1
        if (s.length() == 1)
            return s;

        // Divide the String into its two halves
        String x = leastLexiString(s.substring(0,
                                            s.length() / 2));
        String y = leastLexiString(s.substring(s.length() / 2));

        // Form least lexicographical String
        return String.valueOf((x + y).compareTo(y + x));
    }

    static boolean areEquivalent(String a, String b)
    {
        return !(leastLexiString(a).equals(leastLexiString(b)));
    }

    // Driver Code
    public static void main(String[] args)
    {
        String a = "aaba";
        String b = "abaa";
        if (areEquivalent(a, b))
            System.out.println("Yes");
        else
            System.out.println("No");

        a = "aabb";
        b = "abab";
        if (areEquivalent(a, b))
            System.out.println("Yes");
        else
            System.out.println("No");
    }
}

/* This code contributed by PrinciRaj1992 */
```

## Python 3

```python
# Python 3 Program to find whether two strings
# are equivalent or not according to given
# condition

# This function returns the least lexicographical
# string obtained from its two halves
def leastLexiString(s):

    # Base Case - If string size is 1
    if (len(s) & 1 != 0):
        return s

    # Divide the string into its two halves
    x = leastLexiString(s[0:int(len(s) / 2)])
    y = leastLexiString(s[int(len(s) / 2):len(s)])

    # Form least lexicographical string
    return min(x + y, y + x)

def areEquivalent(a,b):
    return (leastLexiString(a) == leastLexiString(b))

# Driver Code
if __name__ == '__main__':
    a = "aaba"
    b = "abaa"
    if (areEquivalent(a, b)):
        print("YES")
    else:
        print("NO")

    a = "aabb"
    b = "abab"
    if (areEquivalent(a, b)):
        print("YES")
    else:
        print("NO")

# This code is contributed by
# Surendra_Gangwar
```

## C#

```csharp
// C# Program to find whether two strings
// are equivalent or not according to given
// condition
using System;
class GFG
{
    // This function returns the least lexicographical
    // String obtained from its two halves
    static String leastLexiString(String s)
    {
        // Base Case - If String size is 1
        if (s.Length == 1)
            return s;

        // Divide the String into its two halves
        String x = leastLexiString(s.Substring(0,
                                           s.Length / 2));
        String y = leastLexiString(s.Substring(
                                           s.Length / 2));

        // Form least lexicographical String
        return ((x + y).CompareTo(y + x).ToString());
    }

    static Boolean areEquivalent(String a, String b)
    {
        return !(leastLexiString(a).Equals(
                 leastLexiString(b)));
    }

    // Driver Code
    public static void Main(String[] args)
    {
        String a = "aaba";
        String b = "abaa";
        if (areEquivalent(a, b))
            Console.WriteLine("YES");
        else
            Console.WriteLine("NO");

        a = "aabb";
        b = "abab";
        if (areEquivalent(a, b))
            Console.WriteLine("YES");
        else
            Console.WriteLine("NO");
    }
}

// This code is contributed by PrinciRaj1992
```

## JavaScript

```javascript
<script>
    // Javascript Program to find whether two strings
    // are equivalent or not according to given
    // condition

    // This function returns the least lexicographical
    // String obtained from its two halves
    function leastLexiString(s)
    {
        // Base Case - If String size is 1
        if (s.length == 1)
            return s;

        // Divide the String into its two halves
        let x = leastLexiString(s.substring(0,
                                           s.length / 2));
        let y = leastLexiString(s.substring(
                                           s.length / 2));

        // Form least lexicographical String
        if((x + y) < (y + x))
        {
            return (x+y);
        }
        else{
            return (y+x);
        }
    }

    function areEquivalent(a, b)
    {
        return (leastLexiString(a) == leastLexiString(b));
    }

    let a = "aaba";
    let b = "abaa";
    if (areEquivalent(a, b))
        document.write("YES" + "</br>");
    else
        document.write("NO" + "</br>");

    a = "aabb";
    b = "abab";
    if (areEquivalent(a, b))
        document.write("YES" + "</br>");
    else
        document.write("NO" + "</br>");

// This code is contributed by decode2207.
</script>
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```php
<?php
// PHP Program to find whether two strings
// are equivalent or not according to given
// condition

// This function returns the least lexicogr
// aphical string obtained from its two halves
function leastLexiString($s)
{
    // Base Case - If string size is 1
    if (strlen($s) & 1)
        return $s;

    // Divide the string into its two halves
    $x = leastLexiString(substr($s, 0,floor(strlen($s) / 2)));
    $y = leastLexiString(substr($s,floor(strlen($s) / 2),strlen($s)));

    // Form least lexicographical string
    return min($x.$y, $y.$x);
}

function areEquivalent($a, $b)
{
    return (leastLexiString($a) == leastLexiString($b));
}

    // Driver Code
    $a = "aaba";
    $b = "abaa";
    if (areEquivalent($a, $b))
        echo "YES", "\n";
    else
        echo "NO", "\n";

    $a = "aabb";
    $b = "abab";
    if (areEquivalent($a, $b))
        echo "YES", "\n";
    else
        echo "NO","\n";

// This code is contributed by Ryuga
?>
```

**Output:**
```
YES
NO
```

**时间复杂度:** O(N*logN)，其中 N 是字符串的大小。
**辅助空间:** O(logN)