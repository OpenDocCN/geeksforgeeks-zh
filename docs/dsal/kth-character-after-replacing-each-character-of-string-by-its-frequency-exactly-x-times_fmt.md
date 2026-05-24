# 将字符串的每个字符替换为其频率正好为 X 倍后的第 k 个字符

> 原文: [https://www.geeksforgeeks.org/kth-character-after-replacing-each-character-of-string-by-its-frequency-exactly-x-times/](https://www.geeksforgeeks.org/kth-character-after-replacing-each-character-of-string-by-its-frequency-exactly-x-times/)

## 问题描述

给定一个由来自 `[1, 9]` 的 `N` 位和正整数 `K` 和 `X` 组成的字符串 `S`。每天，字符串的每个字符都被其频率和值替换。任务是在 `X` 天后找到字符串的第 `K` 个字符。

## 示例

**输入:** `S = "1214"`, `K = 10`, `X = 3`
**输出:** `4`
**解释:**
第 1 天 = `"12214444"`
第 2 天 = `"12222214444444444444444"`
第 3 天 = `"122222244444444444444444444444"`

**输入:** `S = "123"`, `K = 6`, `X = 2`
**输出:** `3`

## 方法

### 天真法

解决问题最简单的方法是通过将字符串数字 `X` 次中的数字相加来创建字符串，并找到字符串的第 `k` 个字符。

**时间复杂度:** `O(∑digit[i]^X)`，其中 `i` 的范围是 `[0, N-1]`。

### 有效方法

上述方法可以进一步优化，方法是不创建字符串，而是将 `digit^X` 添加到总和中，并检查 `sum` 是否 `>= K`。按照以下步骤解决问题:

*   初始化一个变量，比如说 `sum`，存储 `X` 天后字符串字符的总和。
*   初始化一个变量，比如说 `ans`，在 `X` 天之后存储第 `K` 个字符。
*   在范围 `[0, N-1]` 内迭代，执行以下步骤:
    *   将一个变量 `range` 初始化为 `(S[i] - '0')^X`，并将其添加到变量 `sum` 中。
    *   如果 `sum >= K`，返回 `S`，将 `ans` 修改为 `S[i]`，终止循环。
*   打印 `ans` 的值作为答案。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the Kth character
// after X days
char FindKthChar(string str, long long K, int X)
{

    // Variable to store the KthChar
    char ans;
    int sum = 0;

    // Traverse the string
    for (int i = 0; i < str.length(); i++) {

        // Convert char into int
        int digit = str[i] - '0';

        // Calculate characters
        int range = pow(digit, X);
        sum += range;

        // If K is less than sum
        // than ans = str[i]
        if (K <= sum) {
            ans = str[i];
            break;
        }
    }
    // Return answer
    return ans;
}

// Driver Code
int main()
{
    // Given Input
    string str = "123";
    long long K = 9;
    int X = 3;

    // Function Call
    char ans = FindKthChar(str, K, X);
    cout << ans << "\n";
    return 0;
}
```

### Java

```java
// Java program for the above approach
class GFG{

// Function to find the Kth character
// after X days
static char FindKthChar(String str, int K, int X)
{

    // Variable to store the KthChar
    char ans = ' ';
    int sum = 0;

    // Traverse the string
    for(int i = 0; i < str.length(); i++)
    {

        // Convert char into int
        int digit = (int)str.charAt(i) - 48;

        // Calculate characters
        int range = (int)Math.pow(digit, X);
        sum += range;

        // If K is less than sum
        // than ans = str[i]
        if (K <= sum)
        {
            ans = str.charAt(i);
            break;
        }
    }

    // Return answer
    return ans;
}

// Driver code
public static void main(String[] args)
{

    // Given Input
    String str = "123";
    int K = 9;
    int X = 3;

    // Function Call
    char ans = FindKthChar(str, K, X);
    System.out.println(ans);
}
}

// This code is contributed by abhinavjain194
```

### Python 3

```python
# Python3 program for the above approach
import math

# Function to find the Kth character
# after X days
def FindKthChar(Str, K, X):

    # Variable to store the KthChar
    ans = ' '
    Sum = 0

    # Traverse the string
    for i in range(len(Str)):

        # Convert char into int
        digit = ord(Str[i]) - 48

        # Calculate characters
        Range = int(math.pow(digit, X))
        Sum += Range

        # If K is less than sum
        # than ans = str[i]
        if (K <= Sum):
            ans = Str[i]
            break

    # Return answer
    return ans

# Given Input
Str = "123"
K = 9
X = 3

# Function Call
ans = FindKthChar(Str, K, X)
print(ans)

# This code is contributed by divyeshrabadiya07.
```

### C#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to find the Kth character
// after X days
static char FindKthChar(string str, int K, int X)
{

    // Variable to store the KthChar
    char ans = ' ';
    int sum = 0;

    // Traverse the string
    for(int i = 0; i < str.Length; i++)
    {

        // Convert char into int
        int digit = (int)str[i] - 48;

        // Calculate characters
        int range = (int)Math.Pow(digit, X);
        sum += range;

        // If K is less than sum
        // than ans = str[i]
        if (K <= sum)
        {
            ans = str[i];
            break;
        }
    }

    // Return answer
    return ans;
}

// Driver Code
public static void Main()
{

    // Given Input
    string str = "123";
    int K = 9;
    int X = 3;

    // Function Call
    char ans = FindKthChar(str, K, X);
    Console.Write(ans);
}
}

// This code is contributed by SURENDRA_GANGWAR
```

### JavaScript

```javascript
<script>
// javascript program for the above approach
// Function to find the Kth character
// after X days
function FindKthChar( str , K , X) {

    // Variable to store the KthChar
    var ans = "";
    var sum = 0;

    // Traverse the string
    for (i = 0; i < str.length; i++) {

        // Convert char into int
        var digit = parseInt( str[i]);

        // Calculate characters
        var range = parseInt( Math.pow(digit, X));
        sum += range;

        // If K is less than sum
        // than ans = str[i]
        if (K <= sum) {
            ans = str[i];
            break;
        }
    }

    // Return answer
    return ans;
}

// Driver code

// Given Input
var str = "123";
var K = 9;
var X = 3;

// Function Call
var ans = FindKthChar(str, K, X);
document.write(ans);

// This code contributed by gauravrajput1
</script>
```

**输出**

```
4
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`