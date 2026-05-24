# 清空二进制字符串所需的连续相似字符的最小删除量

> 原文: [https://www.geeksforgeeks.org/minimum-removal-of-consecutive-similar-characters-required-to-empty-a-binary-string/](https://www.geeksforgeeks.org/minimum-removal-of-consecutive-similar-characters-required-to-empty-a-binary-string/)

给定长度为 `N` 的二进制字符串 `S`，任务是找到清空给定的二进制字符串所需的相邻相似字符的最小移除次数。

## 示例

**输入:** `S = "1100011"`
**输出:** 2
**解释:**
操作 1: 移除所有 `0` 将 `S` 修改为 `"1111"`。
操作 2: 移除所有剩余的 `1`，使 `S` 为空。
因此，所需的最小操作次数为 2。

**输入:** `S = "0010100"`
**输出:** 3
**解释:**
操作 1: 全 `1` 的移除将 `S` 修改为 `"000100"`。
操作 2: 移除全 `1` 修改 `S = "00000"`。
操作 3: 移除所有剩余的 `0` 使 `S` 为空。
因此，所需的最小操作次数为 3 次。

## 逼近方法

给定的问题可以用贪婪逼近来解决。其思想是以更高的频率删除字符的连续出现。按照以下步骤解决问题:

*   遍历给定的字符串 `S` 并生成一个新的字符串，比如 `newString`，方法是删除出现频率较高的连续字符。
*   最后，打印 `(sizeof(newString) + 1)/2` 作为所需答案。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find minimum steps
// to make the string empty
int minSteps(string S)
{
    // Stores the modified string
    string new_str;

    // Size of string
    int N = S.length();

    int i = 0;

    while (i < N) {

        new_str += S[i];

        // Removing substring of same
        // character from modified string
        int j = i;
        while (i < N && S[i] == S[j])
            ++i;
    }

    // Print the minimum steps required
    cout << ceil((new_str.size() + 1) / 2.0);
}

// Driver Code
int main()
{
    // Given string S
    string S = "0010100";

    // Function Call
    minSteps(S);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function to find minimum steps
// to make the String empty
static void minSteps(String S)
{

    // Stores the modified String
    String new_str = "";

    // Size of String
    int N = S.length();

    int i = 0;

    while (i < N)
    {
        new_str += S.charAt(i);

        // Removing subString of same
        // character from modified String
        int j = i;
        while (i < N && S.charAt(i) == S.charAt(j))
            ++i;
    }

    // Print the minimum steps required
    System.out.print((int)Math.ceil(
        (new_str.length() + 1) / 2.0));
}

// Driver Code
public static void main(String[] args)
{

    // Given String S
    String S = "0010100";

    // Function Call
    minSteps(S);
}
}

// This code is contributed by Princi Singh
```

### Python 3

```python
# Python3 program for the above approach
from math import ceil

# Function to find minimum steps
# to make the empty
def minSteps(S):

    # Stores the modified string
    new_str = ""

    # Size of string
    N = len(S)

    i = 0

    while (i < N):
        new_str += S[i]

        # Removing substring of same character
        # from modified string
        j = i
        while (i < N and S[i] == S[j]):
            i += 1

    # Print the minimum steps required
    print(ceil((len(new_str) + 1) / 2))

# Driver Code
if __name__ == '__main__':

    # Given S
    S = "0010100"

    # Function Call
    minSteps(S)

# This code is contributed by mohit kumar 29
```

### C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to find minimum steps
// to make the string empty
static void minSteps(string S)
{

    // Stores the modified string
    string new_str = "";

    // Size of string
    int N = S.Length;

    int i = 0;

    while (i < N)
    {
        new_str += S[i];

        // Removing substring of same
        // character from modified string
        int j = i;

        while (i < N && S[i] == S[j])
            ++i;
    }

    // Print the minimum steps required
    Console.Write((int)Math.Ceiling(
        (new_str.Length + 1) / 2.0));
}

// Driver Code
public static void Main()
{

    // Given string S
    string S = "0010100";

    // Function Call
    minSteps(S);
}
}

// This code is contributed by SURENDRA_GANGWAR
```

### JavaScript

```javascript
<script>
// Javascript program to implement
// the above approach

// Function to find minimum steps
// to make the string empty
function minSteps(S)
{

    // Stores the modified string
    let new_str = "";

    // Size of string
    let N = S.length;

    let i = 0;

    while (i < N)
    {
        new_str += S[i];

        // Removing substring of same
        // character from modified string
        let j = i;

        while (i < N && S[i] == S[j])
            ++i;
    }

    // Print the minimum steps required
    document.write(Math.ceil(
        (new_str.length + 1) / 2.0));
}

    // Driver Code

    // Given string S
    let S = "0010100";

    // Function Call
    minSteps(S)

</script>
```

**输出:**

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`