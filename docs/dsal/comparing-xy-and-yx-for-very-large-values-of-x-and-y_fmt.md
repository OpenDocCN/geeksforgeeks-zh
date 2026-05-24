# 比较 X^Y 和 Y^X 非常大的 x 和 y 值

> 原文: [https://www.geeksforgeeks.org/comparing-xy-and-yx-for-very-large-values-of-x-and-y/](https://www.geeksforgeeks.org/comparing-xy-and-yx-for-very-large-values-of-x-and-y/)

给定两个整数 `X` 和 `Y`，任务是比较 `X^Y` 和 `Y^X` 的值，适用于非常大的 `X` 和 `Y`。

**示例:**

> **输入:** `X = 2`，`Y = 3`
> **输出:** `2^3 < 3^2`
> **解释:** `2^3 = 8`，`3^2 = 9`，所以 `8 < 9`。
>
> **输入:** `X = 4`，`Y = 5`
> **输出:** `4^5 > 5^4`
> **解释:** `4^5 = 1024`，`5^4 = 625`，所以 `1024 > 625`。

**天真的方法:** 一个基本的方法是找到值 `X^Y` 和 `Y^X` 并比较它们，因为 `X` 和 `Y` 的值可能很大。

**更好的方法:** 取两个方程的对数，`log(X^Y) = Y * log(X)` 和 `log(Y^X) = X * log(Y)`。现在，这些值可以很容易地进行比较，而不会溢出。

以下是上述办法的实现:

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to compare x^y and y^x
void compareVal(int x, int y)
{
    // Storing values OF x^y AND y^x
    long double a = y * log(x);
    long double b = x * log(y);

    // Comparing values
    if (a > b)
        cout << x << "^" << y << " > "
             << y << "^" << x;

    else if (a < b)
        cout << x << "^" << y << " < "
             << y << "^" << x;

    else if (a == b)
        cout << x << "^" << y << " = "
             << y << "^" << x;
}

// Driver code
int main()
{
    long double x = 4, y = 5;

    compareVal(x, y);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
import java.util.*;

class GFG
{
    // Function to compare x^y and y^x
    static void compareVal(int x, int y)
    {
        // Storing values OF x^y AND y^x
        double a = y * Math.log(x);
        double b = x * Math.log(y);

        // Comparing values
        if (a > b)
            System.out.print(x + "^" + y + " > " +
                             y + "^" + x);

        else if (a < b)
            System.out.print(x + "^" + y + " < " +
                             y + "^" + x);

        else if (a == b)
            System.out.print(x + "^" + y + " = " +
                             y + "^" + x );
    }

    // Driver code
    public static void main(String[] args)
    {
        int x = 4, y = 5;

        compareVal(x, y);
    }
}

// This code is contributed by 29AjayKumar
```

## Python 3

```python
# Python3 implementation of the approach
from math import log

# Function to compare x^y and y^x
def compareVal(x, y) :
    # Storing values OF x^y AND y^x
    a = y * log(x);
    b = x * log(y);

    # Comparing values
    if (a > b) :
        print(x, "^", y, ">", y, "^", x);

    elif (a < b) :
        print(x, "^", y, "<", y ,"^", x);

    elif (a == b) :
        print(x, "^", y, "=", y, "^", x);

# Driver code
if __name__ == "__main__" :
    x = 4; y = 5;

    compareVal(x, y);

# This code is contributed by AnkitRai01
```

## C#

```csharp
// C# implementation of the approach
using System;
class GFG
{
    // Function to compare x^y and y^x
    static void compareVal(double x, double y)
    {
        // Storing values OF x^y AND y^x
        double a = y * Math.Log(x);
        double b = x * Math.Log(y);

        // Comparing values
        if (a > b)
            Console.Write (x + "^" + y + " > " +
                           y + "^" + x);

        else if (a < b)
                Console.Write (x + "^" + y + " < "+
                               y + "^" + x);

        else if (a == b)
            Console.Write (x + "^" + y + " = " +
                           y + "^" + x );
    }

    // Driver code
    static public void Main ()
    {
        double x = 4, y = 5;

        compareVal(x, y);
    }
}

// This Code is contributed by ajit.
```

## JavaScript

```javascript
<script>
// Javascript implementation of the approach

// Function to compare x^y and y^x
function compareVal(x, y)
{
    // Storing values OF x^y AND y^x
    let a = y * Math.log(x);
    let b = x * Math.log(y);

    // Comparing values
    if (a > b)
        document.write(x + "^" + y + " > "
             + y + "^" + x);

    else if (a < b)
        document.write(x + "^" + y + " < "
             + y + "^" + x);

    else if (a == b)
        document.write(x + "^" + y + " = "
             + y + "^" + x);
}

// Driver code
    let x = 4, y = 5;

    compareVal(x, y);

</script>
```

**输出:**

```
4^5 > 5^4
```