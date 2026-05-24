# 检查给定点是否位于任何给定塔的范围内

> 原文: [https://www.geeksforgeeks.org/check-if-given-point-lies-in-range-of-any-of-the-given-towers/](https://www.geeksforgeeks.org/check-if-given-point-lies-in-range-of-any-of-the-given-towers/)

给定由形式为 `{X_i, Y_i, R_i}` 的 `N` 行组成的 2D 数组 `arr[][]`，使得 `(X_i, Y_i)` 代表塔的位置而 `R_i` 代表其范围。给定两个整数 `X` 和 `Y`，任务是检查点 `(X, Y)` 是否在塔的网络范围内。

## 示例

> **输入:** `arr[][] = { {1, 1, 3}, {10, 10, 5}, {15, 15, 15} }`, `X = 5`, `Y = 5`
> **输出:** 真
> **说明:**
> 点 `(5, 5)` 与 `(arr[0][0], arr[0][1])` 的距离 = 5.65685，第一塔的范围为 3。因此，点 `(X, Y)` 不在第一个塔的网络范围内。
> 点 `(5, 5)` 与 `(arr[1][0], arr[1][1])` 的距离 = 7.07107，二塔范围为 5。因此，点 `(X, Y)` 不在第二塔的网络范围内。
> 点 `(5, 5)` 与 `(arr[2][0], arr[2][1])` 的距离 = 14.1421，三塔范围为 15。因此，点 `(X, Y)` 位于第三塔的网络范围内。
> 由于，点 `(X, Y)` 位于第三塔范围内。因此，所需的输出为真。
>
> **输入:** `arr[][] = { {1, 1, 3}, {10, 10, 3}, {15, 15, 3} }`, `X = 5`, `Y = 5`
> **输出:** 假

## 方法

按照下面给出的步骤解决问题:

*   遍历数组，对于遍历的每一行(塔)，检查 `sqrt((arr[i][0] - X)^2 + (arr[i][1] - Y)^2)` 的值是否大于 `arr[i][2]`。如果发现为真，则打印 `真`。
*   否则，打印 `假`。

## C++

```cpp
// C++ program to implement
// the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to check if the point (X, Y)
// exists in the towers network-range or not
bool checkPointRange(int arr[][3], int X,
                     int Y, int N)
{

    // Traverse the array arr[]
    for (int i = 0; i < N; i++) {

        // Stores distance of the
        // point (X, Y) from i-th tower
        double dist
            = sqrt((arr[i][0] - X) * (arr[i][0] - X)
                   + (arr[i][1] - Y) * (arr[i][1] - Y));

        // If dist lies within the
        // range of the i-th tower
        if (dist <= arr[i][2]) {
            return true;
        }
    }

    // If the point (X, Y) does not lie
    // in the range of any of the towers
    return false;
}

// Driver Code
int main()
{

    int arr[][3] = { { 1, 1, 3 },
                     { 10, 10, 3 },
                     { 15, 15, 15 } };
    int X = 5, Y = 5;

    int N = sizeof(arr) / sizeof(arr[0]);

    // If point (X, Y) lies in the
    // range of any of the towers
    if (checkPointRange(arr, X, Y, N)) {
        cout << "True";
    }
    // Otherwise
    else {
        cout << "False";
    }
}
```

## Java

```java
// Java program to implement
// the above approach
import java.util.*;

class GFG{

// Function to check if the point (X, Y)
// exists in the towers network-range or not
static boolean checkPointRange(int arr[][], int X,
                               int Y, int N)
{

    // Traverse the array arr[]
    for(int i = 0; i < N; i++)
    {

        // Stores distance of the
        // point (X, Y) from i-th tower
        double dist = Math.sqrt((arr[i][0] - X) *
                                (arr[i][0] - X) +
                                (arr[i][1] - Y) *
                                (arr[i][1] - Y));

        // If dist lies within the
        // range of the i-th tower
        if (dist <= arr[i][2])
        {
            return true;
        }
    }

    // If the point (X, Y) does not lie
    // in the range of any of the towers
    return false;
}

// Driver Code
public static void main(String[] args)
{
    int arr[][] = { { 1, 1, 3 },
                    { 10, 10, 3 },
                    { 15, 15, 15 } };
    int X = 5, Y = 5;

    int N = arr.length;

    // If point (X, Y) lies in the
    // range of any of the towers
    if (checkPointRange(arr, X, Y, N))
    {
        System.out.print("True");
    }

    // Otherwise
    else
    {
        System.out.print("False");
    }
}
}

// This code is contributed by code_hunt
```

## Python 3

```python
# Python3 program to implement
# the above approach
from math import sqrt

# Function to check if the point (X, Y)
# exists in the towers network-range or not
def checkPointRange(arr, X, Y, N):

    # Traverse the array arr[]
    for i in range(N):

        # Stores distance of the
        # point (X, Y) from i-th tower
        dist = sqrt((arr[i][0] - X) *
                    (arr[i][0] - X) +
                    (arr[i][1] - Y) *
                    (arr[i][1] - Y))

        # If dist lies within the
        # range of the i-th tower
        if (dist <= arr[i][2]):
            return True

    # If the point (X, Y) does not lie
    # in the range of any of the towers
    return False

# Driver Code
if __name__ == '__main__':

    arr = [ [ 1, 1, 3 ],
            [ 10, 10, 3 ],
            [ 15, 15, 15 ] ]
    X = 5
    Y = 5

    N = len(arr)

    # If point (X, Y) lies in the
    # range of any of the towers
    if (checkPointRange(arr, X, Y, N)):
        print("True")

    # Otherwise
    else:
        print("False")

# This code is contributed by bgangwar59
```

## C#

```csharp
// C# program to implement
// the above approach
using System;

class GFG{

// Function to check if the point (X, Y)
// exists in the towers network-range or not
static bool checkPointRange(int[,] arr, int X,
                            int Y, int N)
{

    // Traverse the array arr[]
    for(int i = 0; i < N; i++)
    {

        // Stores distance of the
        // point (X, Y) from i-th tower
        double dist = Math.Sqrt((arr[i, 0] - X) *
                                (arr[i, 0] - X) +
                                (arr[i, 1] - Y) *
                                (arr[i, 1] - Y));

        // If dist lies within the
        // range of the i-th tower
        if (dist <= arr[i, 2])
        {
            return true;
        }
    }

    // If the point (X, Y) does not lie
    // in the range of any of the towers
    return false;
}

// Driver Code
public static void Main()
{
    int[,] arr = { { 1, 1, 3 },
                   { 10, 10, 3 },
                   { 15, 15, 15 } };

    int X = 5, Y = 5;

    int N = arr.Length;

    // If point (X, Y) lies in the
    // range of any of the towers
    if (checkPointRange(arr, X, Y, N))
    {
        Console.Write("True");
    }

    // Otherwise
    else
    {
        Console.Write("False");
    }
}
}

// This code is contributed by susmitakundugoaldanga
```

## JavaScript

```javascript
<script>

// JavaScript program to implement
// the above approach

// Function to check if the point (X, Y)
// exists in the towers network-range or not
function checkPointRange(arr, X, Y, N)
{

    // Traverse the array arr[]
    for(let i = 0; i < N; i++)
    {

        // Stores distance of the
        // point (X, Y) from i-th tower
        let dist = Math.sqrt((arr[i][0] - X) *
                                (arr[i][0] - X) +
                                (arr[i][1] - Y) *
                                (arr[i][1] - Y));

        // If dist lies within the
        // range of the i-th tower
        if (dist <= arr[i][2])
        {
            return true;
        }
    }

    // If the point (X, Y) does not lie
    // in the range of any of the towers
    return false;
}

// Driver Code

    let arr = [[ 1, 1, 3 ],
               [ 10, 10, 3 ],
              [ 15, 15, 15 ]];
    let X = 5, Y = 5;

    let N = arr.length;

    // If point (X, Y) lies in the
    // range of any of the towers
    if (checkPointRange(arr, X, Y, N))
    {
        document.write("True");
    }

    // Otherwise
    else
    {
        document.write("False");
    }

</script>
```

**输出:**

```
True
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`