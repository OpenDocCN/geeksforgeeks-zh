# 通过在给定数字的数字之间插入加法或乘法运算符来找到最小值表达式

> 原文: [https://www.geeksforgeeks.org/find-minimum-value-expression-by-inserting-addition-or-multiplication-operator-between-digits-of-given-number/](https://www.geeksforgeeks.org/find-minimum-value-expression-by-inserting-addition-or-multiplication-operator-between-digits-of-given-number/)

给定仅包含数字的字符串 `str`，任务是通过在每两位数字之间插入 `+` 或 `*` 运算符来返回表达式，以使表达式的算术值最小化。

**例**:

> **输入** : `str = "322"`
> **输出**: `3+2*2`
> **解释**: 上述表达式的值为 7，是其他表达式 `3+2+2`、`3*2+2`、`3*2*2` 的最小值
>
> **输入** : `str = "391118571"`
> **输出**: `3+9*1*1*1+8+5+7*1`

**逼近**: 给定的问题可以用[贪婪的逼近](https://www.geeksforgeeks.org/greedy-algorithms/)来解决。按照以下步骤解决问题:

*   如果 `str` 包含字符 `0`，则:
    *   在字符串的每个字符之间插入乘法运算符
*   否则创建一个字符串 `ans` 来存储结果，迭代字符串，如果当前字符 `str[i]` 为:
    *   `1`，然后在当前字符和前一个字符之间插入乘法运算符 `*`
    *   不是 `1`，然后在当前字符和前一个字符之间插入加法运算符 `+`

下面是上述方法的实现:

## C++

```cpp
// C++ implementation for the above approach

#include <bits/stdc++.h>
using namespace std;
string minimalExpression(string str)
{
    // Initialize an empty string
    // to store the answer
    string ans = "";

    ans.push_back(str[0]);

    bool iszero = false;

    // Check if zero is present in the
    // string
    for (int i = 0; i < str.size();
         i++) {
        if (str[i] == '0') {
            iszero = true;
        }
    }

    // Insert all multiplication operators
    // between every digit of the string
    if (iszero) {
        for (int i = 1; i < str.size();
             i++) {
            ans.push_back('*');
            ans.push_back(str[i]);
        }
        return ans;
    }

    // Else calculate minimum expression
    // with combination of '*' and '+'
    // operators between digits
    for (int i = 1; i < str.size(); i++) {

        // If current character is '1' insert
        // multiplication operator between
        // current and previous character
        if (str[i] == '1') {
            ans.push_back('*');
            ans.push_back(str[i]);
        }

        // Else insert addition operator
        // between current and
        // previous character
        else {
            ans.push_back('+');
            ans.push_back(str[i]);
        }
    }

    // Return the result
    return ans;
}

// Driver Code
int main()
{
    string str = "391118571";
    cout << minimalExpression(str);
}
```

## Java

```java
// Java implementation for the above approach
class GFG {

    public static String minimalExpression(String str) {
        // Initialize an empty String
        // to store the answer
        String ans = "";

        ans = ans + str.charAt(0);

        boolean iszero = false;

        // Check if zero is present in the
        // String
        for (int i = 0; i < str.length(); i++) {
            if (str.charAt(i) == '0') {
                iszero = true;
            }
        }

        // Insert all multiplication operators
        // between every digit of the String
        if (iszero) {
            for (int i = 1; i < str.length(); i++) {
                ans += '*';
                ans += str.charAt(i);
            }
            return ans;
        }

        // Else calculate minimum expression
        // with combination of '*' and '+'
        // operators between digits
        for (int i = 1; i < str.length(); i++) {

            // If current character is '1' insert
            // multiplication operator between
            // current and previous character
            if (str.charAt(i) == '1') {
                ans += '*';
                ans += str.charAt(i);
            }

            // Else insert addition operator
            // between current and
            // previous character
            else {
                ans += '+';
                ans += str.charAt(i);
            }
        }

        // Return the result
        return ans;
    }

    // Driver Code
    public static void main(String args[]) {
        String str = "391118571";
        System.out.println(minimalExpression(str));
    }
}

// This code is contributed by saurabh_jaiswal.
```

## Python 3

```python
# python implementation for the above approach
def minimalExpression(str):

    # Initialize an empty string
    # to store the answer
    ans = ""
    ans += str[0]
    iszero = False

    # Check if zero is present in the
    # string
    for i in range(0, len(str)):
        if (str[i] == '0'):
            iszero = True

    # Insert all multiplication operators
    # between every digit of the string
    if (iszero):
        for i in range(1, len(str)):
            ans += '*'
            ans += str[i]

        return ans

    # Else calculate minimum expression
    # with combination of '*' and '+'
    # operators between digits
    for i in range(1, len(str)):

        # If current character is '1' insert
        # multiplication operator between
        # current and previous character
        if (str[i] == '1'):
            ans += '*'
            ans += str[i]

        # Else insert addition operator
        # between current and
        # previous character
        else:
            ans += '+'
            ans += str[i]

    # Return the result
    return ans

# Driver Code
if __name__ == "__main__":

    str = "391118571"
    print(minimalExpression(str))

# This code is contributed by rakeshsahni
```

## C#

```csharp
// C# implementation for the above approach

using System;
class GFG {
    static string minimalExpression(string str)
    {

        // Initialize an empty string
        // to store the answer
        string ans = "";

        ans += str[0];

        bool iszero = false;

        // Check if zero is present in the
        // string
        for (int i = 0; i < str.Length; i++) {
            if (str[i] == '0') {
                iszero = true;
            }
        }

        // Insert all multiplication operators
        // between every digit of the string
        if (iszero) {
            for (int i = 1; i < str.Length; i++) {
                ans += '*';
                ans += (str[i]);
            }
            return ans;
        }

        // Else calculate minimum expression
        // with combination of '*' and '+'
        // operators between digits
        for (int i = 1; i < str.Length; i++) {

            // If current character is '1' insert
            // multiplication operator between
            // current and previous character
            if (str[i] == '1') {
                ans += '*';
                ans += (str[i]);
            }

            // Else insert addition operator
            // between current and
            // previous character
            else {
                ans += '+';
                ans += (str[i]);
            }
        }

        // Return the result
        return ans;
    }

    // Driver Code
    public static void Main()
    {
        string str = "391118571";
        Console.WriteLine(minimalExpression(str));
    }
}

// This code is contributed by ukasp.
```

# java 描述语言

```javascript
<script>
// Javascript implementation for the above approach

function minimalExpression(str) {
  // Initialize an empty string
  // to store the answer
  let ans = [];

  ans.push(str[0]);

  let iszero = false;

  // Check if zero is present in the
  // string
  for (let i = 0; i < str.length; i++) {
    if (str[i] == "0") {
      iszero = true;
    }
  }

  // Insert all multiplication operators
  // between every digit of the string
  if (iszero) {
    for (let i = 1; i < str.length; i++) {
      ans.push("*");
      ans.push(str[i]);
    }
    return ans;
  }

  // Else calculate minimum expression
  // with combination of '*' and '+'
  // operators between digits
  for (let i = 1; i < str.length; i++) {
    // If current character is '1' insert
    // multiplication operator between
    // current and previous character
    if (str[i] == "1") {
      ans.push("*");
      ans.push(str[i]);
    }

    // Else insert addition operator
    // between current and
    // previous character
    else {
      ans.push("+");
      ans.push(str[i]);
    }
  }

  // Return the result
  return ans.join("");
}

// Driver Code

let str = "391118571";
document.write(minimalExpression(str));

// This code is contributed by saurabh_jaiswal.
</script>
```

**Output**

```
3+9*1*1*1+8+5+7*1
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(N)`，其中 `N` 是给定字符串的长度