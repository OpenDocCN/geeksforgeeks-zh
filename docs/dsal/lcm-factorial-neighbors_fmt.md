# 阶乘及其邻域的 LCM

> 原文：[https://www.geeksforgeeks.org/lcm-factorial-neighbors/](https://www.geeksforgeeks.org/lcm-factorial-neighbors/)

给定一个数，我们需要找到数及其邻域的[阶乘](https://www.geeksforgeeks.org/program-for-factorial-of-a-number/)的 LCM。如果数是 `N`，我们需要求 `(N-1)!`，`N!` 和 `(N+1)!` 的 LCM。这里 `N` 总是大于等于 1。

**示例：**

```
Input : N = 5  
Output : 720
Explanation
Here the given number is 5, its neighbors 
are 4 and 6. The factorial of these three 
numbers are 24, 120, and 720.so the LCM
of 24, 120, 720 is 720.

Input : N = 3  
Output : 24
Explanation
Here the given number is 3, its Neighbors
are 2 and 4.the factorial of these three 
numbers are 2, 6, and 24. So the LCM of 
2, 6 and 24 is 24.
```

## 方法 1（简单）

我们首先计算数和的阶乘及其相邻数的阶乘，然后求这些阶乘数的 LCM。

## 方法 2（高效）

我们可以看到 `(N-1)!`，`N!` 和 `(N+1)!` 的 LCM 永远是 `(N-1)! * N! * (N+1)!`。这个可以写成 `(N-1)! * N * (N-1)! * (N+1) * N * (N-1)!`。所以 LCM 变成 `(N-1)! * N * (N+1)`，也就是 `(N+1)!`。

**示例：**
`N = 5`
我们需要找到 `4!`，`5!` 和 `6!` 的 LCM。
`LCM(4!, 5!, 6!)`
`= 4! * 5! * 6!`
`= 4! * 5 * 4! * 6 * 5 * 4!`
`= 6 * 5 * 4!`
`= 720`
所以我们可以说三个连续数的阶乘的 LCM 永远是最大数的阶乘，这种情况下是 `(N+1)!`。

## C++

```cpp
// CPP program to calculate the LCM of N!
// and its neighbor (N-1)! and (N+1)!
#include <bits/stdc++.h>
using namespace std;

// function to calculate the factorial
unsigned int factorial(unsigned int n)
{
    if (n == 0)
        return 1;
    return n * factorial(n - 1);
}

int LCMOfNeighbourFact(int n)
{
    // returning the factorial of the
    // largest number in the given three
    // consecutive numbers
    return factorial(n + 1);
}

// Driver code
int main()
{
    int N = 5;
    cout << LCMOfNeighbourFact(N) << "\n";
    return 0;
}
```

## Java

```java
// Java program to calculate the LCM of N!
// and its neighbor (N-1)! and (N+1)!
import java.io.*;

class GFG {

    // function to calculate the factorial
    static int factorial(int n)
    {
        if (n == 0)
            return 1;

        return n * factorial(n - 1);
    }

    static int LCMOfNeighbourFact(int n)
    {

        // returning the factorial of the
        // largest number in the given three
        // consecutive numbers
        return factorial(n + 1);
    }

    // Driver code
    public static void main(String args[])
    {
        int N = 5;

        System.out.println(LCMOfNeighbourFact(N));
    }
}

/*This code is contributed by Nikita Tiwari.*/
```

## Python 3

```python
# Python3 program to calculate the LCM of N!
# and its neighbor (N-1)! and (N+1)!

# Function to calculate the factorial
def factorial(n):
    if (n == 0):
        return 1
    return n * factorial(n - 1)

def LCMOfNeighbourFact(n):

    # returning the factorial of the
    # largest number in the given three
    # consecutive numbers
    return factorial(n + 1)

# Driver code
N = 5
print(LCMOfNeighbourFact(N))

# This code is contributed by Anant Agarwal.
```

## C#

```csharp
// Program to calculate the LCM
// of N! and its neighbor (N-1)!
// and (N+1)!
using System;

class GFG
{
// function to calculate the factorial
static int factorial(int n) {

    if (n == 0)
        return 1;
    return n * factorial(n - 1);
}

static int LCMOfNeighbourFact(int n) {

    // returning the factorial of the
    // largest number in the given three
    // consecutive numbers
    return factorial(n + 1);
}

// Driver code
public static void Main()
{
 int N = 5;

 Console.WriteLine(LCMOfNeighbourFact(N));
}
}

// This code is contributed by Anant Agarwal.
```

## PHP

```php
<?php
// PHP program to calculate
// the LCM of N! and its neighbor
// (N-1)! and (N+1)!

// function to calculate
// the factorial
function factorial($n)
{
    if ($n == 0)
        return 1;
    return $n * factorial($n - 1);
}

function LCMOfNeighbourFact($n)
{
    // returning the factorial
    // of the largest number in
    // the given three
    // consecutive numbers
    return factorial($n + 1);
}

// Driver code
$N = 5;
echo(LCMOfNeighbourFact($N));

// This code is contributed by Ajit.
?>
```

## JavaScript

```javascript
<script>
// javascript program to calculate the LCM of N!
// and its neighbor (N-1)! and (N+1)!

    // function to calculate the factorial
    function factorial(n)
    {
        if (n == 0)
            return 1;

        return n * factorial(n - 1);
    }

    function LCMOfNeighbourFact(n)
    {

        // returning the factorial of the
        // largest number in the given three
        // consecutive numbers
        return factorial(n + 1);
    }

    // Driver code
    var N = 5;
    document.write(LCMOfNeighbourFact(N));

// This code is contributed by aashish1995
</script>
```

**Output:**