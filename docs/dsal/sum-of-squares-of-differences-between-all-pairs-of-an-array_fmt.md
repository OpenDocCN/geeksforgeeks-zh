# 数组中所有对之间的差的平方和

> 原文: [https://www.geeksforgeeks.org/sum-of-squares-of-differences-between-all-pairs-of-an-array/](https://www.geeksforgeeks.org/sum-of-squares-of-differences-between-all-pairs-of-an-array/)

给定一个大小为 `N` 的数组 `arr[]`，任务是计算所有可能对的差的平方和。

## 示例

> **输入:** `arr[] = {2, 8, 4}`
> **输出:** 56
> **解释:**
> 所有可能对的平方差之和 = (2–8)² + (2–4)² + (8–4)² = 56
>
> **输入:** `arr[] = {-5, 8, 9, -4, -3}`
> **输出:** 950

## 方法

**朴素方法:** 最简单的方法是生成所有可能的对并计算每对的差的平方，并不断将其添加到一个变量中，比如 `sum`。最后，打印 `sum` 的值。

- **时间复杂度:** O(N²)
- **辅助空间:** O(1)

**高效方法:** 最优思想基于以如下方式重新排列表达式:

> I = Σ(i=2 to n) Σ(j=1 to i-1) (a_i - a_j)²

由于 a_i - a_i = 0，上述表达式可重新排列为 1/2 × (Σ(i=1 to n) Σ(j=1 to n) (a_i - a_j)²)。可利用下式进一步简化:

> (A–B)² = A² + B² – 2 * A * B

as 1/2 * (Σ(i=1 to n) Σ(j=1 to n) (a_i² + a_j² - 2*a_i*a_j))

最终表达式为 `n * Σ(i=1 to n) a_i² – (Σ(i=1 to n) a_i)²`，可以通过线性迭代数组来计算。

## 实现

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to calculate sum of squares
// of differences of all possible pairs
void sumOfSquaredDifferences(int arr[], int N)
{
    // Stores the final sum
    int ans = 0;

    // Stores temporary values
    int sumA = 0, sumB = 0;

    // Traverse the array
    for (int i = 0; i < N; i++) {
        sumA += (arr[i] * arr[i]);
        sumB += arr[i];
    }

    sumA = N * sumA;
    sumB = (sumB * sumB);

    // Final sum
    ans = sumA - sumB;

    // Print the answer
    cout << ans;
}

// Driver Code
int main()
{
    // Given array
    int arr[] = { 2, 8, 4 };

    // Size of the array
    int N = sizeof(arr) / sizeof(arr[0]);

    // Function call to find sum of square
    // of differences of all possible pairs
    sumOfSquaredDifferences(arr, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
class GFG{

// Function to calculate sum of squares
// of differences of all possible pairs
static void sumOfSquaredDifferences(int arr[], int N)
{
    // Stores the final sum
    int ans = 0;

    // Stores temporary values
    int sumA = 0, sumB = 0;

    // Traverse the array
    for(int i = 0; i < N; i++)
    {
        sumA += (arr[i] * arr[i]);
        sumB += arr[i];
    }

    sumA = N * sumA;
    sumB = (sumB * sumB);

    // Final sum
    ans = sumA - sumB;

    // Print the answer
    System.out.println(ans);
}

// Driver Code
public static void main (String[] args)
{
    // Given array
    int arr[] = { 2, 8, 4 };

    // Size of the array
    int N = arr.length;

    // Function call to find sum of square
    // of differences of all possible pairs
    sumOfSquaredDifferences(arr, N);
}
}

// This code is contributed by AnkThon
```

### Python 3

```python
# Python3 program for the above approach

# Function to calculate sum of squares
# of differences of all possible pairs
def sumOfSquaredDifferences(arr, N):

    # Stores the final sum
    ans = 0

    # Stores temporary values
    sumA, sumB = 0, 0

    # Traverse the array
    for i in range(N):
        sumA += (arr[i] * arr[i])
        sumB += arr[i]

    sumA = N * sumA
    sumB = (sumB * sumB)

    # Final sum
    ans = sumA - sumB

    # Print the answer
    print(ans)

# Driver Code
if __name__ == '__main__':

    # Given array
    arr = [2, 8, 4]

    # Size of the array
    N = len(arr)

    # Function call to find sum of square
    # of differences of all possible pairs
    sumOfSquaredDifferences(arr, N)

# This code is contributed by mohit kumar 29.
```

### C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to calculate sum of squares
// of differences of all possible pairs
static void sumOfSquaredDifferences(int []arr, int N)
{
    // Stores the final sum
    int ans = 0;

    // Stores temporary values
    int sumA = 0, sumB = 0;

    // Traverse the array
    for(int i = 0; i < N; i++)
    {
        sumA += (arr[i] * arr[i]);
        sumB += arr[i];
    }

    sumA = N * sumA;
    sumB = (sumB * sumB);

    // Final sum
    ans = sumA - sumB;

    // Print the answer
    Console.WriteLine(ans);
}

// Driver Code
public static void Main(string[] args)
{
    // Given array
    int []arr = { 2, 8, 4 };

    // Size of the array
    int N = arr.Length;

    // Function call to find sum of square
    // of differences of all possible pairs
    sumOfSquaredDifferences(arr, N);
}
}

// This code is contributed by AnkThon
```

### JavaScript

```javascript
<script>
// Javascript program for the above approach

// Function to calculate sum of squares
// of differences of all possible pairs
function sumOfSquaredDifferences(arr, N)
{
    // Stores the final sum
    let ans = 0;

    // Stores temporary values
    let sumA = 0, sumB = 0;

    // Traverse the array
    for(let i = 0; i < N; i++)
    {
        sumA += (arr[i] * arr[i]);
        sumB += arr[i];
    }

    sumA = N * sumA;
    sumB = (sumB * sumB);

    // Final sum
    ans = sumA - sumB;

    // Print the answer
    document.write(ans);
}

// Driver Code

// Given array
let arr = [ 2, 8, 4 ];

// Size of the array
let N = arr.length;

// Function call to find sum of square
// of differences of all possible pairs
sumOfSquaredDifferences(arr, N);

// This code is contributed by subhammahato348
</script>
```

**输出:**

```
56
```

- **时间复杂度:** O(N)
- **辅助空间:** O(1)