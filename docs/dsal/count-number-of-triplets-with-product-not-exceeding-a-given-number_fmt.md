# 计数三胞胎的数量，乘积不超过给定的数字

> 原文: [https://www.geeksforgeeks.org/count-number-of-triplets-with-product-not-exceeding-a-given-number/](https://www.geeksforgeeks.org/count-number-of-triplets-with-product-not-exceeding-a-given-number/)

给定一个正整数 `N`，任务是求正整数 `(X, Y, Z)` 的三元组个数，其乘积最多为 `N`。

**示例:**

> **输入:** `N = 2`
> **输出:** `4`
> **说明:** 下面是乘积最多为 `N(= 2)` 的三胞胎:
> 1.  `(1, 1, 1)`: 乘积为 `1*1*1 = 1`。
> 2.  `(1, 1, 2)`: 乘积为 `1*1*2 = 2`。
> 3.  `(1, 2, 1)`: 乘积为 `1*2*1 = 2`。
> 4.  `(2, 1, 1)`: 乘积为 `2*1*1 = 2`。
>
> 因此，总数为 `4`。

> **输入:** `6`
> **输出:** `25`

**天真方法:** 解决给定问题最简单的方法是[生成所有可能的三元组](https://www.geeksforgeeks.org/python-ways-to-create-triplets-from-given-list/)，其值位于范围 `[0, N]` 内，并计算那些值的乘积最多为 `N` 的三元组。检查所有三胞胎后，打印得到的总数 `count`。

**时间复杂度:** `O(N^3)`
**辅助空间:** `O(1)`

**高效方法:** 上述方法也可以通过[在范围 `[1, N]` 内生成所有可能的对 `(i, j)`](https://www.geeksforgeeks.org/find-all-pairs-possible-from-the-given-array/) 并将所有可能对的计数增加 `N / (i * j)` 来优化。按照以下步骤解决问题:

*   初始化一个变量，比如说 `sum`，它存储所有可能的三元组的计数。
*   [在范围 `[1, N]` 内生成所有可能的对 `(i, j)`](https://www.geeksforgeeks.org/find-all-pairs-possible-from-the-given-array/)，如果对的乘积大于 `N`，则检查下一对。否则，将所有可能对的计数增加 `N/(i*j)`。
*   完成上述步骤后，打印 `sum` 的值作为结果。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach

#include <iostream>
using namespace std;

// Function to count the number of
// triplets whose product is at most N
int countTriplets(int N)
{
    // Stores the count of triplets
    int ans = 0;

    // Iterate over the range [0, N]
    for (int i = 1; i <= N; i++) {

        // Iterate over the range [0, N]
        for (int j = 1; j <= N; j++) {

            // If the product of
            // pairs exceeds N
            if (i * j > N)
                break;

            // Increment the count of
            // possible triplets
            ans += N / (i * j);
        }
    }

    // Return the total count
    return ans;
}

// Driver Code
int main()
{
    int N = 10;
    cout << countTriplets(N);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function to count the number of
// triplets whose product is at most N
static int countTriplets(int N)
{

    // Stores the count of triplets
    int ans = 0;

    // Iterate over the range [0, N]
    for(int i = 1; i <= N; i++)
    {

        // Iterate over the range [0, N]
        for(int j = 1; j <= N; j++)
        {

            // If the product of
            // pairs exceeds N
            if (i * j > N)
                break;

            // Increment the count of
            // possible triplets
            ans += N / (i * j);
        }
    }

    // Return the total count
    return ans;
}

// Driver Code
public static void main(String[] args)
{
    int N = 10;
    System.out.print(countTriplets(N));
}
}

// This code is contributed by Amit Katiyar
```

## Python 3

```python
# Python3 program for the above approach

# Function to count the number of
# triplets whose product is at most N

def countTriplets(N):

    # Stores the count of triplets
    ans = 0

    # Iterate over the range [0, N]
    for i in range(1, N + 1):

        # Iterate over the range [0, N]
        for j in range(1, N + 1):

            # If the product of
            # pairs exceeds N
            if (i * j > N):
                break

            # Increment the count of
            # possible triplets
            ans += N // (i * j)

    # Return the total count
    return ans

# Driver Code
if __name__ == "__main__":

    N = 10
    print(countTriplets(N))

    # This code is contributed by ukasp.
```

## C#

```csharp
// C# program for the above approach
using System;

class GFG{

// Function to count the number of
// triplets whose product is at most N
static int countTriplets(int N)
{

    // Stores the count of triplets
    int ans = 0;

    // Iterate over the range [0, N]
    for(int i = 1; i <= N; i++)
    {

        // Iterate over the range [0, N]
        for(int j = 1; j <= N; j++)
        {

            // If the product of
            // pairs exceeds N
            if (i * j > N)
                break;

            // Increment the count of
            // possible triplets
            ans += N / (i * j);
        }
    }

    // Return the total count
    return ans;
}

// Driver Code
public static void Main(String[] args)
{
    int N = 10;
    Console.Write(countTriplets(N));
}
}

// This code is contributed by Princi Singh
```

## JavaScript

```javascript
<script>
// JavaScript program for the above approach

// Function to count the number of
// triplets whose product is at most N
function countTriplets( N){
    // Stores the count of triplets
    let ans = 0;
    // Iterate over the range [0, N]
    for (let i = 1; i <= N; i++) {

        // Iterate over the range [0, N]
        for (let j = 1; j <= N; j++) {

            // If the product of
            // pairs exceeds N
            if (i * j > N)
                break;

            // Increment the count of
            // possible triplets
            ans += Math.floor(N / (i * j));
        }
    }

    // Return the total count
    return ans;
}

// Driver Code

let N = 10;
document.write( countTriplets(N));

// This code is contributed by rohitsingh07052.
</script>
```

**Output:**

```
25
```

**时间复杂度:** `O(N^2)`
**辅助空间:** `O(1)`