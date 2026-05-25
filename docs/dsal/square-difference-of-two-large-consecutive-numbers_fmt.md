# 两个连续大数字的平方差

> 原文: [https://www.geeksforgeeks.org/square-difference-of-two-large-consecutive-numbers/](https://www.geeksforgeeks.org/square-difference-of-two-large-consecutive-numbers/)

给定两个连续的正数 `M` 和 `N`，任务是在不计算这两个数的平方的情况下找到这两个数的平方差。

**例:**

> **输入:** `N = 4`，`M = 5`
> **输出:** `9`
> **说明:**
> `5^2–4^2 = 25–16 = 9`。
> **输入:** `N = 9999999999`，`M = 100000000`
> **输出:** `19999999999`

**方法:** 思路是用代数表达式求解这个问题。题中给出 `M = N + 1`。因此:

*   要计算的值是 `M^2–N^2`。
*   当用 `N + 1` 代替 `M` 时，上述等式变为:

```
(N + 1)^2 - N^2
```

*   `(N + 1)^2` 可以扩展为:

```
N^2 + 1^2 + 2 * N - N^2
```

*   简化后，上述等式变为:

```
1 + 2 * N
1 + N + N
(1 + N) + N
M + N
```

*   因此，我们只需要计算并返回 `M + N` 的值。

以下是上述方法的实现:

## C++ 实现

```cpp
// C++ program to find the square
// difference of two large
// consecutive numbers

#include <bits/stdc++.h>
using namespace std;
typedef long long l;

// Function to find the square
// difference of two large
// consecutive numbers
l difference(l M, l N)
{
    return M + N;
}

// Driver code
int main()
{
    l M = 999999999;
    l N = 1000000000;

    cout << difference(M, N) << endl;
}
```

## Java 实现

```java
// Java program to find the square
// difference of two large
// consecutive numbers

class GFG{

// Function to find the square
// difference of two large
// consecutive numbers
static long difference(long M, long N)
{
    return M + N;
}

// Driver code
public static void main(String[] args)
{
    long M = 999999999;
    long N = 1000000000;

    System.out.print(difference(M, N) +"\n");
}
}

// This code is contributed by 29AjayKumar
```

## Python 3 实现

```python
# Python3 program to find the square
# difference of two large
# consecutive numbers

# Function to find the square
# difference of two large
# consecutive numbers
def difference(M, N):
    return M + N

# Driver code
if __name__ == '__main__':
    M = 999999999
    N = 1000000000

    print(difference(M, N))

# This code is contributed by mohit kumar 29
```

## C# 实现

```csharp
// C# program to find the square
// difference of two large
// consecutive numbers
using System;

public class GFG{

// Function to find the square
// difference of two large
// consecutive numbers
static long difference(long M, long N)
{
    return M + N;
}

// Driver code
public static void Main(String[] args)
{
    long M = 999999999;
    long N = 1000000000;

    Console.Write(difference(M, N) +"\n");
}
}

// This code is contributed by 29AjayKumar
```

## JavaScript 实现

```javascript
// JavaScript program to find the square
// difference of two large
// consecutive numbers

// Function to find the square
// difference of two large
// consecutive numbers
function difference(M, N)
{
    return M + N;
}

// Driver code
let M = 999999999;
let N = 1000000000;

document.write(difference(M, N));
```

**输出:**

```
1999999999
```