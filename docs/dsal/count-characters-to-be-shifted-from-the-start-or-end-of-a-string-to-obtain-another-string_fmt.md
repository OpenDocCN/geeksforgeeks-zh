# 从一个字符串的开头或结尾开始计算要移位的字符，以获得另一个字符串

> 原文: [https://www.geeksforgeeks.org/count-characters-to-be-shifted-from-the-start-or-end-of-a-string-to-obtain-another-string/](https://www.geeksforgeeks.org/count-characters-to-be-shifted-from-the-start-or-end-of-a-string-to-obtain-another-string/)

## 问题描述

给定两个字符串 `A` 和 `B`，其中字符串 `A` 是字符串 `B` 的字谜。一次操作，去掉字符串 `A` 的第一个或最后一个字符，插入到 `A` 的任意位置。任务是找到将字符串 `A` 转换为字符串 `B` 所需执行的此类操作的最小数量。

## 示例

**输入:**
`A = "edab"`, `B = "abcde"`
**输出:** 3
**解释:**
执行给定的操作如下:
**步骤 1:** 取最后一个字符 `'b'` 并将其插入到 `'a'` 和 `'c'` 之间 (`"edab"` 变成 `"edacb"`)
**步骤 2:** 取第一个字符 `'e'` 将其插入到最后 (`"edacb"` 变成 `"dacbe"`)
**步骤 3:** 取第一个字符 `'d'` 将其插入到 `'a'` 和 `'c'` 之间 (`"dacbe"` 变成 `"adcbe"`)

**输入:**
`A = "abcd"`, `B = "abdc"`
**输出:** 1
**解释:**
执行给定的操作如下:
**步骤 1:** 取最后一个字符 `'d'` 并插入到 `'b'` 和 `'c'` 之间 (`"abcd"` 变成 `"abdc"`)
因此，操作的计数为 1。

## 方法

思路是找到字符串 `A` 的最长子串，该子串也是字符串 `B` 的子串，从给定的字符串长度中减去这个值，得到所需操作的最小计数。

下面是上述方法的实现:

## C++14

```cpp
// C++14 program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the minimum cost
// to convert string A to string B
int minCost(string A, string B)
{

    // Length of string
    int n = A.size();

    int i = 0;

    // Initialize maxlen as 0
    int maxlen = 0;

    // Traverse the string A
    while (i < n)
    {

        // Stores the length of
        // substrings of string A
        int length = 0;

        // Traversing string B for
        // each character of A
        for(int j = 0; j < n; ++j)
        {

            // Shift i pointer towards
            // right and increment length,
            // if A[i] equals B[j]
            if (A[i] == B[j])
            {
                ++i;
                ++length;

                // If traverse till end
                if (i == n)
                break;
            }
        }

        // Update maxlen
        maxlen = max(maxlen,
                     length);
    }

    // Return minimum cost
    return n - maxlen;
}

// Driver Code
int main()
{

    // Given two strings A and B
    string A = "edacb";
    string B = "abcde";

    // Function call
    cout << minCost(A, B) << endl;
}

// This code is contributed by sanjoy_62
```

## Java

```java
// Java Program for the above approach

import java.util.*;
import java.lang.*;

class GFG {

    // Function to find the minimum cost
    // to convert string A to string B
    static int minCost(String A, String B)
    {
        // Length of string
        int n = A.length();

        int i = 0;

        // Initialize maxlen as 0
        int maxlen = 0;

        // Traverse the string A
        while (i < n) {

            // Stores the length of
            // substrings of string A
            int length = 0;

            // Traversing string B for
            // each character of A
            for (int j = 0; j < n; ++j) {

                // Shift i pointer towards
                // right and increment length,
                // if A[i] equals B[j]
                if (A.charAt(i) == B.charAt(j)) {

                    ++i;
                    ++length;

                    // If traverse till end
                    if (i == n)
                        break;
                }
            }

            // Update maxlen
            maxlen = Math.max(maxlen,
                              length);
        }

        // Return minimum cost
        return n - maxlen;
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Given two strings A and B
        String A = "edacb";
        String B = "abcde";

        // Function call
        System.out.println(minCost(A, B));
    }
}
```

## Python 3

```python
# Python3 Program for
# the above approach
# Function to find the
# minimum cost to convert
# string A to string B
def minCost(A, B):

    # Length of string
    n = len(A);

    i = 0;

    # Initialize maxlen as 0
    maxlen = 0;

    # Traverse the string A
    while (i < n):

        # Stores the length of
        # substrings of string A
        length = 0;

        # Traversing string B for
        # each character of A
        for j in range(0, n):

            # Shift i pointer towards
            # right and increment length,
            # if A[i] equals B[j]
            if (A[i] == B[j]):

                i+= 1
                length+=1;

                # If traverse till end
                if (i == n):
                    break;

        # Update maxlen
        maxlen = max(maxlen, length);

    # Return minimum cost
    return n - maxlen;

# Driver Code
if __name__ == '__main__':

    # Given two strings A and B
    A = "edacb";
    B = "abcde";

    # Function call
    print(minCost(A, B));

# This code is contributed by Rajput-Ji
```

## C#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to find the minimum cost
// to convert string A to string B
static int minCost(string A, string B)
{

    // Length of string
    int n = A.Length;

    int i = 0;

    // Initialize maxlen as 0
    int maxlen = 0;

    // Traverse the string A
    while (i < n)
    {

        // Stores the length of
        // substrings of string A
        int length = 0;

        // Traversing string B for
        // each character of A
        for(int j = 0; j < n; ++j)
        {

            // Shift i pointer towards
            // right and increment length,
            // if A[i] equals B[j]
            if (A[i] == B[j])
            {
                ++i;
                ++length;

                // If traverse till end
                if (i == n)
                    break;
            }
        }

        // Update maxlen
        maxlen = Math.Max(maxlen,
                          length);
    }

    // Return minimum cost
    return n - maxlen;
}

// Driver Code
public static void Main()
{

    // Given two strings A and B
    string A = "edacb";
    string B = "abcde";

    // Function call
    Console.WriteLine(minCost(A, B));
}
}

// This code is contributed by sanjoy_62
```

## JavaScript

```javascript
<script>

// Javascript program for the above approach

// Function to find the minimum cost
// to convert string A to string B
function minCost(A, B)
{

    // Length of string
    var n = A.length;

    var i = 0;

    // Initialize maxlen as 0
    var maxlen = 0;

    // Traverse the string A
    while (i < n)
    {

        // Stores the length of
        // substrings of string A
        var length = 0;

        // Traversing string B for
        // each character of A
        for(var j = 0; j < n; ++j)
        {

            // Shift i pointer towards
            // right and increment length,
            // if A[i] equals B[j]
            if (A[i] == B[j])
            {
                ++i;
                ++length;

                // If traverse till end
                if (i == n)
                break;
            }
        }

        // Update maxlen
        maxlen = Math.max(maxlen,
                     length);
    }

    // Return minimum cost
    return n - maxlen;
}

// Driver Code
// Given two strings A and B
var A = "edacb";
var B = "abcde";

// Function call
document.write(minCost(A, B));

// This code is contributed by itsok.
</script>
```

## 复杂度分析

**时间复杂度:** `O(N^2)`，其中 `N` 为字符串的长度。
**辅助空间:** `O(N)`。