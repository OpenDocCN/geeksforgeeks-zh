# 检查二次方程的一根是否是另一根的两倍

> 原文: [https://www.geeksforgeeks.org/check-whether-one-root-of-the-quadratic-equation-is-twice-of-other-or-not/](https://www.geeksforgeeks.org/check-whether-one-root-of-the-quadratic-equation-is-twice-of-other-or-not/)

给定三个数字 `A`，`B`，`C`，代表一个二次方程 $Ax^{2} + Bx + C = 0$ 的系数（常数），任务是检查由这些常数代表的方程的一个根是否是另一个的两倍。

**示例:**

> **输入:** `A = 1`，`B = -3`，`C = 2`
> **输出:** 是
> **说明:**
> 给定的二次方程是 $x^{2} - 3x + 2 = 0$。
> 它的根是 (1，2)。$2 = 2 * 1$。
>
> **输入:** `A = 1`，`B = -5`，`C = 6`
> **输出:** No
> **解释:**
> 给定的二次方程是 $x^{2} - 5x + 6 = 0$。
> 它的根是 (2，3)。$3 \ne 2 * 2$ 或 $2 \ne 2 * 3$。

**做法:** 思路是用二次根的概念来解决问题。我们可以通过以下步骤来表达检查一个根是否是另一个根的两倍所需的条件：

1.  根之和 = $\alpha + 2*\alpha = 3\alpha$。该值等于：
    > $\frac{-b}{a}$

2.  同样，根的乘积 = $\alpha * 2*\alpha = 2\alpha^2$。该值等于：
    > $\frac{c}{a}$

3.  我们可以解上面两个方程 $3 * \alpha = \frac{-b}{a}$ 和 $2 * \alpha^2 = \frac{c}{a}$ 得到条件：
    > $2b^2 = 9 * a * c$

4.  因此，为了使根的第一个假设成立，上述条件需要成立。因此，对于给定的系数，我们简单地检查上述条件是否成立。

以下是上述方法的实现：

## C++

```cpp
// C++ program to check if one root
// of a Quadratic Equation is
// twice of other or not

#include <iostream>
using namespace std;

// Function to find the required answer
void checkSolution(int a, int b, int c)
{
    if (2 * b * b == 9 * a * c)
        cout << "Yes";
    else
        cout << "No";
}

// Driver code
int main()
{
    int a = 1, b = 3, c = 2;

    checkSolution(a, b, c);

    return 0;
}
```

## Java

```java
// Java program to check if one root
// of a quadratic equation is
// twice of other or not
class GFG{

// Function to find the required answer
static void checkSolution(int a, int b, int c)
{
    if (2 * b * b == 9 * a * c)
        System.out.print("Yes");
    else
        System.out.print("No");
}

// Driver Code
public static void main(String[] args)
{
    int a = 1, b = 3, c = 2;

    checkSolution(a, b, c);
}
}

// This code is contributed by shubham
```

## Python 3

```python
# Python3 program to check if one root
# of a Quadratic Equation is
# twice of other or not

# Function to find the required answer
def checkSolution(a, b, c):

    if (2 * b * b == 9 * a * c):
        print("Yes");
    else:
        print("No");

# Driver code
a = 1; b = 3; c = 2;
checkSolution(a, b, c);

# This code is contributed by Code_Mech
```

## C#

```csharp
// C# program to check if one root
// of a quadratic equation is
// twice of other or not
using System;

class GFG{

// Function to find the required answer
static void checkSolution(int a, int b, int c)
{
    if (2 * b * b == 9 * a * c)
        Console.Write("Yes");
    else
        Console.Write("No");
}

// Driver Code
public static void Main(String[] args)
{
    int a = 1, b = 3, c = 2;

    checkSolution(a, b, c);
}
}

// This code is contributed by shubham
```

## JavaScript

```javascript
// JavaScript program to check if one root
// of a quadratic equation is
// twice of other or not

// Function to find the required answer
function checkSolution(a, b, c)
{
    if (2 * b * b == 9 * a * c)
        document.write("Yes");
    else
        document.write("No");
}

// Driver code
let a = 1, b = 3, c = 2;

checkSolution(a, b, c);

// This code is contributed by avanitrachhadiya2158
```

**输出:**

```
Yes
```

**时间复杂度:** O(1)

**辅助空间:** O(1)