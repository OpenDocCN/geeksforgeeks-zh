# 可在矩形内接的最大三角形的高度

> 原文：[https://www.geeksforgeeks.org/altitude-of-largest-triangle-that-can-be-inscribed-in-a-rectangle/](https://www.geeksforgeeks.org/altitude-of-largest-triangle-that-can-be-inscribed-in-a-rectangle/)

给定一个长度为 `L` 和宽度为 `B` 的矩形，任务是打印可能的最大整数高度，这样三角形的高度应该等于底边的一半。

## 示例

> **输入:** `L = 3`，`B = 4`
> **输出:** 2
>
> **输入:** `L = 8`，`B = 9`
> **输出:** 4
>
> **输入:** `L = 325`，`B = 300`
> **输出:** 162

## 天真法

最简单的方法是反向迭代 `[0, min(L, B)]` 的范围，如果当前值小于等于 `max(L, B) / 2`，则打印当前值作为答案，打破循环。

**时间复杂度:** `O(min(L, B))`
**辅助空间:** `O(1)`

## 二分搜索法

上述方法可以通过使用二分搜索技术并观察选择矩形最大边长边上的三角形的底边总是最优的这一事实来优化。按照以下步骤解决问题：

*   如果 `L` 大于 `B`，则交换数值。
*   初始化三个变量，比如说，`low` 为 `0`，和 `high` 为 `L`。在范围 `[0, L]` 上执行二分搜索。
*   另外，初始化一个变量，说 `res` 为 `0` 来存储高度的最大可能长度。
*   当 `low` 小于或等于 `high` 时迭代，并执行以下步骤：
    *   初始化一个变量，说 `mid`，设置为 `low + (high - low) / 2`。
    *   如果 `mid <= B / 2` 的值，则将 `mid` 分配给 `res` 和 `mid + 1` 到 `low`。
    *   否则，将 `high` 设置为 `mid - 1`。
*   最后，完成上述步骤后，打印在 `res` 中获得的值。

下面是上述方法的实现：

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the greatest
// altitude of the largest triangle
// triangle that can be inscribed
// in the rectangle
int largestAltitude(int L, int B)
{
    // If L is greater than B
    if (L > B) {
        swap(B, L);
    }

    // Variables to perform binary
    // search
    int low = 0, high = L;

    // Stores the maximum altitude
    // possible
    int res = 0;

    // Iterate until low is less
    // than high
    while (low <= high) {

        // Stores the mid value
        int mid = low + (high - low) / 2;

        // If mide is less than
        // or equal to the B/2
        if (mid <= (B / 2)) {

            // Update res
            res = mid;

            // Update low
            low = mid + 1;
        }
        else

            // Update high
            high = mid - 1;
    }

    // Print the result
    return res;
}

// Driver Code
int main()
{
    // Given Input
    int L = 3;
    int B = 4;

    // Function call
    cout << largestAltitude(L, B);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;

class GFG {

// Function to find the greatest
// altitude of the largest triangle
// triangle that can be inscribed
// in the rectangle
static int largestAltitude(int L, int B)
{

    // If L is greater than B
    if (L > B)
    {
        int t = L;
        L = B;
        B = t;
    }

    // Variables to perform binary
    // search
    int low = 0, high = L;

    // Stores the maximum altitude
    // possible
    int res = 0;

    // Iterate until low is less
    // than high
    while (low <= high)
    {

        // Stores the mid value
        int mid = low + (high - low) / 2;

        // If mide is less than
        // or equal to the B/2
        if (mid <= (B / 2))
        {

            // Update res
            res = mid;

            // Update low
            low = mid + 1;
        }
        else

            // Update high
            high = mid - 1;
    }

    // Print the result
    return res;
}

// Driver Code
public static void main(String[] args)
{
     // Given Input
    int L = 3;
    int B = 4;

    // Function call
    System.out.print(largestAltitude(L, B));
}
}

// This code is contributed by splevel62.
```

### Python 3

```python
# Python 3 program for the above approach

# Function to find the greatest
# altitude of the largest triangle
# triangle that can be inscribed
# in the rectangle
def largestAltitude(L, B):

    # If L is greater than B
    if (L > B):
        temp = B
        B = L
        L = temp

    # Variables to perform binary
    # search
    low = 0
    high = L

    # Stores the maximum altitude
    # possible
    res = 0

    # Iterate until low is less
    # than high
    while (low <= high):
        # Stores the mid value
        mid = low + (high - low) // 2

        # If mide is less than
        # or equal to the B/2
        if (mid <= (B / 2)):
            # Update res
            res = mid

            # Update low
            low = mid + 1

        else:
            # Update high
            high = mid - 1

    # Print the result
    return res

# Driver Code
if __name__ == '__main__':

    # Given Input
    L = 3
    B = 4

    # Function call
    print(largestAltitude(L, B))

    # This ode is contributed by ipg2016107.
```

### C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to find the greatest
// altitude of the largest triangle
// triangle that can be inscribed
// in the rectangle
static int largestAltitude(int L, int B)
{

    // If L is greater than B
    if (L > B)
    {
        int t = L;
        L = B;
        B = t;
    }

    // Variables to perform binary
    // search
    int low = 0, high = L;

    // Stores the maximum altitude
    // possible
    int res = 0;

    // Iterate until low is less
    // than high
    while (low <= high)
    {

        // Stores the mid value
        int mid = low + (high - low) / 2;

        // If mide is less than
        // or equal to the B/2
        if (mid <= (B / 2))
        {

            // Update res
            res = mid;

            // Update low
            low = mid + 1;
        }
        else

            // Update high
            high = mid - 1;
    }

    // Print the result
    return res;
}

// Driver Code
public static void Main(string[] args)
{

    // Given Input
    int L = 3;
    int B = 4;

    // Function call
    Console.Write(largestAltitude(L, B));
}
}

// This code is contributed by code_hunt
```

### JavaScript

```javascript
<script>

// JavaScript program for the above approach

// Function to find the greatest
// altitude of the largest triangle
// triangle that can be inscribed
// in the rectangle
function largestAltitude(L, B) {
  // If L is greater than B
  if (L > B) {
    let temp = B;
    B = L;
    L = temp;
  }

  // Variables to perform binary
  // search
  let low = 0,
    high = L;

  // Stores the maximum altitude
  // possible
  let res = 0;

  // Iterate until low is less
  // than high
  while (low <= high) {
    // Stores the mid value
    let mid = Math.floor(low + (high - low) / 2);

    // If mide is less than
    // or equal to the B/2
    if (mid <= Math.floor(B / 2)) {
      // Update res
      res = mid;

      // Update low
      low = mid + 1;
    }

    // Update high
    else high = mid - 1;
  }

  // Print the result
  return res;
}

// Driver Code

// Given Input
let L = 3;
let B = 4;

// Function call
document.write(largestAltitude(L, B));

</script>
```

**输出**

```
2
```

**时间复杂度:** `O(log(min(L, B)))`
**辅助空间:** `O(1)`

## 高效方法

通过观察将三角形的底边放在长度的边上，`max(L, B)` 高度将等于 `min(max(L, B) / 2, min(L, B))`，可以进一步优化上述方法。按照以下步骤解决问题：

下面是上述方法的实现：

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the greatest
// altitude of the largest triangle
// triangle that can be inscribed
// in the rectangle
int largestAltitude(int L, int B)
{
    // If L is greater than B
    if (L > B)
        swap(L, B);
    // Stores the maximum altitude
    // value
    int res = min(B / 2, L);

    // Return res
    return res;
}

// Driver Code
int main()
{
    // Given Input
    int L = 3;
    int B = 4;

    // Function call
    cout << largestAltitude(L, B);

    return 0;
}
```

## Java 语言

```java
// C++ program for the above approach
import java.io.*;
class GFG
{

// Function to find the greatest
// altitude of the largest triangle
// triangle that can be inscribed
// in the rectangle
static int largestAltitude(int L, int B)
{

    // If L is greater than B
    if (L > B)
        {
        int t = L;
        L = B;
        B = t;
    }

    // Stores the maximum altitude
    // value
    int res = Math.min(B / 2, L);

    // Return res
    return res;
}

// Driver Code
public static void main(String[] args)
{

    // Given Input
    int L = 3;
    int B = 4;

    // Function call
    System.out.print( largestAltitude(L, B));
}
}

// This code is contributed by shivanisinghss2110
```

## 蟒蛇 3

```python
# Python program for the above approach
# Function to find the greatest
# altitude of the largest triangle
# triangle that can be inscribed
# in the rectangle
def largestAltitude( L,  B):

    # If L is greater than B
    if (L > B):
        temp = B
        B = L
        L = temp
    # Stores the maximum altitude
    # value
    res = min(B // 2, L)

    # Return res
    return res

# Driver Code
# Given Input
L = 3
B = 4

# Function call
print(largestAltitude(L, B))

# This code is contributed by shivanisinghss2110
```

## C\#

```csharp
// C# program for the above approach
using System;
class GFG
{

// Function to find the greatest
// altitude of the largest triangle
// triangle that can be inscribed
// in the rectangle
static int largestAltitude(int L, int B)
{

    // If L is greater than B
    if (L > B)
        {
        int t = L;
        L = B;
        B = t;
    }

    // Stores the maximum altitude
    // value
    int res = Math.Min(B / 2, L);

    // Return res
    return res;
}

// Driver Code
public static void Main(String[] args)
{

    // Given Input
    int L = 3;
    int B = 4;

    // Function call
    Console.Write( largestAltitude(L, B));
}
}

// This code is contributed by shivanisinghss2110
```

## JavaScript

```javascript
<script>
// JavaScript program for the above approach
// Function to find the greatest
// altitude of the largest triangle
// triangle that can be inscribed
// in the rectangle
function largestAltitude(L, B)
{

    // If L is greater than B
    if (L > B)
        {
        var t = L;
        L = B;
        B = t;
    }

    // Stores the maximum altitude
    // value
    var res = Math.min(B / 2, L);

    // Return res
    return res;
}

// Driver Code
    // Given Input
    var L = 3;
    var B = 4;

    // Function call
    document.write( largestAltitude(L, B));

// This code is contributed by shivanisinghss2110
</script>
```

### Output

`时间复杂度:` O(1)
`辅助空间:` O(1)