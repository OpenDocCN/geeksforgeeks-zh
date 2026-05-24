# 检查数字在B进制下是否为回文

> 原文：[https://www.geeksforgeeks.org/check-if-number-is-palindrome-or-not-in-base-b/](https://www.geeksforgeeks.org/check-if-number-is-palindrome-or-not-in-base-b/)

给定一个整数 `N`，任务是检查 `N_B`（`N` 在 `B` 进制下）是不是[回文](https://www.geeksforgeeks.org/check-if-a-number-is-palindrome/)。

**示例：**

> **输入：** `N = 5`，`B = 2`
> **输出：** 是
> **解释：**
> `(5)_10 = (101)_2`，这是回文。因此，所需的输出是“是”。
> **输入：** `N = 4`，`B = 2`
> **输出：** 否

**方法：** 这个问题可以通过检查十进制值的逆序 `N_B` 是否等于 `N` 来解决。按照以下步骤解决问题。

1.  初始化变量 `rev = 0`，用于存储 `N` 的倒数。
2.  通过 `N % B` 提取 `N_B` 的每一位数字。
3.  对于 `N_B` 的每一位数字：
    *   更新 `rev = rev * B + N % B`。
4.  最后，检查 `N` 是否等于 `rev`。

以下是上述方法的实现：

## C++

```cpp
// C++ program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to check if N in
// base B is palindrome or not
int checkPalindromeB(int N, int B)
{
    // Stores the reverse of N
    int rev = 0;

    // Stores the value of N
    int N1 = N;

    // Extract all the digits of N
    while (N1) {
        // Generate its reverse
        rev = rev * B + N1 % B;
        N1 = N1 / B;
    }

    return N == rev;
}

// Driver Code
int main()
{
    int N = 5, B = 2;
    if (checkPalindromeB(N, B)) {
        cout << "Yes";
    }
    else {
        cout << "No";
    }
}
```

## Java

```java
// Java program to implement
// the above approach
class GFG{

// Function to check if N in
// base B is palindrome or not
static boolean checkPalindromeB(int N,
                                int B)
{

    // Stores the reverse of N
    int rev = 0;

    // Stores the value of N
    int N1 = N;

    // Extract all the digits of N
    while (N1 > 0)
    {

        // Generate its reverse
        rev = rev * B + N1 % B;
        N1 = N1 / B;
    }
    return N == rev;
}

// Driver code
public static void main(String[] args)
{
    int N = 5, B = 2;

    if (checkPalindromeB(N, B))
    {
        System.out.print("Yes");
    }
    else
    {
        System.out.print("No");
    }
}
}

// This code is contributed by Dewanti
```

## Python 3

```python
# Python3 program to implement
# the above approach

# Function to check if N in
# base B is palindrome or not
def checkPalindromeB(N, B):

    # Stores the reverse of N
    rev = 0;

    # Stores the value of N
    N1 = N;

    # Extract all the digits of N
    while (N1 > 0):

        # Generate its reverse
        rev = rev * B + N1 % B;
        N1 = N1 // B;

    return N == rev;

# Driver code
if __name__ == '__main__':
    N = 5; B = 2;

    if (checkPalindromeB(N, B)):
        print("Yes");
    else:
        print("No");

# This code is contributed by Princi Singh
```

## C#

```csharp
// C# program to implement
// the above approach
using System;

class GFG{

// Function to check if N in
// base B is palindrome or not
static bool checkPalindromeB(int N,
                             int B)
{

    // Stores the reverse of N
    int rev = 0;

    // Stores the value of N
    int N1 = N;

    // Extract all the digits of N
    while (N1 > 0)
    {

        // Generate its reverse
        rev = rev * B + N1 % B;
        N1 = N1 / B;
    }
    return N == rev;
}

// Driver code
public static void Main(String[] args)
{
    int N = 5, B = 2;

    if (checkPalindromeB(N, B))
    {
        Console.Write("Yes");
    }
    else
    {
        Console.Write("No");
    }
}
}

// This code is contributed by Amit Katiyar
```

## JavaScript

```javascript
<script>

// Javascript program to implement
// the above approach

// Function to check if N in
// base B is palindrome or not
function checkPalindromeB(N, B)
{
    // Stores the reverse of N
    var rev = 0;

    // Stores the value of N
    var N1 = N;

    // Extract all the digits of N
    while (N1) {
        // Generate its reverse
        rev = rev * B + N1 % B;
        N1 = parseInt(N1 / B);
    }

    return N == rev;
}

// Driver Code
var N = 5, B = 2;
if (checkPalindromeB(N, B)) {
    document.write("Yes");
}
else {
    document.write("No");
}

</script>
```

**输出：**

```
Yes
```

**时间复杂度：** `O(log_B N)`
**辅助空间：** `O(1)`