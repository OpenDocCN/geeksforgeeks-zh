# 旋转后以相同字符开始和结束的字符串数

> 原文：[https://www.geeksforgeeks.org/number-of-strings-which-starts-and-ends-with-same-character-after-rotations/](https://www.geeksforgeeks.org/number-of-strings-which-starts-and-ends-with-same-character-after-rotations/)

给定一个字符串 `str`，任务是在给定字符串的每个可能索引处旋转一圈后，找到以相同字符开始和结束的字符串的数量。

**示例：**

> **输入：** `str = "geeksforgeks"`
> **输出：** 2
> **解释：**
> 在每个索引处都有旋转的所有可能的字符串是：“geeksforgeeks”、“eeksforgeeksg”、“eksforgeeksge”、“ksforgeeksgee”、“sforgeeksgeek”、“forgeeksgeeks”、“orgeeksgeeksg”、“rgeeksgeeksge”、“geeksgeeksgeo”、“eeksgeeksgeof”、“eksgeeksforge”、“ksgeeksforgee”、“sgeeksforgeek”。
> 在上述字符串中，只有 2 个字符串以相同的字符开头和结尾：“eksforgeeksge”和“eksgeeksforge”。
>
> **输入：** `str = "aabcdd"`
> **输出：** 3
> **解释：**
> 所有在每个索引处有旋转的可能字符串为：“aabcdd”、“aabcdda”、“abcdada”、“bcddaab”、“cddaaba”、“ddaabca”、“daabcdd”。
> 在上述字符串中，只有 3 个字符串以相同的字符开头和结尾：“aabcdda”、“abcddaa”和“daabcdd”。

**天真方法：** 想法是生成给定字符串所有可能的旋转，并检查旋转后形成的每个字符串是否以相同的字符开始和结束。如果是，则将该字符串包括在计数中。打印最终计数。

**有效方法：** 计算可能字符串的有效方法是在具有连续相同字符的索引处旋转给定字符串。因此，最终计数是给定字符串中每个连续字符的 `(连续相同字符数 – 1)`。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the count of string
// with equal end after rotations
int countStrings(string s)
{
    // To store the final count
    int cnt = 0;

    // Traverse the string
    for (int i = 1; s[i]; i++) {
        // If current character is same
        // as the previous character then
        // increment the count
        if (s[i] == s[i + 1]) {
            cnt++;
        }
    }

    // Return the final count
    return cnt;
}

// Driver Code
int main()
{
    // Given string
    string str("aacbb");

    // Function Call
    cout << countStrings(str);
    return 0;
}
```

## Java

```java
// Java program for the above approach
class GFG{

// Function to find the count of string
// with equal end after rotations
static int countStrings(String s)
{

    // To store the final count
    int cnt = 0;

    // Traverse the string
    for(int i = 1; i < s.length() - 1; i++)
    {

       // If current character is same
       // as the previous character then
       // increment the count
       if (s.charAt(i) == s.charAt(i + 1))
       {
           cnt++;
       }
    }

    // Return the final count
    return cnt;
}

// Driver Code
public static void main(String[] args)
{

    // Given string
    String str = "aacbb";

    // Function call
    System.out.println(countStrings(str));
}
}

// This code is contributed by rutvik_56
```

## Python 3

```python
# Python3 program for the above approach

# Function to find the count of string
# with equal end after rotations
def countStrings(s):

    # To store the final count
    cnt = 0;

    # Traverse the string
    for i in range(1, len(s) - 1):

        # If current character is same
        # as the previous character then
        # increment the count
        if (s[i] == s[i + 1]):
            cnt += 1;

    # Return the final count
    return cnt;

# Driver Code
if __name__ == '__main__':

    # Given string
    str = "aacbb";

    # Function call
    print(countStrings(str));

# This code is contributed by 29AjayKumar
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to find the count of string
// with equal end after rotations
static int countStrings(String s)
{

    // To store the final count
    int cnt = 0;

    // Traverse the string
    for(int i = 1; i < s.Length - 1; i++)
    {

       // If current character is same
       // as the previous character then
       // increment the count
       if (s[i] == s[i + 1])
       {
           cnt++;
       }
    }

    // Return the final count
    return cnt;
}

// Driver Code
public static void Main(String[] args)
{

    // Given string
    String str = "aacbb";

    // Function call
    Console.WriteLine(countStrings(str));
}
}

// This code is contributed by sapnasingh4991
```

## JavaScript

```javascript
<script>

// javascript program for the above approach

// Function to find the count of string
// with equal end after rotations
function countStrings( s)
{
    // To store the final count
    let cnt = 0;

    // Traverse the string
    for (let i = 1; s[i]; i++) {
        // If current character is same
        // as the previous character then
        // increment the count
        if (s[i] == s[i + 1]) {
            cnt++;
        }
    }

    // Return the final count
    return cnt;
}

// Driver Code

    // Given string
    let str = "aacbb";

    // Function Call
        document.write(countStrings(str));

// This code contributed by gauravrajsum1

</script>
```

**输出：**

```
3
```

**时间复杂度：** `O(N)`，其中 `N` 为给定字符串的长度。