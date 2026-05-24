# 由给定的根形成三次方程

> 原文: [https://www.geeksforgeeks.org/form-the-cubic-equation-from-the-given-roots/](https://www.geeksforgeeks.org/form-the-cubic-equation-from-the-given-roots/)

给定三次方程的根 `A`、`B` 和 `C`，任务是从给定的根形成三次方程。
**注:** 给定的根是整数。

**举例:**

> **输入:** `A = 1`，`B = 2`，`C = 3`
> **输出:** `x^3–6x^2+11x–6 = 0`
> **解释:**
> 由于 1、2 和 3 是三次方程的根，那么方程由下式给出:
> `(x–1)(x–2)(x–3)= 0`
> `(x–1)(x^2–5x+6)= 0`
> `x^3–5x^2+6x–x^2+5x–6 = 0`

> **输入:** `A = 5`，`B = 2`，`C = 3`
> **输出:** `x^3–10x^2+31x–30 = 0`
> **解释:**
> 由于 5、2 和 3 是三次方程的根，那么方程由下式给出:
> `(x–5)(x–2)(x–3)= 0`
> `(x–5)(x^2–5x+6)= 0`
> `x^3–5x^2`

**逼近:** 让三次方程的根 (`ax^3+bx^2+cx+d = 0`) 为 `A`、`B`、`C`，那么给定的三次方程可以表示为:

> `ax^3+bx^2+cx+d = x^3-(a+b+c)x^2+(ab+bc+ca)x-a*b*c = 0`。
> 令 `X = (a+b+c)`
> `Y = (ab+bc+ca)`
> `Z = a * b * c`

因此利用上述关系求出 `X`、`Y` 和 `Z` 的值，形成所需的三次方程。
以下是上述方法的实现:

## C++

```cpp
// C++ program for the approach

#include <bits/stdc++.h>
using namespace std;

// Function to find the cubic
// equation whose roots are a, b and c
void findEquation(int a, int b, int c)
{
    // Find the value of coefficient
    int X = (a + b + c);
    int Y = (a * b) + (b * c) + (c * a);
    int Z = a * b * c;

    // Print the equation as per the
    // above coefficients
    cout << "x^3 - " << X << "x^2 + "
         << Y << "x - " << Z << " = 0";
}

// Driver Code
int main()
{
    int a = 5, b = 2, c = 3;

    // Function Call
    findEquation(a, b, c);
    return 0;
}
```

## Java

```java
// Java program for the approach

class GFG{

// Function to find the cubic equation
// whose roots are a, b and c
static void findEquation(int a, int b, int c)
{
    // Find the value of coefficient
    int X = (a + b + c);
    int Y = (a * b) + (b * c) + (c * a);
    int Z = a * b * c;

    // Print the equation as per the
    // above coefficients
    System.out.print("x^3 - " + X+ "x^2 + "
                  + Y+ "x - " + Z+ " = 0");
}

// Driver Code
public static void main(String[] args)
{
    int a = 5, b = 2, c = 3;

    // Function Call
    findEquation(a, b, c);
}
}

// This code contributed by PrinciRaj1992
```

## Python 3

```python
# Python3 program for the approach

# Function to find the cubic equation
# whose roots are a, b and c
def findEquation(a, b, c):

    # Find the value of coefficient
    X = (a + b + c);
    Y = (a * b) + (b * c) + (c * a);
    Z = (a * b * c);

    # Print the equation as per the
    # above coefficients
    print("x^3 - " , X ,
          "x^2 + " ,Y ,
          "x - " , Z , " = 0");

# Driver Code
if __name__ == '__main__':

    a = 5;
    b = 2;
    c = 3;

    # Function Call
    findEquation(a, b, c);

# This code is contributed by sapnasingh4991
```

## C#

```csharp
// C# program for the approach
using System;

class GFG{

// Function to find the cubic equation
// whose roots are a, b and c
static void findEquation(int a, int b, int c)
{

    // Find the value of coefficient
    int X = (a + b + c);
    int Y = (a * b) + (b * c) + (c * a);
    int Z = a * b * c;

    // Print the equation as per the
    // above coefficients
    Console.Write("x^3 - " + X +
                  "x^2 + " + Y +
                    "x - " + Z + " = 0");
}

// Driver Code
public static void Main()
{
    int a = 5, b = 2, c = 3;

    // Function Call
    findEquation(a, b, c);
}
}

// This code is contributed by shivanisinghss2110
```

## JavaScript

```javascript
<script>

    // Javascript program for the approach

    // Function to find the cubic
    // equation whose roots are a, b and c
    function findEquation(a, b, c)
    {
        // Find the value of coefficient
        let X = (a + b + c);
        let Y = (a * b) + (b * c) + (c * a);
        let Z = a * b * c;

        // Print the equation as per the
        // above coefficients
        document.write("x^3 - " + X + "x^2 + "
             + Y + "x - " + Z + " = 0");
    }

    let a = 5, b = 2, c = 3;

    // Function Call
    findEquation(a, b, c);

</script>
```

**Output:**

```
x^3 - 10x^2 + 31x - 30 = 0
```

时间复杂度: O(1)

辅助空间: O(1)