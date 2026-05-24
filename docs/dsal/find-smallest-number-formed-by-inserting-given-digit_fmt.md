# 找出插入给定数字形成的最小数字

> 原文: [https://www.geeksforgeeks.org/find-smallest-number-formed-by-inserting-given-digit/](https://www.geeksforgeeks.org/find-smallest-number-formed-by-inserting-given-digit/)

## 问题描述

给定一个字符串 `N` 和一个数字 `X`（范围 `[1, 9]`），任务是在 `N` 的任意位置插入数字 `X`，找出能构成的**最小**整数。

## 示例

> **输入:** `N = "89"`, `X = 1`
> **输出:** `"189"`
> **说明:** `X` 可以插入 3 个位置 `{189, 891, 819}`，其中 `189` 为最小值。
>
> **输入:** `N = "-12"`, `X = 3`
> **输出:** `"-312"`

## 解法

### 朴素法

解决这个问题的一个简单方法是在所有可能的位置上插入 `X`（如果有负号的话，除了最左边），并在所有形成的数字中找到**最小值**。在字符串较长的情况下，这种方法是**低效的**。

### 有效方法

主要思想是：如果 `N` 是正数，则插入方式应使形成的数字**最小**；而如果 `N` 是负数，则插入 `X` 应使形成的数字**最大**（忽略负号）。按照以下步骤优化上述方法：

1.  初始化两个变量，比如 `len = 字符串 N 的长度` 和 `position = len + 1`。
2.  如果 `N` 为负数（`N[0] == '-'`），则[遍历字符串](https://www.geeksforgeeks.org/iterate-over-characters-of-a-string-in-c/)从 `(len-1)` 索引到 `1` 索引，检查 `N[i] - '0' < X`，如果为真则更新 `position = i`。
3.  如果 `N` 为正数，则[遍历字符串](https://www.geeksforgeeks.org/iterate-over-characters-of-a-string-in-c/)从 `(len-1)` 索引到 `0` 索引，检查 `N[i] - '0' > X`，如果为真则更新 `position = i`。
4.  将 `X` 插入 `N` 中的索引 `position` 处。
5.  最后，返回字符串 `N`。

## 代码实现

下面是上述方法的实现：

### C++

```cpp
// C++ implementation of above approach
#include <bits/stdc++.h>
using namespace std;

// Function to insert X in N and
// return the minimum value string
string MinValue(string N, int X)
{

    // Variable to store length
    // of string N
    int len = N.size();

    // Variable to denote the position
    // where X must be added
    int position = len + 1;

    // If the given string N represent
    // a negative value
    if (N[0] == '-') {
        // X must be place at the last
        // index where is greater than N[i]
        for (int i = len - 1; i >= 1; i--) {
            if ((N[i] - '0') < X) {
                position = i;
            }
        }
    }
    else {
        // For positive numbers, X must be
        // placed at the last index where
        // it is smaller than N[i]
        for (int i = len - 1; i >= 0; i--) {
            if ((N[i] - '0') > X) {
                position = i;
            }
        }
    }
    // Insert X at that position
    N.insert(N.begin() + position, X + '0');

    // Return the string
    return N;
}

// Driver Code
int main()
{
    // Given Input
    string N = "89";
    int X = 1;

    // Function Call
    cout << MinValue(N, X) << "\n";
}
```

### Java

```java
// Java implementation of above approach
import java.io.*;
import java.lang.*;
import java.util.*;
public class GFG {

  // Function to insert X in N and
  // return the minimum value string
  static String MinValue(String number, int x)
  {

    // Variable to store length
    // of string N
    int length = number.length();

    // Variable to denote the position
    // where X must be added
    int position = length + 1;

    // If the given string N represent
    // a negative value
    if (number.charAt(0) == '-') {

      // X must be place at the last
      // index where is greater than N[i]
      for (int i = number.length() - 1; i >= 1; --i) {
        if ((number.charAt(i) - 48) < x) {
          position = i;
        }
      }
    }
    else {

      // For positive numbers, X must be
      // placed at the last index where
      // it is smaller than N[i]
      for (int i = number.length() - 1; i >= 0; --i) {
        if ((number.charAt(i) - 48) > x) {
          position = i;
        }
      }
    }

    // Insert X at that position
    number
      = number.substring(0, position) + x
      + number.substring(position, number.length());

    // return string
    return number.toString();
  }

  // Driver call
  public static void main(String[] args)
  {

    // given input
    String number = "89";
    int x = 1;

    // function call
    System.out.print(MinValue(number, x));
  }
}

// This code is contributed by zack_aayush.
```

### Python 3

```python
# Python Program for the above approach

# Function to insert X in N and
# return the minimum value string
def MinValue(N, X):

    # Variable to store length
    # of string N
    N = list(N);
    ln = len(N)

    # Variable to denote the position
    # where X must be added
    position = ln + 1

    # If the given string N represent
    # a negative value
    if (N[0] == '-'):

        # X must be place at the last
        # index where is greater than N[i]
        for i in range(ln - 1, 0, -1):
            if ((ord(N[i]) - ord('0')) < X):
                position = i

    else:
        # For positive numbers, X must be
        # placed at the last index where
        # it is smaller than N[i]
        for i in range(ln - 1, -1, -1):
            if ((ord(N[i]) - ord('0')) > X):
                position = i

    # Insert X at that position
    c = chr(X + ord('0'))

    str = N.insert(position, c);

    # Return the string
    return ''.join(N)

# Driver Code

# Given Input
N = "89"
X = 1

# Function Call
print(MinValue(N, X))

# This code is contributed by gfgking
```

### C#

```csharp
// C# program for the above approach
using System;

class GFG {

  // Function to insert X in N and
  // return the minimum value string
  static String MinValue(string number, int x)
  {

    // Variable to store length
    // of string N
    int length = number.Length;

    // Variable to denote the position
    // where X must be added
    int position = length + 1;

    // If the given string N represent
    // a negative value
    if (number[0] == '-') {

      // X must be place at the last
      // index where is greater than N[i]
      for (int i = number.Length - 1; i >= 1; --i) {
        if ((number[i] - 48) < x) {
          position = i;
        }
      }
    }
    else {

      // For positive numbers, X must be
      // placed at the last index where
      // it is smaller than N[i]
      for (int i = number.Length - 1; i >= 0; --i) {
        if ((number[i] - 48) > x) {
          position = i;
        }
      }
    }

    // Insert X at that position
    number
      = number.Substring(0, position) + x
      + number.Substring(position, number.Length);

    // return string
    return number.ToString();
  }

    // Driver code
    public static void Main()
    {
        // given input
    string number = "89";
    int x = 1;

    // function call
    Console.WriteLine(MinValue(number, x));
    }
}

// This code is contributed by avijitmondal1998.
```

## java 描述语言

```
<script>
     // JavaScript Program for the above approach

     // Function to insert X in N and
     // return the minimum value string
     function MinValue(N, X) {

         // Variable to store length
         // of string N
         let len = N.length;

         // Variable to denote the position
         // where X must be added
         let position = len + 1;

         // If the given string N represent
         // a negative value
         if (N[0] == '-') {
             // X must be place at the last
             // index where is greater than N[i]
             for (let i = len - 1; i >= 1; i--) {
                 if ((N[i].charCodeAt(0) - '0'.charCodeAt(0)) < X) {
                     position = i;
                 }
             }
         }
         else {
             // For positive numbers, X must be
             // placed at the last index where
             // it is smaller than N[i]
             for (let i = len - 1; i >= 0; i--) {
                 if ((N[i].charCodeAt(0) - '0'.charCodeAt(0)) > X) {
                     position = i;
                 }
             }
         }

         // Insert X at that position
         const c = String.fromCharCode(X + '0'.charCodeAt(0));

         let str = N.slice(0, position) + c + N.slice(position);

         // Return the string
         return str;
     }

     // Driver Code

     // Given Input
     let N = "89";
     let X = 1;

     // Function Call
     document.write(MinValue(N, X));

 // This code is contributed by Potta Lokesh
 </script>
```

`Output`

```

```

时间复杂度: `O(N)`
辅助空间: `O(1)`