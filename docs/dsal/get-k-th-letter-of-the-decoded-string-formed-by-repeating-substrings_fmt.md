# 获取由重复子串构成的解码字符串的第 K 个字母

> 原文: [https://www.geeksforgeeks.org/get-k-th-letter-of-the-decoded-string-formed-by-repeating-substrings/](https://www.geeksforgeeks.org/get-k-th-letter-of-the-decoded-string-formed-by-repeating-substrings/)

给定一个包含**字母**和**数字**的字符串 `S` 和一个整数 `K`，其中，`2 <= S.length() <= 100` 和 `1 <= K <= 10^9`。任务是返回新字符串 `S'` 的第 `K` 个字母。
新字符串 `S'` 由旧字符串 `S` 经以下步骤形成:
1.  如果读取的字符是一个**字母**，则该字母添加在 `S'` 的末尾。
2.  如果读取的字符是一个**数字**，那么整个字符串 `S'` 总共重复写入 `d-1` 更多次。

**注:** 新字符串保证少于 `2^63` 个字母。

**例:**

> 输入: `S = "geeks2for2"`, `K = 15`
> 输出: `"e"`
> 说明: 新字符串 `S' = "geeksgeeforgeksgeekfor"`。第 15 个字母是 `"e"`。

> 输入: `S = "a2345"`, `K = 100`
> 输出: `"a"`
> 说明: 新字符串 `S' = "a"` 重复 120 次。第 100 个字母是 `"a"`。

让我们取一个像 `S' = "geeksgeeksgeeksgeeks"` 这样的新字符串和一个索引 `K = 22`，那么如果 `K = 2`，那么 `K = 22` 的答案是一样的。
一般来说，当一个字符串等于某个大小长度的**单词**重复某个次数时（比如大小=5的`geeks`重复5次），那么对于索引 `K` 的答案会和对于索引 `K % size` 的答案一样。
利用这种洞察力并向后操作，我们跟踪新字符串 `S'` 的**尺寸**。每当字符串等于某个单词重复 `d` 次时，我们可以将 `K` 减少到 `K % (单词长度)`。
我们先找到新字符串 `S'` 的长度。之后，我们将向后操作，记录大小: 解析符号 `S[0]、S[1]、…、S[i]` 后新字符串的长度。
如果看到一个数字 `S[i]`，表示解析 `S[0]，S[1]，…，S[i-1]` 后新字符串的大小将为 `(size / toInteger(S[i]))`。否则为 `size - 1`。

**以下是上述做法的实施:**

## C++

```cpp
// CPP implementation of above approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the K-th letter from new String.
string K_thletter(string S, int K)
{
    int N = S.size();
    long size = 0;

    // finding size = length of new string S'
    for (int i = 0; i < N; ++i) {
        if (isdigit(S[i]))
            size = size * (S[i] - '0');
        else
            size += 1;
    }

    // get the K-th letter
    for (int i = N - 1; i >= 0; --i) {
        K %= size;

        if (K == 0 && isalpha(S[i]))
            return (string) "" + S[i];

        if (isdigit(S[i]))
            size = size / (S[i] - '0');
        else
            size -= 1;
    }
}

// Driver program
int main()
{
    string S = "geeks2for2";
    int K = 15;

    cout << K_thletter(S, K);

    return 0;
}

// This code is written by Sanjit_Prasad
```

## Java

```java
// Java implementation of above approach
class GFG
{
    // Function to return the K-th letter from new String.
    static String K_thletter(String S, int K)
    {
        int N = S.length();
        long size = 0;

        // finding size = length of new string S'
        for (int i = 0; i < N; ++i)
        {
            if (Character.isDigit(S.charAt(i)))
            {
                size = size * (S.charAt(i) - '0');
            }
            else
            {
                size += 1;
            }
        }

        // get the K-th letter
        for (int i = N - 1; i >= 0; --i)
        {
            K %= size;
            if (K == 0 && Character.isAlphabetic(S.charAt(i)))
            {
                return (String) "" + S.charAt(i);
            }

            if (Character.isDigit(S.charAt(i)))
            {
                size = size / (S.charAt(i) - '0');
            }
            else
            {
                size -= 1;
            }
        }
        return null;
    }

    // Driver program
    public static void main(String[] args)
    {
        String S = "geeks2for2";
        int K = 15;
        System.out.println(K_thletter(S, K));
    }
}

// This code is contributed by Rajput-Ji
```

## Python 3

```python
# Python3 implementation of above approach

# Function to return the K-th letter
# from new String.
def K_thletter(S, K):
    N = len(S)
    size = 0

    # finding size = length of new string S'
    for i in range(0, N):
        if S[i].isdigit():
            size = size * int(S[i])
        else:
            size += 1

    # get the K-th letter
    for i in range(N - 1, -1, -1):
        K %= size

        if K == 0 and S[i].isalpha():
            return S[i]

        if S[i].isdigit():
            size = size // int(S[i])
        else:
            size -= 1

# Driver Code
if __name__ == "__main__":
    S = "geeks2for2"
    K = 15

    print(K_thletter(S, K))

# This code is contributed by Rituraj Jain
```

## C#

```csharp
// C# implementation of the above approach
using System;

class GFG
{
    // Function to return the K-th letter from new String.
    static String K_thletter(String S, int K)
    {
        int N = S.Length;
        long size = 0;

        // finding size = length of new string S'
        for (int i = 0; i < N; ++i)
        {
            if (char.IsDigit(S[i]))
            {
                size = size * (S[i] - '0');
            }
            else
            {
                size += 1;
            }
        }

        // get the K-th letter
        for (int i = N - 1; i >= 0; --i)
        {
            K %= (int)size;
            if (K == 0 && char.IsLetter(S[i]))
            {
                return (String) "" + S[i];
            }

            if (char.IsDigit(S[i]))
            {
                size = size / (S[i] - '0');
            }
            else
            {
                size -= 1;
            }
        }
        return null;
    }

    // Driver code
    public static void Main(String[] args)
    {
        String S = "geeks2for2";
        int K = 15;
        Console.WriteLine(K_thletter(S, K));
    }
}

// This code has been contributed by 29AjayKumar
```

## JavaScript

```javascript
<script>
// Javascript implementation of above approach

function isAlphaNumeric(str) {
  var code, i, len;

  for (i = 0, len = str.length; i < len; i++) {
    code = str.charCodeAt(i);
    if (!(code > 47 && code < 58) && // numeric (0-9)
        !(code > 64 && code < 91) && // upper alpha (A-Z)
        !(code > 96 && code < 123)) { // lower alpha (a-z)
      return false;
    }
  }
  return true;
};

// Function to return the K-th letter from new String.
function K_thletter(S, K)
{
    var N = S.length;
    var size = 0;

    // finding size = length of new string S'
    for (var i = 0; i < N; ++i) {
        if (Number.isInteger(parseInt(S[i])))
            size = size * (S[i].charCodeAt(0) - '0'.charCodeAt(0));
        else
            size += 1;
    }

    // get the K-th letter
    for (var i = N - 1; i >= 0; --i) {
        K %= size;

        if (K == 0 && isAlphaNumeric(S[i]))
            return "" + S[i];

        if (Number.isInteger(parseInt(S[i])))
            size = size / (S[i].charCodeAt(0) - '0'.charCodeAt(0));
        else
            size -= 1;
    }
}

// Driver program
var S = "geeks2for2";
var K = 15;

document.write(K_thletter(S, K));

// This code is contributed by imporrtantly.
</script>
```

**输出:**

```
e
```

**时间复杂度:** `O(N)`，其中 `N` 是 `S` 的长度。