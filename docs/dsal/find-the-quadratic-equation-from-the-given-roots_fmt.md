# 从给定的根求二次方程

> 原文：`https://www.geeksforgeeks.org/find-the-quadratic-equation-from-the-given-roots/`

给定一个二次方程 `A` 和 `B` 的根，任务是找到方程。
**注**：给定的根是整数。

**示例：**

> **输入：** `A = 2, B = 3`
> **输出：**
> `x^2 –( 5x)+(6)= 0`
> `x^2–5x+6 = 0`
> `x^2-3x-2x+6 = 0`
> `x(x–3)–2(x–3)= 0`
> `(x–3)(x–2)= 0`
> `x = 2, 3`
>
> **输入：** `A = 5, B = 10`
> **输出：** `x^2 –( 15x)+(50)= 0`

**逼近：** 如果一个二次方程 `ax^2 + bx + c = 0` 的根是 `A` 和 `B`，那么已知 `A+B = –b/a` 和 `A * B = c/a`。
现在，`ax^2 + bx + c = 0` 可以写成
`x^2+(b/a)x+(c/a)= 0` (自，`a != 0`)
`x^2–(A+B)x +(A * B)= 0` (自，`A + B = -b/a` 和 `A * B = c/a`)
即 **`x^2–(根之和)x+根之积= 0`**

下面是上述方法的实现：

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the quadratic
// equation whose roots are a and b
void findEquation(int a, int b)
{
    int sum = (a + b);
    int product = (a * b);
    cout << "x^2 - (" << sum << "x) + ("
         << product << ") = 0";
}

// Driver code
int main()
{
    int a = 2, b = 3;

    findEquation(a, b);

    return 0;
}
```

## Java

```java
// Java implementation of the above approach
class GFG
{

    // Function to find the quadratic
    // equation whose roots are a and b
    static void findEquation(int a, int b)
    {
        int sum = (a + b);
        int product = (a * b);
        System.out.println("x^2 - (" + sum +
                           "x) + (" + product + ") = 0");
    }

    // Driver code
    public static void main(String args[])
    {
        int a = 2, b = 3;

        findEquation(a, b);
    }
}

// This code is contributed by AnkitRai01
```

## Python 3

```python
# Python3 implementation of the approach

# Function to find the quadratic
# equation whose roots are a and b
def findEquation(a, b):
    summ = (a + b)
    product = (a * b)
    print("x^2 - (", summ,
          "x) + (", product, ") = 0")

# Driver code
a = 2
b = 3

findEquation(a, b)

# This code is contributed by Mohit Kumar
```

## C#

```csharp
// C# implementation of the above approach
using System;
class GFG
{

    // Function to find the quadratic
    // equation whose roots are a and b
    static void findEquation(int a, int b)
    {
        int sum = (a + b);
        int product = (a * b);
        Console.WriteLine("x^2 - (" + sum +
                          "x) + (" + product + ") = 0");
    }

    // Driver code
    public static void Main()
    {
        int a = 2, b = 3;

        findEquation(a, b);
    }
}

// This code is contributed by CodeMech.
```

## JavaScript

```javascript
<script>

// Javascript implementation of the above approach

// Function to find the quadratic
// equation whose roots are a and b
function findEquation(a, b)
{
    var sum = (a + b);
    var product = (a * b);
    document.write("x^2 - (" + sum +
                    "x) + (" + product +
                    ") = 0");
}

// Driver Code
var a = 2, b = 3;

findEquation(a, b);

// This code is contributed by Ankita saini

</script>
```

**Output：**

```
x^2 - (5x) + (6) = 0
```