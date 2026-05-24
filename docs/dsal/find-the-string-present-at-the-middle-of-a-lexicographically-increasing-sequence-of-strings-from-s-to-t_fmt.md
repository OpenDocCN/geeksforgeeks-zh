# 找出出现在从 S 到 T 的按字典顺序递增的字符串序列中间的字符串

> 原文: [https://www.geeksforgeeks.org/find-the-string-present-at-the-middle-of-a-lexicographically-increasing-sequence-of-strings-from-s-to-t/](https://www.geeksforgeeks.org/find-the-string-present-at-the-middle-of-a-lexicographically-increasing-sequence-of-strings-from-s-to-t/)

假设两个字符串 `S` 和 `T`，`S` 在字典顺序上大于 `T`，任务是生成从 `S` 到 `T`（*两者都包含*）的字典顺序递增的字符串序列，并打印出现在序列中间的字符串。
**注：** 在按字典顺序递增的序列中，总会有奇数个字符串。

**示例：**

> **输入：** `N = 2`，`S = "az"`，`T = "bf"`
> **输出：** `bc`
> **解释：** 字符串的字典顺序递增顺序为 "az"、"ba"、"bb"、"bc"、"bd"、"be"、"bf"。中间的字符串是 "bc"。
>
> **输入：** `S = "afogk"`，`T = "asdji"`
> **输出：** `aluw`

## 方法

按照以下步骤解决问题：

*   每一个字符串都可以用 `[0, 26]` 之间的整数表示在基数 26 中。
*   如果字符串表示两个整数 `L` 和 `R`，那么结果将是 `(L + R) / 2`，这将是中间的数字。
*   使用类似的概念，字符串可以用基数为 26 的数字来表示。
*   "az" 等字符串可以表示为 `(0, 25)_26`，"bf" 可以表示为 `(1, 5)_26`；和 "" 可以表示为 `()_26`。
*   将字符串转换为各自的基数 26 后，获得它们的按位求和。
*   将从右向左迭代的位相加，并将余数结转到下一个位置。
*   `(0, 25)_26`、`(1, 5)_26` 相加为 `(2, 4)_26`。
*   取每个位置值的中间，打印相应的字符。如果位置是奇数，则将下一个位置移动 26 个字符。

> **插图：**
>
> `S = "afogk"`，`T = "asdji"`
>
> *   `S = [0, 5, 14, 6, 10]` 的 26 个基本表示
> *   `T = [0, 18, 3, 9, 8]` 的 26 个基数表示
> *   字符串 `S` 和 `T` 的加法 = `[0, 23, 17, 15, 18]`
> *   `(S + T) / 2 = [0, 11, 21, 20, 22]` 的中间字符串表示
> *   因此，字符串中的每个字符都将是基于 0 的索引中 "a" 的第 `a[i]` 个字符

**下面是上述方法的实现：**

### C++

```cpp
// C++ Program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to print the string at
// the middle of lexicographically
// increasing sequence of strings from S to T
int printMiddleString(string S, string T, int N)
{
    // Stores the base 26 digits after addition
    vector<int> a1(N + 1);

    for (int i = 0; i < N; i++) {
        a1[i + 1] = S[i] - 'a' + T[i] - 'a';
    }

    // Iterete from right to left
    // and add carry to next position
    for (int i = N; i >= 1; i--) {
        a1[i - 1] += a1[i] / 26;
        a1[i] %= 26;
    }

    // Reduce the number to find the middle
    // string by dividing each position by 2
    for (int i = 0; i <= N; i++) {

        // If current value is odd,
        // carry 26 to the next index value
        if (a1[i] & 1) {

            if (i + 1 <= N) {
                a1[i + 1] += 26;
            }
        }

        a1[i] /= 2;
    }

    for (int i = 1; i <= N; i++) {
        cout << char(a1[i] + 'a');
    }
    return 0;
}

// Driver Code
int main()
{
    int N = 5;
    string S = "afogk";
    string T = "asdji";
    printMiddleString(S, T, N);
}
```

### Java

```java
// Java Program for the above approach
import java.util.*;

class GFG {

    // Function to print the string at
    // the middle of lexicographically
    // increasing sequence of strings from S to T
    static void printMiddleString(String S, String T, int N)
    {
        // Stores the base 26 digits after addition
        int[] a1 = new int[N + 1];

        for (int i = 0; i < N; i++) {
            a1[i + 1] = (int)S.charAt(i) - 97
                        + (int)T.charAt(i) - 97;
        }

        // Iterete from right to left
        // and add carry to next position
        for (int i = N; i >= 1; i--) {
            a1[i - 1] += (int)a1[i] / 26;
            a1[i] %= 26;
        }

        // Reduce the number to find the middle
        // string by dividing each position by 2
        for (int i = 0; i <= N; i++) {

            // If current value is odd,
            // carry 26 to the next index value
            if ((a1[i] & 1) != 0) {

                if (i + 1 <= N) {
                    a1[i + 1] += 26;
                }
            }

            a1[i] = (int)a1[i] / 2;
        }

        for (int i = 1; i <= N; i++) {
            System.out.print((char)(a1[i] + 97));
        }
    }

    // Driver Code
    public static void main(String[] args)
    {
        int N = 5;
        String S = "afogk";
        String T = "asdji";
        printMiddleString(S, T, N);
    }
}

// This code is contributed by ukasp.
```

### Python 3

```python
# Python Program for the above approach

# Function to print the string at
# the middle of lexicographically
# increasing sequence of strings from S to T
def printMiddleString(S, T, N):

  # Stores the base 26 digits after addition
  a1 = [0] * (N + 1);

  for i in range(N):
    a1[i + 1] = ord(S[i]) - ord("a") + ord(T[i]) - ord("a");

  # Iterete from right to left
  # and add carry to next position
  for i in range(N, 1, -1):
    a1[i - 1] += a1[i] // 26;
    a1[i] %= 26;

  # Reduce the number to find the middle
  # string by dividing each position by 2
  for i in range(N+1):
    # If current value is odd,
    # carry 26 to the next index value
    if (a1[i] & 1):
      if (i + 1 <= N):
        a1[i + 1] += 26;

    a1[i] = a1[i] // 2;

  for i in range(1, N + 1):
    print(chr(a1[i] + ord("a")), end="");

  return 0;

# Driver Code
N = 5;
S = "afogk";
T = "asdji";
printMiddleString(S, T, N);

# This code is contributed by gfgking
```

### C\#

```csharp
// C# Program for the above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to print the string at
// the middle of lexicographically
// increasing sequence of strings from S to T
static void printMiddleString(string S, string T, int N)
{
    // Stores the base 26 digits after addition
    int []a1 = new int[N + 1];

    for (int i = 0; i < N; i++) {
        a1[i + 1] = (int)S[i] - 97 + (int)T[i] - 97;
    }

    // Iterete from right to left
    // and add carry to next position
    for (int i = N; i >= 1; i--) {
        a1[i - 1] += (int)a1[i] / 26;
        a1[i] %= 26;
    }

    // Reduce the number to find the middle
    // string by dividing each position by 2
    for (int i = 0; i <= N; i++) {

        // If current value is odd,
        // carry 26 to the next index value
        if ((a1[i] & 1)!=0) {

            if (i + 1 <= N) {
                a1[i + 1] += 26;
            }
        }

        a1[i] = (int)a1[i]/2;
    }

    for (int i = 1; i <= N; i++) {
        Console.Write(Convert.ToChar(a1[i] + 'a'));
    }

}

// Driver Code
public static void Main()
{
    int N = 5;
    string S = "afogk";
    string T = "asdji";
    printMiddleString(S, T, N);
}
}

// This code is contributed by ipg2016107.
```

### JavaScript

```javascript
<script>
// Javascript Program for the above approach

// Function to print the string at
// the middle of lexicographically
// increasing sequence of strings from S to T
function printMiddleString(S, T, N) {
  // Stores the base 26 digits after addition
  let a1 = new Array(N + 1);

  for (let i = 0; i < N; i++) {
    a1[i + 1] = S[i].charCodeAt(0) - "a".charCodeAt(0) + T[i].charCodeAt(0) - "a".charCodeAt(0);
  }

  // Iterete from right to left
  // and add carry to next position
  for (let i = N; i >= 1; i--) {
    a1[i - 1] += a1[i] / 26;
    a1[i] %= 26;
  }

  // Reduce the number to find the middle
  // string by dividing each position by 2
  for (let i = 0; i <= N; i++) {
    // If current value is odd,
    // carry 26 to the next index value
    if (a1[i] & 1) {
      if (i + 1 <= N) {
        a1[i + 1] += 26;
      }
    }

    a1[i] = Math.floor(a1[i] / 2);
  }

  for (let i = 1; i <= N; i++) {
    document.write(String.fromCharCode(a1[i] + "a".charCodeAt(0)));
  }
  return 0;
}

// Driver Code
let N = 5;
let S = "afogk";
let T = "asdji";
printMiddleString(S, T, N);

// This code is contributed by _saurabh_jaiswal.
</script>
```

**输出：**

```
aluw
```

**时间复杂度：** `O(N)`
**辅助空间：** `O(N)`