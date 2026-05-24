# 计算矢量大小的程序

> 原文: [https://www.geeksforgeeks.org/program-to-find-the-magnitude-of-a-vector/](https://www.geeksforgeeks.org/program-to-find-the-magnitude-of-a-vector/)

给定三个整数代表一个三维向量的坐标，任务是找出该向量的大小。

**示例:**

> **输入:** `X = 1`，`Y = 2`，`Z = 2`
> **输出:** 3
> **说明:** 矢量大小等于√9 = 3
>
> **输入:** `X = 0`，`Y = 4`，`Z = 3`
> **输出:** 5

**逼近:** 矢量的大小可以通过解方程 **√(X²+Y²+Z²)** 来计算。按照以下步骤解决问题:

*   将 `X`，`Y` 和 `Z` 坐标的平方和存储在一个变量中，比如说 `sum`。
*   初始化一个变量，说 `magnitude`，到存储 `sum` 的平方根。
*   打印 `magnitude` 的值作为所需结果。

下面是上述方法的实现:

## C++14

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to calculate magnitude
// of a 3 dimensional vector
float vectorMagnitude(int x, int y, int z)
{
    // Stores the sum of squares
    // of coordinates of a vector
    int sum = x * x + y * y + z * z;

    // Return the magnitude
    return sqrt(sum);
}

// Driver Code
int main()
{
    int x = 1;
    int y = 2;
    int z = 3;

    cout << vectorMagnitude(x, y, z);

    return 0;
}
```

## Java

```java
// Java program for the above approach
class GFG{

// Function to calculate magnitude
// of a 3 dimensional vector
private static double vectorMagnitude(int x, int y,
                                      int z)
{

    // Stores the sum of squares
    // of coordinates of a vector
    int sum = x * x + y * y + z * z;

    // Return the magnitude
    return Math.sqrt(sum);
}

// Driver code
public static void main(String[] args)
{
    int x = 1;
    int y = 2;
    int z = 3;

    System.out.print(vectorMagnitude(x, y, z));
}
}

// This code is contributed by abhinavjain194
```

## Python 3

```python
# Python3 program for the above approach
from math import sqrt

# Function to calculate magnitude
# of a 3 dimensional vector
def vectorMagnitude(x, y, z):

    # Stores the sum of squares
    # of coordinates of a vector
    sum = x * x + y * y + z * z

    # Return the magnitude
    return sqrt(sum)

# Driver code
x = 1
y = 2
z = 3

print(vectorMagnitude(x, y, z))

# This code is contributed by abhinavjain194
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to calculate magnitude
// of a 3 dimensional vector
private static double vectorMagnitude(int x, int y,
                                      int z)
{

    // Stores the sum of squares
    // of coordinates of a vector
    int sum = x * x + y * y + z * z;

    // Return the magnitude
    return Math.Sqrt(sum);
}

// Driver code
static void Main()
{
    int x = 1;
    int y = 2;
    int z = 3;

    Console.Write(vectorMagnitude(x, y, z));
}
}

// This code is contributed by abhinavjain194
```

## JavaScript

```javascript
<script>

// Javascript program for the above approach

// Function to calculate magnitude
// of a 3 dimensional vector
function vectorMagnitude(x, y, z)
{

    // Stores the sum of squares
    // of coordinates of a vector
    var sum = x * x + y * y + z * z;

    // Return the magnitude
    return Math.sqrt(sum);
}

// Driver Code
var x = 1;
var y = 2;
var z = 3;

document.write(vectorMagnitude(x, y, z));

// This code is contributed by Ankita saini

</script>
```

**Output:**

```
3.74166
```

**时间复杂度:** O(1)
**辅助空间:** O(1)