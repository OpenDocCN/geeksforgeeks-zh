# N 个自然数之和与乘积之差形成的级数之和

> 原文: [https://www.geeksforgeeks.org/sum-of-series-formed-by-difference-between-product-and-sum-of-n-natural-numbers/](https://www.geeksforgeeks.org/sum-of-series-formed-by-difference-between-product-and-sum-of-n-natural-numbers/)

给定一个自然数 `N`，任务是找到直到第 `N` 项的级数之和，其中第 `i` 项表示前 `i` 个自然数的乘积与前 `i` 个自然数的和之间的差，即：

> { 1 – 1 } + { (1 * 2) – (2 + 1) } + { (1 * 2 * 3) – (3 + 2 + 1) } + { (1 * 2 * 3 * 4) – (4 + 3 + 2 + 1) } + ………

**示例:**

> **输入:** 2
> **输出:** -1
> **解释:** { 1–1 } + {(1 * 2)–(2+1)} = { 0 } + {-1 } = -1
>
> **输入:** 4
> **输出:** 13
> **解释:** { 0 } + {(1 * 2)–(2+1)} + {(1 * 2 * 3)–(3+2+1)} + {(1 * 2 * 3 * 4)–(4+3+2+1)}
> = { 0 } + {-1 } + { 0 } + { 14 }
> = 0 – 1 + 0 + 14

## 迭代方法

按照以下步骤解决问题:

*   初始化三个变量:
    *   `currProd`: 存储截至当前项的所有自然数的乘积。
    *   `currSum`: 存储截至当前项的所有自然数的总和。
    *   `sum`: 存储截至当前项的级数总和。
*   初始化 `currProd = 1`，`currSum = 1`，和 `sum = 0` (因为 1–1 = 0) 以存储它们各自的第一项值。
*   迭代范围 `[2, N]` 并为每一次第 `i` 次迭代更新以下内容:
    *   `currSum = currSum + i`
    *   `currProd = currProd * i`
    *   `sum = sum + currProd - currSum`
*   返回 `sum` 的最终值。

下面是上述方法的实现:

### C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to
// calculate the
// sum upto Nth term
int seriesSum(int n)
{
    // Stores the sum
    // of the series
    int sum = 0;

    // Stores the
    // product of
    // natural numbers
    // upto the
    // current term
    int currProd = 1;

    // Stores the sum
    // of natural numbers
    // upto the
    // upto current term
    int currSum = 1;

    // Generate the remaining
    // terms and calculate sum
    for (int i = 2; i <= n; i++) {
        currProd *= i;
        currSum += i;

        // Update the sum
        sum += currProd
               - currSum;
    }

    // Return the sum
    return sum;
}

// Driver Program
int main()
{
    int N = 5;
    cout << seriesSum(N) << " ";
}
```

### Java

```java
// Java program to implement the
// above approach
import java.lang.*;

class GFG{

// Function to calculate the
// sum upto Nth term
static int seriesSum(int n)
{

    // Stores the sum
    // of the series
    int sum = 0;

    // Stores the product of
    // natural numbers upto
    // the current term
    int currProd = 1;

    // Stores the sum of natural
    // numbers upto the upto
    // current term
    int currSum = 1;

    // Generate the remaining
    // terms and calculate sum
    for(int i = 2; i <= n; i++)
    {
       currProd *= i;
       currSum += i;

       // Update the sum
       sum += currProd - currSum;
    }

    // Return the sum
    return sum;
}

// Driver code
public static void main(String[] args)
{
    int N = 5;

    System.out.print(seriesSum(N));
}
}

// This code is contributed by rock_cool
```

### Python 3

```python
# Python3 program to implement
# the above approach

# Function to calculate the
# sum upto Nth term
def seriesSum(n):

    # Stores the sum
    # of the series
    sum1 = 0;

    # Stores the product of
    # natural numbers upto the
    # current term
    currProd = 1;

    # Stores the sum of natural numbers
    # upto the upto current term
    currSum = 1;

    # Generate the remaining
    # terms and calculate sum
    for i in range(2, n + 1):
        currProd *= i;
        currSum += i;

        # Update the sum
        sum1 += currProd - currSum;

    # Return the sum
    return sum1;

# Driver Code
N = 5;
print(seriesSum(N), end = " ");

# This code is contributed by Code_Mech
```

### C#

```csharp
// C# program to implement the
// above approach
using System;
class GFG{

// Function to calculate the
// sum upto Nth term
static int seriesSum(int n)
{

    // Stores the sum
    // of the series
    int sum = 0;

    // Stores the product of
    // natural numbers upto
    // the current term
    int currProd = 1;

    // Stores the sum of natural
    // numbers upto the upto
    // current term
    int currSum = 1;

    // Generate the remaining
    // terms and calculate sum
    for(int i = 2; i <= n; i++)
    {
        currProd *= i;
        currSum += i;

        // Update the sum
        sum += currProd - currSum;
    }

    // Return the sum
    return sum;
}

// Driver code
public static void Main()
{
    int N = 5;

    Console.Write(seriesSum(N));
}
}

// This code is contributed by Code_Mech
```

### JavaScript

```javascript
<script>

    // Javascript program to implement
    // the above approach

    // Function to
    // calculate the
    // sum upto Nth term
    function seriesSum(n)
    {
        // Stores the sum
        // of the series
        let sum = 0;

        // Stores the
        // product of
        // natural numbers
        // upto the
        // current term
        let currProd = 1;

        // Stores the sum
        // of natural numbers
        // upto the
        // upto current term
        let currSum = 1;

        // Generate the remaining
        // terms and calculate sum
        for (let i = 2; i <= n; i++) {
            currProd *= i;
            currSum += i;

            // Update the sum
            sum += currProd
                   - currSum;
        }

        // Return the sum
        return sum;
    }

    let N = 5;
    document.write(seriesSum(N) + " ");

</script>
```

**输出:**

```
15
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`

## 递归方法

*   通过调用函数递归计算和，更新 `K` (表示当前项)。
*   通过添加 `multi * K – add + K` 更新预计算的 `prevSum`。
*   递归计算 `K` 的所有值，在每次迭代时更新 `prevSum`、`multi` 和 `add`。
*   最后，返回 `prevSum` 的值。

下面是上述方法的实现:

### C++

```cpp
// C++ program to calculate the
// sum upto the Nth term of the
// given series

#include <bits/stdc++.h>
using namespace std;

// Recursive Function to calculate the
// sum upto Nth term
int seriesSumUtil(int k, int n,
                  int prevSum,
                  int multi, int add)
{
    // If N-th term is calculated
    if (k == n + 1) {
        return prevSum;
    }

    // Update multi to store
    // product upto K
    multi = multi * k;

    // Update add to store
    // sum upto K
    add = add + k;

    // Update prevSum to store sum
    // upto K
    prevSum = prevSum + multi - add;

    // Proceed to next K
    return seriesSumUtil(k + 1, n, prevSum,
                         multi, add);
}

// Function to calculate
// and return the
// Sum upto Nth term
int seriesSum(int n)
{
    if (n == 1)
        return 0;
    int prevSum = 0;
    int multi = 1;
    int add = 1;

    // Recursive Function
    return seriesSumUtil(2, n, prevSum,
                         multi, add);
}

// Driver Program
int main()
{
    int N = 5;
    cout << seriesSum(N) << " ";
}
```

### Java

```java
// Java program to calculate the
// sum upto the Nth term of the
// given series
class GFG{

// Recursive Function to calculate the
// sum upto Nth term
static int seriesSumUtil(int k, int n,
                         int prevSum,
                         int multi, int add)
{

    // If N-th term is calculated
    if (k == n + 1)
    {
        return prevSum;
    }

    // Update multi to store
    // product upto K
    multi = multi * k;

    // Update add to store
    // sum upto K
    add = add + k;

    // Update prevSum to store sum
    // upto K
    prevSum = prevSum + multi - add;

    // Proceed to next K
    return seriesSumUtil(k + 1, n, prevSum,
                         multi, add);
}

// Function to calculate and
// return the Sum upto Nth term
static int seriesSum(int n)
{
    if (n == 1)
        return 0;

    int prevSum = 0;
    int multi = 1;
    int add = 1;

    // Recursive Function
    return seriesSumUtil(2, n, prevSum,
                         multi, add);
}

// Driver code
public static void main(String []args)
{
    int N = 5;
    System.out.println(seriesSum(N));
}
}

// This code is contributed by Ritik Bansal
```

## 蟒蛇 3

```python
# Python3 program to calculate the
# sum upto the Nth term of the
# given series

# Recursive Function to calculate the
# sum upto Nth term
def seriesSumUtil(k, n, prevSum, multi, add):

    # If N-th term is calculated
    if (k == n + 1):
        return prevSum;

    # Update multi to store
    # product upto K
    multi = multi * k;

    # Update add to store
    # sum upto K
    add = add + k;

    # Update prevSum to store sum
    # upto K
    prevSum = prevSum + multi - add;

    # Proceed to next K
    return seriesSumUtil(k + 1, n,
                         prevSum, multi, add);

# Function to calculate and
# return the Sum upto Nth term
def seriesSum(n):
    if (n == 1):
        return 0;

    prevSum = 0;
    multi = 1;
    add = 1;

    # Recursive Function
    return seriesSumUtil(2, n, prevSum,
                         multi, add);

# Driver code
if __name__ == '__main__':
    N = 5;
    print(seriesSum(N));

# This code is contributed by Princi Singh
```

## C\#

```csharp
// C# program to calculate the
// sum upto the Nth term of the
// given series
using System;
class GFG{

// Recursive Function to calculate the
// sum upto Nth term
static int seriesSumUtil(int k, int n,
                         int prevSum,
                         int multi, int add)
{

    // If N-th term is calculated
    if (k == n + 1)
    {
        return prevSum;
    }

    // Update multi to store
    // product upto K
    multi = multi * k;

    // Update add to store
    // sum upto K
    add = add + k;

    // Update prevSum to store sum
    // upto K
    prevSum = prevSum + multi - add;

    // Proceed to next K
    return seriesSumUtil(k + 1, n, prevSum,
                         multi, add);
}

// Function to calculate and
// return the Sum upto Nth term
static int seriesSum(int n)
{
    if (n == 1)
        return 0;

    int prevSum = 0;
    int multi = 1;
    int add = 1;

    // Recursive Function
    return seriesSumUtil(2, n, prevSum,
                         multi, add);
}

// Driver code
public static void Main(String []args)
{
    int N = 5;
    Console.WriteLine(seriesSum(N));
}
}

// This code is contributed by Rohit_ranjan
```

## java 描述语言

```javascript
// Javascript program to calculate the
// sum upto the Nth term of the
// given series

// Recursive Function to calculate the
// sum upto Nth term
function seriesSumUtil(k, n, prevSum, multi, add)
{

    // If N-th term is calculated
    if (k == n + 1)
    {
        return prevSum;
    }

    // Update multi to store
    // product upto K
    multi = multi * k;

    // Update add to store
    // sum upto K
    add = add + k;

    // Update prevSum to store sum
    // upto K
    prevSum = prevSum + multi - add;

    // Proceed to next K
    return seriesSumUtil(k + 1, n, prevSum,
                         multi, add);
}

// Function to calculate and
// return the Sum upto Nth term
function seriesSum(n)
{
    if (n == 1)
        return 0;

    let prevSum = 0;
    let multi = 1;
    let add = 1;

    // Recursive Function
    return seriesSumUtil(2, n, prevSum,
                         multi, add);
}

// Driver code
let N = 5;
document.write(seriesSum(N));

// This code is contributed by rameshtravel07
```

**Output:**

- **时间复杂度:** `O(N)`
- **辅助空间:** `O(1)`