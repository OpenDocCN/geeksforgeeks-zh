# 检查给定的边长是否能形成直角三角形

> 原文: [https://www.geeksforgeeks.org/check-if-a-right-angled-triangle-can-be-formed-by-the-given-side-lengths/](https://www.geeksforgeeks.org/check-if-a-right-angled-triangle-can-be-formed-by-the-given-side-lengths/)

给定两个正整数 `A` 和 `B` 代表三角形的边，任务是检查给定的三角形两边是否是有效的直角三角形的边。如发现属实，打印“是”。否则，打印“否”。

**示例:**

> **输入:** `A = 3`，`B = 4`
> **输出:** 是
> **说明:** 边长为 3、4、5 的直角三角形是可能的。
>
> **输入:** `A = 2`，`B = 5`
> **输出:** 否

## 方法

按照以下步骤解决问题:

*   初始化一个变量，说 `checkTriangle` 检查给定的三角形两边是否是直角三角形的边。
*   检查 `B^2 + A^2` 的值是否为完全平方数。如果发现为真，则更新 `checkTriangle = true`。
*   否则，检查 `B^2 - A^2` 的值是否为完全平方数。如果发现为真，则更新 `checkTriangle = true`。
*   否则，检查 `A^2 - B^2` 的值是否为完全平方数。如果发现为真，则更新 `checkTriangle = true`。
*   最后，如果 `checkTriangle` 为 `true`，则打印“是”。否则，打印“否”。

下面是上述方法的实现:

## C++

```cpp
// C++ program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to check if N is a
// perfect square number or not
int checkPerfectSquare(int N)
{

    // If N is a non
    // positive integer
    if (N <= 0) {
        return 0;
    }

    // Stores square root
    // of N
    double sq = sqrt(N);

    // Check for perfect square
    if (floor(sq) == ceil(sq)) {
        return 1;
    }

    // If N is not a
    // perfect square number
    return 0;
}

// Function to check if given two sides of a
// triangle forms a right-angled triangle
bool checktwoSidesareRighTriangle(int A, int B)
{
    bool checkTriangle = false;

    // If the value of (A * A + B * B) is a
    // perfect square number
    if (checkPerfectSquare(A * A + B * B)) {

        // Update checkTriangle
        checkTriangle = true;
    }

    // If the value of (A * A - B * B) is a
    // perfect square number
    if (checkPerfectSquare(A * A - B * B)) {

        // Update checkTriangle
        checkTriangle = true;
    }

    // If the value of (B * B - A * A) is a
    // perfect square number
    if (checkPerfectSquare(B * B - A * A)) {

        // Update checkTriangle
        checkTriangle = true;
    }

    return checkTriangle;
}

// Driver Code
int main()
{
    int A = 3, B = 4;

    // If the given two sides of a triangle
    // forms a right-angled triangle
    if (checktwoSidesareRighTriangle(A, B)) {
        cout << "Yes";
    }

    // Otherwise
    else {
        cout << "No";
    }

    return 0;
}
```

## Java

```java
// Java program to implement
// the above approach
import java.io.*;
import java.util.*;

class GFG{

// Function to check if N is a
// perfect square number or not
static int checkPerfectSquare(int N)
{

    // If N is a non
    // positive integer
    if (N <= 0)
    {
        return 0;
    }

    // Stores square root
    // of N
    double sq = Math.sqrt(N);

    // Check for perfect square
    if (Math.floor(sq) == Math.ceil(sq))
    {
        return 1;
    }

    // If N is not a
    // perfect square number
    return 0;
}

// Function to check if given two sides of a
// triangle forms a right-angled triangle
static boolean checktwoSidesareRighTriangle(int A,
                                            int B)
{
    boolean checkTriangle = false;

    // If the value of (A * A + B * B) is a
    // perfect square number
    if (checkPerfectSquare(A * A + B * B) != 0)
    {

        // Update checkTriangle
        checkTriangle = true;
    }

    // If the value of (A * A - B * B) is a
    // perfect square number
    if (checkPerfectSquare(A * A - B * B) != 0)
    {

        // Update checkTriangle
        checkTriangle = true;
    }

    // If the value of (B * B - A * A) is a
    // perfect square number
    if (checkPerfectSquare(B * B - A * A) != 0)
    {

        // Update checkTriangle
        checkTriangle = true;
    }
    return checkTriangle;
}

// Driver Code
public static void main(String[] args)
{
    int A = 3, B = 4;

    // If the given two sides of a triangle
    // forms a right-angled triangle
    if (checktwoSidesareRighTriangle(A, B))
    {
        System.out.print("Yes");
    }

    // Otherwise
    else
    {
        System.out.print("No");
    }
}
}

// This code is contributed by susmitakundugoaldanga
```

## Python 3

```python
# Python3 program to implement
# the above approach
from math import sqrt, floor, ceil

# Function to check if N is a
# perfect square number or not
def checkPerfectSquare(N):

    # If N is a non
    # positive integer
    if (N <= 0):
        return 0

    # Stores square root
    # of N
    sq = sqrt(N)

    # Check for perfect square
    if (floor(sq) == ceil(sq)):
        return 1

    # If N is not a
    # perfect square number
    return 0

# Function to check if given two sides of a
# triangle forms a right-angled triangle
def checktwoSidesareRighTriangle(A, B):

    checkTriangle = False

    # If the value of (A * A + B * B) is a
    # perfect square number
    if (checkPerfectSquare(A * A + B * B)):

        # Update checkTriangle
        checkTriangle = True

    # If the value of (A * A - B * B) is a
    # perfect square number
    if (checkPerfectSquare(A * A - B * B)):

        # Update checkTriangle
        checkTriangle = True

    # If the value of (B * B - A * A) is a
    # perfect square number
    if (checkPerfectSquare(B * B - A * A)):

        # Update checkTriangle
        checkTriangle = True

    return checkTriangle

# Driver Code
if __name__ == '__main__':

    A = 3
    B = 4

    # If the given two sides of a triangle
    # forms a right-angled triangle
    if (checktwoSidesareRighTriangle(A, B)):
        print("Yes")

    # Otherwise
    else:
        print("No")

# This code is contributed by SURENDRA_GANGWAR
```

## C#

```csharp
// C# program to implement
// the above approach
using System;

class GFG{

// Function to check if N is a
// perfect square number or not
static int checkPerfectSquare(int N)
{

    // If N is a non
    // positive integer
    if (N <= 0)
    {
        return 0;
    }

    // Stores square root
    // of N
    double sq = Math.Sqrt(N);

    // Check for perfect square
    if (Math.Floor(sq) == Math.Ceiling(sq))
    {
        return 1;
    }

    // If N is not a
    // perfect square number
    return 0;
}

// Function to check if given two sides of a
// triangle forms a right-angled triangle
static bool checktwoSidesareRighTriangle(int A,
                                         int B)
{
    bool checkTriangle = false;

    // If the value of (A * A + B * B) is a
    // perfect square number
    if (checkPerfectSquare(A * A + B * B) != 0)
    {

        // Update checkTriangle
        checkTriangle = true;
    }

    // If the value of (A * A - B * B) is a
    // perfect square number
    if (checkPerfectSquare(A * A - B * B) != 0)
    {

        // Update checkTriangle
        checkTriangle = true;
    }

    // If the value of (B * B - A * A) is a
    // perfect square number
    if (checkPerfectSquare(B * B - A * A) != 0)
    {

        // Update checkTriangle
        checkTriangle = true;
    }
    return checkTriangle;
}

// Driver Code
public static void Main()
{
    int A = 3, B = 4;

    // If the given two sides of a triangle
    // forms a right-angled triangle
    if (checktwoSidesareRighTriangle(A, B))
    {
        Console.Write("Yes");
    }

    // Otherwise
    else
    {
        Console.Write("No");
    }
}
}

// This code is contributed by code_hunt
```

## java 描述语言

```
<script>
// Javascript program to implement
// the above approach

    // Function to check if N is a
    // perfect square number or not
    function checkPerfectSquare( N) {

        // If N is a non
        // positive integer
        if (N <= 0) {
            return 0;
        }

        // Stores square root
        // of N
        let sq = Math.sqrt(N);

        // Check for perfect square
        if (Math.floor(sq) == Math.ceil(sq)) {
            return 1;
        }

        // If N is not a
        // perfect square number
        return 0;
    }

    // Function to check if given two sides of a
    // triangle forms a right-angled triangle
    function checktwoSidesareRighTriangle( A , B) {
        let checkTriangle = false;

        // If the value of (A * A + B * B) is a
        // perfect square number
        if (checkPerfectSquare(A * A + B * B) != 0) {

            // Update checkTriangle
            checkTriangle = true;
        }

        // If the value of (A * A - B * B) is a
        // perfect square number
        if (checkPerfectSquare(A * A - B * B) != 0) {

            // Update checkTriangle
            checkTriangle = true;
        }

        // If the value of (B * B - A * A) is a
        // perfect square number
        if (checkPerfectSquare(B * B - A * A) != 0) {

            // Update checkTriangle
            checkTriangle = true;
        }
        return checkTriangle;
    }

    // Driver Code

    let A = 3, B = 4;

    // If the given two sides of a triangle
    // forms a right-angled triangle
    if (checktwoSidesareRighTriangle(A, B)) {
        document.write("Yes");
    }

    // Otherwise
    else {
        document.write("No");
    }

// This code is contributed by Rajput-Ji
</script>
```

`Output:`

```
Yes
```

`时间复杂度:` O(log(max(A，B))
`辅助空间:` O(1)