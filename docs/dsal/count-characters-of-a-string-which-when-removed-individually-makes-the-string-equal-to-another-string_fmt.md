# 计算一个字符串的字符数，当单独删除时，该字符串等于另一个字符串

> 原文：[https://www.geeksforgeeks.org/count-characters-of-a-string-which-when-removed-individually-makes-the-string-equal-to-another-string/](https://www.geeksforgeeks.org/count-characters-of-a-string-which-when-removed-individually-makes-the-string-equal-to-another-string/)

给定两个大小分别为 `N` 和 `M` 的[字符串](https://www.geeksforgeeks.org/strings-in-c-and-how-to-create-them/) `A` 和 `B`，任务是计算字符串 `A` 的字符数，当单独移除时，这两个字符串相等。如果有几个这样的字符，那么打印它们各自的位置。否则，打印 `-1`。

## 示例

**输入：** `A = "abaac"`, `B = "abac"`
**输出：**
```
2
3 4
```
**解释：**
以下移除是可能的，可以使字符串相等：
1.  移除 `A[2]` 会将 `A` 修改为 `"abac"`，这样就等于 `B`。
2.  移除 `A[3]` 会将 `A` 修改为 `"abac"`，这样就等于 `B`。

因此，两种可能的移除满足条件。

**输入：** `A = "abs"`, `B = "bkk"`
**输出：** `-1`

## 方法

给定的问题可以基于以下观察来解决：

-   假设如果删除索引 `i` 和 `j` 处的字符以使两个字符串相等，则字符串的前缀（即范围 `[0, i-1]` 内的子串）必须相等，并且字符串的后缀（即范围 `[j+1, n-1]` 内的子串）必须相等。
-   令 `i` 为满足范围 `[0, i-1]` 的最长相等前缀字符串的索引。令 `j` 满足范围 `[j+1, n-1]` 且该子串是最长的相等后缀字符串。
-   那么，如果 `i >= j`，则只有删除这些字符才能使两个字符串相等。并且单独删除后能使字符串相等的字符总数是 `i - j + 1`。

## 解决步骤

1.  初始化两个变量，`X` 表示为 `0`，`Y` 表示为 `N-1`，存储最长相等前缀串的结束索引和最长相等后缀串的开始索引。
2.  [迭代](https://www.geeksforgeeks.org/iterate-over-characters-of-a-string-in-c/)字符串 `B` 的字符，然后在每次迭代中检查当前字符是否等于字符串 `A` 的索引 `X` 处的字符，然后将 `X` 增加 `1`。否则，打破。
3.  [反向](https://www.geeksforgeeks.org/write-a-program-to-reverse-an-array-or-string/)中迭代字符串 `B` 的字符，然后在每次迭代中检查当前字符是否等于字符串 `A` 的索引 `Y` 处的字符，然后将 `Y` 递减 `1`。否则，打破。
4.  现在如果 `N` 和 `M` 的差值等于 `1` 和 `Y` 小于 `X` 那么：
    -   打印 `X - Y + 1` 等字符的总数。
    -   然后通过迭代范围 `[Y+1, X+1]` 打印字符的索引。
5.  否则，打印 `-1`。

## 实现

下面是上述方法的实现：

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to count characters
// from string A whose removal
// makes the strings A and B equal
void RemoveOneChar(string A, string B,
                   int N, int M)
{
    // Stores the index of
    // the longest prefix
    int X = 0;

    // Stores the index of
    // the longest suffix
    int Y = N - 1;

    // Traverse the string B
    for (int i = 0; i < M; i++) {
        if (A[X] != B[i])
            break;
        X++;
    }

    // Traverse the string B
    for (int i = M - 1; i >= 0; i--) {
        if (A[Y] != B[i])
            break;
        Y--;
    }
    // If N - M is equal to 1 and Y
    // is less than or equal to X
    if (N - M == 1 && Y < X) {

        // Print the count
        // of characters
        cout << X - Y + 1 << endl;

        // Print the positions
        // of the characters
        for (int i = Y; i <= X; i++)
            cout << i + 1 << " ";
        cout << endl;
    }

    // Otherwise
    else
        cout << -1 << endl;
}

// Driver Code
int main()
{

    string A = "abaac";
    string B = "abac";
    int N = A.length();
    int M = B.length();

    RemoveOneChar(A, B, N, M);
}
```

### Java

```java
// Java program for the above approach
class GFG{

// Function to count characters
// from string A whose removal
// makes the strings A and B equal
static void RemoveOneChar(String A, String B,
                          int N, int M)
{

    // Stores the index of
    // the longest prefix
    int X = 0;

    // Stores the index of
    // the longest suffix
    int Y = N - 1;

    // Traverse the string B
    for(int i = 0; i < M; i++)
    {
        if (A.charAt(X) != B.charAt(i))
            break;

        X++;
    }

    // Traverse the string B
    for(int i = M - 1; i >= 0; i--)
    {
        if (A.charAt(Y) != B.charAt(i))
            break;

        Y--;
    }

    // If N - M is equal to 1 and Y
    // is less than or equal to X
    if (N - M == 1 && Y < X)
    {

        // Print the count
        // of characters
        System.out.println(X - Y + 1);

        // Print the positions
        // of the characters
        for(int i = Y; i <= X; i++)
            System.out.print(i + 1 + " ");

        System.out.println();
    }

    // Otherwise
    else
        System.out.println(-1);
}

// Driver Code
static public void main(String []args)
{
    String A = "abaac";
    String B = "abac";
    int N = A.length();
    int M = B.length();

    RemoveOneChar(A, B, N, M);
}
}

// This code is contributed by AnkThon
```

### Python 3

```python
# Python3 program for the above approach

# Function to count characters
# from A whose removal
# makes the strings A and B equal
def RemoveOneChar(A, B, N, M):

    # Stores the index of
    # the longest prefix
    X = 0

    # Stores the index of
    # the longest suffix
    Y = N - 1

    # Traverse the B
    for i in range(M):
        if (A[X] != B[i]):
            break

        X += 1

    # Traverse the B
    for i in range(M - 1, -1, -1):
        if (A[Y] != B[i]):
            break

        Y -= 1

    # If N - M is equal to 1 and Y
    # is less than or equal to X
    if (N - M == 1 and Y < X):

        # Print count
        # of characters
        print(X - Y + 1)

        # Print positions
        # of the characters
        for i in range(Y, X + 1):
            print(i + 1, end = " ")

        print()

    # Otherwise
    else:
        print(-1)

# Driver Code
if __name__ == '__main__':

    A = "abaac"
    B = "abac"
    N = len(A)
    M = len(B)

    RemoveOneChar(A, B, N, M)

# This code is contributed by mohit kumar 29
```

### C\#

```csharp
// C# program for the above approach

using System;

public class GFG{

    // Function to count characters
    // from string A whose removal
    // makes the strings A and B equal
    static void RemoveOneChar(string A, string B,
                       int N, int M)
    {
        // Stores the index of
        // the longest prefix
        int X = 0;

        // Stores the index of
        // the longest suffix
        int Y = N - 1;

        // Traverse the string B
        for (int i = 0; i < M; i++) {
            if (A[X] != B[i])
                break;
            X++;
        }

        // Traverse the string B
        for (int i = M - 1; i >= 0; i--) {
            if (A[Y] != B[i])
                break;
            Y--;
        }
        // If N - M is equal to 1 and Y
        // is less than or equal to X
        if (N - M == 1 && Y < X) {

            // Print the count
            // of characters
            Console.WriteLine(X - Y + 1);

            // Print the positions
            // of the characters
            for (int i = Y; i <= X; i++)
                Console.Write(i + 1 + " ");
            Console.WriteLine();
        }

        // Otherwise
        else
            Console.WriteLine(-1) ;
    }

    // Driver Code
    static public void Main (){

        string A = "abaac";
        string B = "abac";
        int N = A.Length;
        int M = B.Length;

        RemoveOneChar(A, B, N, M);
    }
}

// This code is contributed by AnkThon
```

# java 描述语言

```javascript
// JavaScript program for the above approach

// Function to count characters
// from string A whose removal
// makes the strings A and B equal
function RemoveOneChar(A, B, N, M)
{
    // Stores the index of
    // the longest prefix
    var X = 0;

    // Stores the index of
    // the longest suffix
    var Y = N - 1;
    var i;
    // Traverse the string B
    for (i = 0; i < M; i++) {
        if (A[X] != B[i])
            break;
        X++;
    }

    // Traverse the string B
    for (i = M - 1; i >= 0; i--) {
        if (A[Y] != B[i])
            break;
        Y--;
    }
    // If N - M is equal to 1 and Y
    // is less than or equal to X
    if (N - M == 1 && Y < X) {

        // Print the count
        // of characters
        document.write(X - Y + 1 + "<br>");

        // Print the positions
        // of the characters
        for (i = Y; i <= X; i++)
            document.write(i + 1 +" ");
        document.write("\n");
    }

    // Otherwise
    else
        document.write(-1);
}

// Driver Code
    var A = "abaac";
    var B = "abac";
    var N = A.length;
    var M = B.length;

    RemoveOneChar(A, B, N, M);
```

**Output:**
```
3 4
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`