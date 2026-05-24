# 五角星数

> 哎哎哎:# t0]https://www . geeksforgeeks . org/pentcontenhanagon-number/

**五角星数**是一类图形数。它有一个 51 边的多边形，叫做五角星。第 `N` 个五角星数计数是 51 个点的数量，所有其他点被一个共同的共享角包围并形成一个图案。
前几个五角星数是:

> 1，51，150，298，…

### 寻找第 n 个五角星数的程序

给定一个数字 `N`，任务是找到第 `N` 个五角星数。

**举例:**

> **输入:** `N = 2`
> **输出:** 51
> **说明:**
> 第二个五角星数为 51。
> **输入:** `N = 3`
> **输出:** 150

**方法:** 第 `N` 个五角星数由公式给出:

*   `S` 边多边形的第 `n` 项 = ![\frac{((S - 2)N^{2} - (S - 4)N)}{2}](img/06979e276f01f9c5a63c01dedda1d5b1.png "Rendered by QuickLaTeX.com")
*   因此 51 边多边形的第 `N` 项由给出

> ![Tn =\frac{((51 - 2)N^{2} - (51 - 4)N)}{2} =\frac{(49N^{2} - 47N)}{2}](img/9de15163e4c0f815c26e6e9c7cfc095c.png "Rendered by QuickLaTeX.com")

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the N-th
// Pentacontahenagon Number
int PentacontahenagonNum(int N)
{
    return (49 * N * N - 47 * N)
        / 2;
}

// Driver Code
int main()
{
    int N = 3;

// Function Call
    cout << "3rd Pentacontahenagon Number is "
        << PentacontahenagonNum(N);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.*;
class GFG{

// Function to find the N-th
// Pentacontahenagon Number
static int PentacontahenagonNum(int N)
{
    return (49 * N * N - 47 * N) / 2;
}

// Driver Code
public static void main(String[] args)
{
    int N = 3;

    // Function Call
    System.out.print("3rd Pentacontahenagon Number is " +
                                PentacontahenagonNum(N));
}
}

// This code is contributed by Rajput-Ji
```

## Python 3

```python
# Python3 program for the above approach

# Function to find the N-th
# Pentacontahenagon Number
def PentacontahenagonNum(N):

    return (49 * N * N - 47 * N) // 2;

# Driver Code
N = 3;

# Function Call
print("3rd Pentacontahenagon Number is",
               PentacontahenagonNum(N));

# This code is contributed by Code_Mech
```

## C#

```csharp
// C# program for the above approach
using System;
class GFG{

// Function to find the N-th
// Pentacontahenagon Number
static int PentacontahenagonNum(int N)
{
    return (49 * N * N - 47 * N) / 2;
}

// Driver Code
public static void Main()
{
    int N = 3;

    // Function Call
    Console.Write("3rd Pentacontahenagon Number is " +
                         PentacontahenagonNum(N));
}
}

// This code is contributed by Code_Mech
```

## JavaScript

```javascript
<script>
// Javascript program for the above approach

    // Function to find the N-th
    // Pentacontahenagon Number
    function PentacontahenagonNum( N) {
        return (49 * N * N - 47 * N) / 2;
    }

    // Driver Code

        let N = 3;

        // Function Call
        document.write("3rd Pentacontahenagon Number is " + PentacontahenagonNum(N));

// This code is contributed by aashish1995
</script>
```

**输出:**

```
3rd Pentacontahenagon Number is 150
```