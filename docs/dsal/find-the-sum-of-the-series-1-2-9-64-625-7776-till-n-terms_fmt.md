# 求数列 1 + 2 + 9 + 64 + 625 + 7776 的和…直到 N 项

> 原文: [https://www.geeksforgeeks.org/find-the-sum-of-the-series-1-2-9-64-625-7776-till-n-terms/](https://www.geeksforgeeks.org/find-the-sum-of-the-series-1-2-9-64-625-7776-till-n-terms/)

给定一个数字 `N`，任务是找到下面系列的和，直到 `N` 项。

> 1 + 2 + 9 + 64 + 625 + 7776 ...

**例:**

> **输入:** `N = 2`
> **输出:** 3
> 1 + 2 = 3
> **输入:** `N = 5`
> **输出:** 701
> 1+2+9+64+625 = 701

**方法:** 从给定的序列中，找到第 `n` 项的公式:

```
1st term = 1 = 1^(1-1)
2nd term = 2 = 2^(2-1)
3rd term = 9 = 3^(3-1)
4th term = 64 = 4^(4-1)
.
.
Nth term = N^(N-1)
```

因此，该系列的第 `n` 项为 `N^(N-1)`。

然后在 `[1, N]` 范围内的数字上迭代，使用上面的公式找到所有的项，并计算它们的和。

以下是上述办法的实施情况:

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the sum of series
void printSeriesSum(int N)
{
    long long sum = 0;

    for (int i = 1; i <= N; i++) {
        // Generate the ith term and
        // add it to the sum
        sum += pow(i, i - 1);
    }

    // Print the sum
    cout << sum << endl;
}

// Driver Code
int main()
{
    int N = 5;
    printSeriesSum(N);
    return 0;
}
```

## Java

```java
// Java program for the above approach
class GFG{

// Function to find the sum of series
static void printSeriesSum(int N)
{
    long sum = 0;

    for (int i = 1; i <= N; i++) {
        // Generate the ith term and
        // add it to the sum
        sum += Math.pow(i, i - 1);
    }

    // Print the sum
    System.out.print(sum +"\n");
}

// Driver Code
public static void main(String[] args)
{
    int N = 5;
    printSeriesSum(N);
}
}

// This code is contributed by Princi Singh
```

## Python 3

```python
# Python3 program for the above approach

# Function to find the summ of series
def printSeriessumm(N):
    summ = 0

    for i in range(1,N+1):
        # Generate the ith term and
        # add it to the summ
        summ += pow(i, i - 1)

    # Prthe summ
    print(summ)

# Driver Code
N = 5
printSeriessumm(N)

# This code is contributed by shubhamsingh10
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to find the sum of series
static void printSeriesSum(int N)
{
    double sum = 0;

    for (int i = 1; i <= N; i++) {
        // Generate the ith term and
        // add it to the sum
        sum += Math.Pow(i, i - 1);
    }

    // Print the sum
    Console.Write(sum +"\n");
}

// Driver Code
public static void Main(String[] args)
{
    int N = 5;
    printSeriesSum(N);
}
}

// This code is contributed by PrinciRaj1992
```

## JavaScript

```javascript
<script>
// javascript program for the above approach

// Function to find the sum of series
function printSeriesSum( N)
{
    let sum = 0;

    for (let i = 1; i <= N; i++) {
        // Generate the ith term and
        // add it to the sum
        sum += Math.pow(i, i - 1);
    }

    // Print the sum
    document.write(sum);
}

// Driver Code
    let N = 5;
    printSeriesSum(N);

// This code is contributed by todaysgaurav
</script>
```

**Output:**

```
701
```

时间复杂度: `O(N * log N)`

辅助空间: `O(1)`