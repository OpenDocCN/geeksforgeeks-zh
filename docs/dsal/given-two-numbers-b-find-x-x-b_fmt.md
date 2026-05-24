# 给定两个数字 a 和 b，求所有 x，使得 a % x = b

> 原文: [https://www.geeksforgeeks.org/given-two-numbers-b-find-x-x-b/](https://www.geeksforgeeks.org/given-two-numbers-b-find-x-x-b/)

给定两个数字 `a` 和 `b`，求所有 `x`，使得 `a % x = b`。

示例:

```
Input : a = 21, b = 5
Output : 2
The answers of the Modular Equation are
8 and 16 since 21 % 8 = 21 % 16 = 5 .
```

这里出现 3 种情况:

1.  如果 `(a < b)` 则没有答案。
2.  如果 `(a = b)` 则所有大于 `a` 的数字都是答案，此时将有无限多个可能的解。
3.  如果 `(a > b)`，令 `x` 为方程的解。那么 `x` 能整除 `(a–b)`。类似地，因为 `a % x = b`，所以 `b < x`。这些条件也是必要且充分的。因此，答案是 `A–B` 的约数中严格大于 `B` 的那些，可以在 **`O(SQRT(a-b))`** 时间内求解。这里只有一种特殊情况。当 `(a-b)` 是一个完全平方数时，我们需要单独处理，然后我们会将其平方根计算了两次，因此必须减去一次。如果发生这种情况。

## C++

```cpp
// C++ program to find x such that a % x is equal
// to b.
#include <bits/stdc++.h>
using namespace std;

void modularEquation(int a, int b)
{
    // if a is less than b then no solution
    if (a < b) {
        cout << "No solution possible " << endl;
        return;
    }

    // if a is equal to b then every number
    // greater than a will be the solution
    // so its infinity
    if (a == b) {
        cout << "Infinite Solution possible " << endl;
        return;
    }

    // all resultant number should be greater than
    // b and (a-b) should be divisible by resultant
    // number

    // count variable store the number of values
    // possible
    int count = 0;
    int n = a - b;
    int y = sqrt(a - b);
    for (int i = 1; i <= y; ++i) {
        if (n % i == 0) {

            // checking for both divisor and quotient
            // whether they divide ( a-b ) completely
            // and greater than b .
            if (n / i > b)
                count++;
            if (i > b)
                count++;
        }
    }

    // Here y is added twice in the last iteration
    // so 1 y should be decremented to get correct
    // solution
    if (y * y == n && y > b)
        count--;

    cout << count << endl;
}

// Driver code
int main()
{
    int a = 21, b = 5;
    modularEquation(a, b);
    return 0;
}
```

## Java

```java
// Java program to find x such that
// a % x is equal to b.
import java.io.*;
class GFG {

    static void modularEquation(int a, int b)
    {
        // if a is less than b then no solution
        if (a < b) {
            System.out.println("No solution possible ");
            return;
        }

        // if a is equal to b then every number
        // greater than a will be the solution
        // so its infinity
        if (a == b) {
            System.out.println("Infinite Solution possible ");
            return;
        }

        // all resultant number should be greater
        // than b and (a-b) should be divisible
        // by resultant number

        // count variable store the number of
        // values possible
        int count = 0;
        int n = a - b;
        int y = (int)Math.sqrt(a - b);
        for (int i = 1; i <= y; ++i) {
            if (n % i == 0) {

                // checking for both divisor and
                // quotient whether they divide
                // ( a-b ) completely and
                // greater than b .
                if (n / i > b)
                    count++;
                if (i > b)
                    count++;
            }
        }

        // Here y is added twice in the last
        // iteration so 1 y should be decremented
        // to get correct solution
        if (y * y == n && y > b)
            count--;

        System.out.println(count);
    }

    // Driver code
    public static void main(String[] args)
    {
        int a = 21, b = 5;
        modularEquation(a, b);
    }
}

// This code is contributed by Prerna Saini
```

## Python 3

```python
# Python3 program to find x such
# that a % x is equal to b.

import math
def modularEquation(a, b) :

    # if a is less than b then no solution
    if (a < b) :
        print("No solution possible ")
        return

    # if a is equal to b then every number
    # greater than a will be the solution
    # so its infinity
    if (a == b) :
        print("Infinite Solution possible ")
        return

    # all resultant number should be
    # greater than b and (a-b) should
    # be divisible by resultant number

    # count variable store the number
    # of values possible
    count = 0
    n = a - b
    y = (int)(math.sqrt(a - b))
    for i in range(1, y+1) :
        if (n % i == 0) :

            # checking for both divisor
            # and quotient whether they
            # divide ( a-b ) completely
            # and greater than b .
            if (n / i > b) :
                count = count + 1
            if (i > b) :
                count = count  + 1

    # Here y is added twice in the
    # last iteration so 1 y should be
    # decremented to get correct
    # solution
    if (y * y == n and y > b) :
        count = count - 1

    print (count)

# Driver code
a = 21
b = 5
modularEquation(a, b)

# This code is contributed by Nikita Tiwari.
```

T35】c#T3T39】PHPT4T43】JavascriptT46

**输出:**

```

```