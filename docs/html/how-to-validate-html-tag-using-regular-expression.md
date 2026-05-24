# 如何使用正则表达式

验证 HTML 标签

> 原文:[https://www . geesforgeks . org/如何使用正则表达式验证 html-tag/](https://www.geeksforgeeks.org/how-to-validate-html-tag-using-regular-expression/)

给定字符串 **str** ，任务是使用[正则表达式](https://www.geeksforgeeks.org/write-regular-expressions/)检查是否是有效的 [HTML 标签](https://www.geeksforgeeks.org/most-commonly-used-tags-in-html/)。
有效的 HTML 标签必须满足以下条件:

1.  它应该以一个开始标记(
2.  它应该后跟一个双引号字符串或单引号字符串。
3.  它不应该允许一个双引号字符串、一个单引号字符串或一个结束标记(>)不带单引号或双引号。
4.  它应该以结束标记(>)结束。

**示例:**

> **输入:**str = " T44 "输入值= '>'>"；
> **输出:**真
> **说明:**给定的字符串满足上述所有条件。
> **输入:**str = " T47 " br/>"；
> **输出:**真
> **说明:**给定字符串满足上述所有条件。
> **输入:**str = " br/>"；
> **输出:**假
> **解释:**给定的字符串不是以开始标记“<”开始的。因此，它不是有效的 HTML 标记。
> **输入:**str = "<' br/>"；
> **输出:**假
> **说明:**给定字符串有一个单引号字符串是不允许的。因此，它不是有效的 HTML 标记。
> **输入:**str =<输入值=>>"；
> **输出:**假
> **解释:**给定字符串有一个结束标记(>)，没有单引号或双引号，这是不允许的。因此，它不是有效的 HTML 标记。

**做法:**思路是用正则表达式来解决这个问题。可以按照以下步骤计算答案。

*   获取字符串。
*   创建一个正则表达式来检查有效的 HTML 标记，如下所述:

> regex = "])* > "；

*   其中:
    *   **<** 代表字符串应该以一个开始标记(<)开始。
    *   **(** 代表组的开始。
    *   **【^"]*】**代表字符串应允许双引号括起来的字符串。
    *   **|** 代表或。
    *   **'[^']*** 代表字符串应允许单引号括起来的字符串。
    *   **|** 代表或。
    *   **【^'】>**代表字符串不应包含单引号、双引号和“>”。
    *   **)** 代表团体结束。
    *   ***** 代表 0 或更大。
    *   **>** 代表字符串应以结束标记(>)结束。
*   将给定的字符串与正则表达式匹配。在 Java 中，这可以通过使用[**pattern . matcher()**](https://www.geeksforgeeks.org/matcher-pattern-method-in-java-with-examples/)来完成。
*   如果字符串与给定的正则表达式匹配，则返回 true，否则返回 false。

以下是上述方法的实现:

## C++

```html
// C++ program to validate the
// HTML tag using Regular Expression
#include <iostream>
#include <regex>
using namespace std;

// Function to validate the HTML tag.
bool isValidHTMLTag(string str)
{

  // Regex to check valid HTML tag.
  const regex pattern("<(\"[^\"]*\"|'[^']*'|[^'\">])*>");

  // If the HTML tag
  // is empty return false
  if (str.empty())
  {
     return false;
  }

  // Return true if the HTML tag
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
  string str1 = "<input value = '>'>";
  cout << isValidHTMLTag(str1) << endl;

  // Test Case 2:
  string str2 = "<br/>";
  cout << isValidHTMLTag(str2) << endl;

  // Test Case 3:
  string str3 = "br/>";
  cout << isValidHTMLTag(str3) << endl;

  // Test Case 4:
  string str4 = "<'br/>";
  cout << isValidHTMLTag(str4) << endl;

  // Test Case 5:
  string str5 = "<input value => >";
  cout << isValidHTMLTag(str5) << endl;

  return 0;
}

// This code is contributed by yuvraj_chandra
```

## Java 语言(一种计算机语言，尤用于创建网站)

```html
// Java program to validate
// HTML tag using regex.

import java.util.regex.*;

class GFG {

    // Function to validate
    // HTML tag using regex.
    public static boolean
    isValidHTMLTag(String str)
    {
        // Regex to check valid HTML tag.
        String regex
            = "<(\"[^\"]*\"|'[^']*'|[^'\">])*>";

        // Compile the ReGex
        Pattern p = Pattern.compile(regex);

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

    // Driver Code.
    public static void main(String args[])
    {

        // Test Case 1:
        String str1 = "<input value = '>'>";
        System.out.println(isValidHTMLTag(str1));

        // Test Case 2:
        String str2 = "<br/>";
        System.out.println(isValidHTMLTag(str2));

        // Test Case 3:
        String str3 = "br/>";
        System.out.println(isValidHTMLTag(str3));

        // Test Case 4:
        String str4 = "<'br/>";
        System.out.println(isValidHTMLTag(str4));

        // Test Case 5:
        String str5 = "<input value => >";
        System.out.println(isValidHTMLTag(str5));
    }
}
```

## 蟒蛇 3

```html
# Python3 program to validate
# HTML tag using regex.  
# using regular expression
import re

# Function to validate
# HTML tag using regex.
def isValidHTMLTag(str):

    # Regex to check valid
    # HTML tag using regex.
    regex = "<(\"[^\"]*\"|'[^']*'|[^'\">])*>"

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
str1 = "<input value = '>'>"
print(isValidHTMLTag(str1))

# Test Case 2:
str2 = "<br/>"
print(isValidHTMLTag(str2))

# Test Case 3:
str3 = "br/>"
print(isValidHTMLTag(str3))

# Test Case 4:
str4 = "<'br/>"
print(isValidHTMLTag(str4))

# This code is contributed by avanitrachhadiya2155
```

**Output:** 

```html
true
true
false
false
false
```