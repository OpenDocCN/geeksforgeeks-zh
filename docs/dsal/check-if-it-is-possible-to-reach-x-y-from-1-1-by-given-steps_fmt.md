# 检查是否可以通过给定的步骤

从`(1,1)`到达`(X,Y)`

> 原文: [https://www.geeksforgeeks.org/check-if-it-is-possible-to-reach-x-y-from-1-1-by-given-steps/](https://www.geeksforgeeks.org/check-if-it-is-possible-to-reach-x-y-from-1-1-by-given-steps/)

给定两个整数 `X` 和 `Y`，任务是检查是否有可能通过以下可能的移动从 `(1,1)` 到达 `(X,Y)`：

*   从点 `(a,b)` 移动到点 `(a, b-a)`。
*   从点 `(a,b)` 移动到点 `(a-b, b)`。
*   从任意点 `(a,b)` 移动到点 `(2 * a, b)` 或 `(a, 2 * b)`。

如果有可能到达 `(X,Y)`，打印“`Yes`”。否则，打印“`No`”。

**示例：**

> **输入:** `X = 4`, `Y = 7`
> **输出:** `Yes`
> **说明:** 点`(4,7)`可通过以下步骤到达：`(1,1) -> (1,2) -> (1,4) -> (1,8) -> (1,7) -> (2,7) -> (4,7)`
>
> **输入:** `X = 3`, `Y = 6`
> **输出:** `No`

**天真方法:** 解决问题最简单的方法是递归，通过从一个点开始做所有可能的移动，检查 `(1,1)` 是否可以从 `(X,Y)` 到达。如果在任一点到达 `(1,1)`，打印“`Yes`”。否则，打印“`No`”。

***时间复杂度:** `O(N^4)`，其中 `N` 是到达点`(1,1)`的步数。*
***辅助空间:** `O(1)`*

**高效法:** 思路是找到最大公约数并观察以下事实：

*   通过将点从 `(a,b)` 移动到点 `(a, b-a)` 或 `(a-b, b)`，该对的 GCD 没有变化。
*   通过将点从 `(a,b)` 移动到点 `(2 * a, b)` 或 `(a, 2 * b)`，GCD 可以翻倍或保持不变。
*   因此，从以上观察，点 `(1,1)` 可以移动到点 `(X,Y)` 当且仅当 `(X,Y)` 的 GCD 是 `2` 的幂。

按照以下步骤解决上述方法：

1.  找到 `(X,Y)` 的 GCD 并存储在变量中，比如 `val`。
2.  通过检查 `(val & (val-1))` 等于 `0`，其中 `&` 为位“与”运算符。
3.  如果是 `2` 的幂则打印“`Yes`”。否则，打印“`No`”。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the above approach
#include <iostream>
using namespace std;

// Function to find the gcd of
// two numbers
int gcd(int a, int b)
{

    // Base case
    if (a < b)
    {
        int t = a;
        a = b;
        b = t;
    }
    if (a % b == 0)
        return b;

    // Recurse
    return gcd(b, a % b);
}

// Function to print the answer
void printAnswer(int x, int y)
{

    // GCD of X and Y
    int val = gcd(x, y);

    // If GCD is power of 2
    if ((val & (val - 1)) == 0)
        cout << "Yes";
    else
        cout << "No";
}

// Driver code
int main()
{

    // Given X and Y
    int x = 4;
    int y = 7;

    // Function call
    printAnswer(x, y);

    return 0;
}

// This code is contributed by RohitOberoi
```

## Java

```java
// Java program for the above approach

import java.io.*;

class GFG {

    // Function to find the gcd of two numbers
    public static int gcd(int a, int b)
    {

        // Base case
        if (a < b) {
            int t = a;
            a = b;
            b = t;
        }
        if (a % b == 0)
            return b;

        // Recurse
        return gcd(b, a % b);
    }

    // Function to print the answer
    static void printAnswer(int x, int y)
    {

        // GCD of X and Y
        int val = gcd(x, y);

        // If GCD is power of 2
        if ((val & (val - 1)) == 0)
            System.out.println("Yes");
        else
            System.out.println("No");
    }

    // Driver code
    public static void main(String[] args)
    {

        // Given X and Y
        int x = 4;
        int y = 7;

        // Function call
        printAnswer(x, y);
    }
}
```

## Python 3

```python
# Python3 program for the
# above approach

# Function to find the gcd
# of two numbers
def gcd(a, b):

    # Base case
    if (a < b):

        t = a
        a = b
        b = t

    if (a % b == 0):
        return b

    # Recurse
    return gcd(b, a % b)

# Function to print the
# answer
def printAnswer(x, y):

    # GCD of X and Y
    val = gcd(x, y)

    # If GCD is power of 2
    if ((val &
        (val - 1)) == 0):
        print("Yes")
    else:
        print("No")

# Driver code
if __name__ == "__main__":

    # Given X and Y
    x = 4
    y = 7

    # Function call
    printAnswer(x, y)

# This code is contributed by Chitranayal
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to find the gcd of two numbers
public static int gcd(int a, int b)
{

    // Base case
    if (a < b)
    {
        int t = a;
        a = b;
        b = t;
    }
    if (a % b == 0)
        return b;

    // Recurse
    return gcd(b, a % b);
}

// Function to print the answer
static void printAnswer(int x, int y)
{

    // GCD of X and Y
    int val = gcd(x, y);

    // If GCD is power of 2
    if ((val & (val - 1)) == 0)
        Console.WriteLine("Yes");
    else
        Console.WriteLine("No");
}

// Driver code
public static void Main()
{

    // Given X and Y
    int x = 4;
    int y = 7;

    // Function call
    printAnswer(x, y);
}
}

// This code is contributed by bgangwar59
```

## JavaScript

```javascript
<script>
// JavaScript program for the above approach

// Function to find the gcd of
// two numbers
function gcd(a, b)
{

    // Base case
    if (a < b)
    {
        let t = a;
        a = b;
        b = t;
    }
    if (a % b == 0)
        return b;

    // Recurse
    return gcd(b, a % b);
}

// Function to print the answer
function printAnswer(x, y)
{

    // GCD of X and Y
    let val = gcd(x, y);

    // If GCD is power of 2
    if ((val & (val - 1)) == 0)
        document.write("Yes");
    else
        document.write("No");
}

// Driver code

    // Given X and Y
    let x = 4;
    let y = 7;

    // Function call
    printAnswer(x, y);

// This code is contributed by Surbhi Tyagi.
</script>
```

**Output:**

```
Yes
```

***时间复杂度:** `O(Log(min(X,Y)))`，其中`(X,Y)`是给定点。*
***辅助空间:** `O(1)`*