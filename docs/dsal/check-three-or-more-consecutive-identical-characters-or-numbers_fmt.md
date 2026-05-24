# 检查三个或三个以上连续的相同字符或数字

> 原文: [https://www.geeksforgeeks.org/check-three-or-more-consecutive-identical-characters-or-numbers/](https://www.geeksforgeeks.org/check-three-or-more-consecutive-identical-characters-or-numbers/)

给定字符串 `str`，任务是使用[正则表达式](https://www.geeksforgeeks.org/write-regular-expressions/)检查给定字符串是否包含 3 个或更多连续的相同字符/数字。

## 示例

> **输入:** `str = "AAA";`
> **输出:** `true`
> **解释:**
> 给定的字符串包含 'A'、'A'、'A'，它们是连续的相同字符。
> **输入:** `str = "ABC";`
> **输出:** `false`
> **说明:**
> 给定字符串包含 'A'、'B'、'C'，它们不是连续的相同字符。
> **输入:** `str = "11";`
> **输出:** `false`
> **解释:**
> 给定字符串包含 '1'、'1'，它们不是 3 个或更多连续的相同数字。

## 解决方法

思路是用[正则表达式](https://www.geeksforgeeks.org/write-regular-expressions/)来解决这个问题。可以按照以下步骤计算答案。

1.  获取字符串。
2.  创建一个正则表达式来检查 3 个或更多连续的相同字符或数字，如下所述:
    `regex = "\\b([a-zA-Z0-9])\\1\\1+\\b";`
    其中:
    *   `\b` 代表单词边界。
    *   `(` 代表组 1 的开始。
    *   `[a-zA-Z0-9]` 代表字母或数字。
    *   `)` 代表第 1 组的结束。
    *   `\1` 代表与组 1 相同的字符。
    *   `\1+` 一次或多次代表与组 1 相同的字符。
    *   `\b` 代表单词边界。
3.  将给定的字符串与正则表达式匹配。在 Java 中，这可以通过使用 `Pattern.matcher()` 来完成。
4.  如果字符串与给定的正则表达式匹配，则返回 `true`，否则返回 `false`。

以下是上述方法的实现:

## C++

```cpp
// C++ program to check
// three or more consecutive identical
// characters or numbers using Regular Expression
#include <iostream>
#include <regex>
using namespace std;

// Function to check three or more
// consecutive identical characters or numbers.
bool isIdentical(string str)
{

    // Regex to check valid three or more
    // consecutive identical characters or numbers.
    const regex pattern("\\b([a-zA-Z0-9])\\1\\1+\\b");

    // If the three or more consecutive
    // identical characters or numbers
    // is empty return false
    if (str.empty())
    {
        return false;
    }

    // Return true if the three or more
    // consecutive identical characters or numbers
    // matched the ReGex
    if(regex_match(str, pattern))
    {
        return true;
    }
    else
    {
        return false;
    }
}

// Driver Code
int main()
{

    // Test Case 1:
    string str1 = "aaa";
    cout << isIdentical(str1) << endl;

    // Test Case 2:
    string str2 = "11111";
    cout << isIdentical(str2) << endl;

    // Test Case 3:
    string str3 = "aaab";
    cout << isIdentical(str3) << endl;

    // Test Case 4:
    string str4 = "abc";
    cout << isIdentical(str4) << endl;

    // Test Case 5:
    string str5 = "aa";
    cout << isIdentical(str5) << endl;
    return 0;
}

// This code is contributed by yuvraj_chandra
```

## Java

```java
// Java program to check three or
// more consecutive identical
// characters or numbers
// using regular expression

import java.util.regex.*;
class GFG {

    // Function to check three or
    // more consecutive identical
    // characters or numbers
    // using regular expression
    public static boolean isIdentical(String str)
    {
        // Regex to check three or
        // more consecutive identical
        // characters or numbers
        String regex
            = "\\b([a-zA-Z0-9])\\1\\1+\\b";

        // Compile the ReGex
        Pattern p
            = Pattern.compile(regex);

        // If the string is empty
        // return false
        if (str == null) {
            return false;
        }

        // Find match between given string
        // and regular expression
        // using Pattern.matcher()
        Matcher m = p.matcher(str);

        // Return if the string
        // matched the ReGex
        return m.matches();
    }

    // Driver code
    public static void main(String args[])
    {

        // Test Case 1:
        String str1 = "aaa";
        System.out.println(
            isIdentical(str1));

        // Test Case 2:
        String str2 = "11111";
        System.out.println(
            isIdentical(str2));

        // Test Case 3:
        String str3 = "aaab";
        System.out.println(
            isIdentical(str3));

        // Test Case 4:
        String str4 = "abc";
        System.out.println(
            isIdentical(str4));

        // Test Case 5:
        String str5 = "aa";
        System.out.println(
            isIdentical(str5));
    }
}
```

## Python 3

```python
# Python3 program to check three or
# more consecutive identical
# characters or numbers
# using regular expression
import re

# Function to check three or
# more consecutive identical
# characters or numbers
# using regular expression
def isValidGUID(str):

    # Regex to check three or
    # more consecutive identical
    # characters or numbers
    regex = "\\b([a-zA-Z0-9])\\1\\1+\\b"

    # Compile the ReGex
    p = re.compile(regex)

    # If the string is empty
    # return false
    if (str == None):
        return False

    # Return if the string
    # matched the ReGex
    if(re.search(p, str)):
        return True
    else:
        return False

# Driver code

# Test Case 1:
str1 = "aaa"
print(isValidGUID(str1))

# Test Case 2:
str2 = "11111"
print(isValidGUID(str2))

# Test Case 3:
str3 = "aaab"
print(isValidGUID(str3))

# Test Case 4:
str4 = "abc"
print(isValidGUID(str4))

# Test Case 5:
str5 = "aa"
print(isValidGUID(str5))

# This code is contributed by avanitrachhadiya2155
```

## 输出

```
true
true
false
false
false
```