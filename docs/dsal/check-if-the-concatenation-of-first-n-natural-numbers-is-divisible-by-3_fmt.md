# 检查前 N 个自然数的连接是否能被 3 整除

> 原文: [https://www.geeksforgeeks.org/check-if-the-concatenation-of-first-n-natural-numbers-is-divisible-by-3/](https://www.geeksforgeeks.org/check-if-the-concatenation-of-first-n-natural-numbers-is-divisible-by-3/)

给定一个整数 `N`，任务是检查前 `N` 个自然数的连接是否可以被 3 整除。如果可整除则打印 `Yes`，否则打印 `No`。

## 示例

**输入**：`N = 3`
**输出**：`Yes`
**说明**：连接后的数字是 `123`。由于 `123` 能被 3 整除，所以输出为 `Yes`。

**输入**：`N = 7`
**输出**：`No`
**说明**：连接后的数字是 `1234567`。由于 `1234567` 不能被 3 整除，所以输出为 `No`。

## 天真法

最简单的方法是将前 `N` 个自然数串联起来，计算结果数的各位数字之和，然后检查是否能被 3 整除。

- **时间复杂度**：`O(N)`
- **辅助空间**：`O(1)`

## 高效方法

为了优化上述方法，我们可以观察到一个模式。对于序列 `1, 4, 7, 10, 13, 16, 19, ...`，前 `N` 个自然数的连接不能被 3 整除。该序列的第 `N` 项由公式 `3×n + 1` 给出。因此，如果 `(N - 1)` 不能被 `3` 整除，那么结果数可以被 3 整除，所以打印 `Yes`。否则，打印 `No`。

以下是实现上述方法的代码：

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>

using namespace std;

// Function that returns True if
// concatenation of first N natural
// numbers is divisible by 3
bool isDivisible(int N)
{
    // Check using the formula
    return (N - 1) % 3 != 0;
}

// Driver Code
int main()
{
    // Given Number
    int N = 6;

    // Function Call
    if (isDivisible(N))
        cout << ("Yes");

    else
        cout << ("No");

    return 0;
}

// This code is contributed by Mohit Kumar
```

### Java

```java
// Java program for the above approach
class GFG{

// Function that returns True if
// concatenation of first N natural
// numbers is divisible by 3
static boolean isDivisible(int N)
{
    // Check using the formula
    return (N - 1) % 3 != 0;
}

// Driver Code
public static void main(String[] args)
{
    // Given Number
    int N = 6;

    // Function Call
    if (isDivisible(N))
        System.out.println("Yes");

    else
        System.out.println("No");
}
}

// This code is contributed by Ritik Bansal
```

### Python 3

```python
# Python program for the above approach

# Function that returns True if
# concatenation of first N natural
# numbers is divisible by 3
def isDivisible(N):

    # Check using the formula
    return (N - 1) % 3 != 0

# Driver Code
if __name__ == "__main__":

    # Given Number
    N = 6

    # Function Call
    if (isDivisible(N)):
        print("Yes")

    else:
        print("No")
```

### C#

```csharp
// C# program for the above approach
using System;
class GFG{

// Function that returns True if
// concatenation of first N natural
// numbers is divisible by 3
static bool isDivisible(int N)
{
    // Check using the formula
    return (N - 1) % 3 != 0;
}

// Driver Code
public static void Main()
{
    // Given Number
    int N = 6;

    // Function Call
    if (isDivisible(N))
        Console.Write("Yes");

    else
        Console.Write("No");
}
}

// This code is contributed by Code_Mech
```

### JavaScript

```javascript
<script>
// javascript program for the above approach

// Function that returns True if
// concatenation of first N natural
// numbers is divisible by 3
function isDivisible(N)
{
    // Check using the formula
    return (N - 1) % 3 != 0;
}

// Driver Code

// Given Number
var N = 6;

// Function Call
if (isDivisible(N))
    document.write("Yes");
else
    document.write("No");

// This code is contributed by Princi Singh.
</script>
```

**输出**：

```
Yes
```

- **时间复杂度**：`O(1)`
- **辅助空间**：`O(1)`