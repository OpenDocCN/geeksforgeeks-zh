# 检查物体是否处于平衡状态的程序

> 原文: [https://www.geeksforgeeks.org/program-to-check-if-a-body-is-in-equilibrium-or-not/](https://www.geeksforgeeks.org/program-to-check-if-a-body-is-in-equilibrium-or-not/)

给定一个二维数组 `a[][]`，其中每一行由一个作用于物体的矢量坐标 `(x_i, y_i, z_i)` 组成。如果物体处于**平衡状态**，打印“`YES`”。否则，打印“`NO`”。

**示例:**

> **输入:** `a[][] = {{4, 1, 7}, {-2, 4, -1}, {1, -5, -3}}`
> **输出:** `NO`
>
> **输入:** `a[][] = {{3, -1, 7}, {-5, 2, -4}, {2, -1, -3}}`
> **输出:** `YES`

## 方法

按照以下步骤解决问题:

*   在所有矢量坐标上应用矢量加法。
*   如果向量相加的结果是 `(0, 0, 0)`，则物体处于**平衡**状态。因此，打印“`YES`”。
*   否则，打印“`NO`”。

下面是上述方法的实现:

### C++

```cpp
// C++ Program to implement
// the above approach
#include <iostream>
using namespace std;

// Function to calculate vector addition
void vectorAddition(int a[][3], int N)
{

    // Sum1 to store sum of xi
    // Sum2 to store sum of yi
    // Sum3 to store sum of zi
    int sum1 = 0, sum2 = 0, sum3 = 0;

    for (int i = 0; i < N; i++) {
        sum1 += a[i][0];
        sum2 += a[i][1];
        sum3 += a[i][2];
    }

    // If the sum1, sum2 and sum3
    // are all equal to zero
    if (sum1 == 0 && sum2 == 0
        && sum3 == 0) {

        // Body is in
        // equilibrium
        cout << "YES";
    }
    else {

        // Body is not in
        // equilibrium
        cout << "NO";
    }
}

// Driver Code
int main()
{
    int N = 3;

    int a[N][3]
        = { { 3, -1, 7 },
            { -5, 2, -4 },
            { 2, -1, -3 } };

    vectorAddition(a, N);

    return 0;
}
```

### Java

```java
// Java Program to implement
// the above approach
import java.util.*;
class GFG{

// Function to calculate
// vector addition
static void vectorAddition(int a[][],
                           int N)
{
  // Sum1 to store sum of xi
  // Sum2 to store sum of yi
  // Sum3 to store sum of zi
  int sum1 = 0, sum2 = 0, sum3 = 0;

  for (int i = 0; i < N; i++)
  {
    sum1 += a[i][0];
    sum2 += a[i][1];
    sum3 += a[i][2];
  }

  // If the sum1, sum2 and sum3
  // are all equal to zero
  if (sum1 == 0 && sum2 == 0 &&
      sum3 == 0)
  {
    // Body is in
    // equilibrium
    System.out.print("YES");
  }
  else
  {
    // Body is not in
    // equilibrium
    System.out.print("NO");
  }
}

// Driver Code
public static void main(String[] args)
{
  int N = 3;
  int a[][] = {{3, -1, 7},
               {-5, 2, -4},
               {2, -1, -3}};
  vectorAddition(a, N);
}
}

// This code is contributed by shikhasingrajput
```

### Python 3

```python
# Python3 program to implement
# the above approach

# Function to calculate vector addition
def vectorAddition(a, N):

    # Sum1 to store sum of xi
    # Sum2 to store sum of yi
    # Sum3 to store sum of zi
    sum1 = 0
    sum2 = 0
    sum3 = 0

    for i in range(N):
        sum1 += a[i][0]
        sum2 += a[i][1]
        sum3 += a[i][2]

    # If the sum1, sum2 and sum3
    # are all equal to zero
    if (sum1 == 0 and sum2 == 0 and
        sum3 == 0):

        # Body is in
        # equilibrium
        print("YES")

    else:

        # Body is not in
        # equilibrium
        print("NO")

# Driver Code
if __name__ == '__main__':

    N = 3
    a = [ [ 3, -1, 7 ],
          [ -5, 2, -4 ],
          [ 2, -1, -3 ] ]

    vectorAddition(a, N)

# This code is contributed by mohit kumar 29
```

### C#

```csharp
// C# Program to implement
// the above approach
using System;
class GFG{

// Function to calculate
// vector addition
static void vectorAddition(int[,]a,
                           int N)
{
  // Sum1 to store sum of xi
  // Sum2 to store sum of yi
  // Sum3 to store sum of zi
  int sum1 = 0, sum2 = 0, sum3 = 0;

  for (int i = 0; i < N; i++)
  {
    sum1 += a[i, 0];
    sum2 += a[i, 1];
    sum3 += a[i, 2];
  }

  // If the sum1, sum2 and sum3
  // are all equal to zero
  if (sum1 == 0 && sum2 == 0 &&
      sum3 == 0)
  {
    // Body is in
    // equilibrium
    Console.Write("YES");
  }
  else
  {
    // Body is not in
    // equilibrium
    Console.Write("NO");
  }
}

// Driver Code
public static void Main(String[] args)
{
  int N = 3;
  int[,]a = {{3, -1, 7},
             {-5, 2, -4},
             {2, -1, -3}};
  vectorAddition(a, N);
}
}

// This code is contributed by shikhasingrajput
```

### JavaScript

```javascript
<script>

// Javascript program for the above approach

// Function to calculate
// vector addition
function vectorAddition(a, N)
{
  // Sum1 to store sum of xi
  // Sum2 to store sum of yi
  // Sum3 to store sum of zi
  let sum1 = 0, sum2 = 0, sum3 = 0;

  for (let i = 0; i < N; i++)
  {
    sum1 += a[i][0];
    sum2 += a[i][1];
    sum3 += a[i][2];
  }

  // If the sum1, sum2 and sum3
  // are all equal to zero
  if (sum1 == 0 && sum2 == 0 &&
      sum3 == 0)
  {
    // Body is in
    // equilibrium
    document.write("YES");
  }
  else
  {
    // Body is not in
    // equilibrium
    document.write("NO");
  }
}

// Driver Code

  let N = 3;
  let a = [[3, -1, 7],
               [-5, 2, -4],
               [2, -1, -3]];
  vectorAddition(a, N);

</script>
```

**输出**

```
YES
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`