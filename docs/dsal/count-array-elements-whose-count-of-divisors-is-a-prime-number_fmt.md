# 计数除数为素数的数组元素

> 原文:[https://www . geesforgeks . org/count-array-elements-其除数是素数/](https://www.geeksforgeeks.org/count-array-elements-whose-count-of-divisors-is-a-prime-number/)

给定一个由 `N` 个正整数组成的数组 `arr[]`，任务是找出数组元素的个数，其中除数是一个素数。

**示例:**

> ***输入:** `arr[] = {3，6，4}`*
> ***输出:** `2`*
> ***解释:***
> 每个元素的除数为:
> 1.  `arr[0]( = 3):` 3 有 2 个除数，即 1 和 3。
> 2.  `arr[1]( = 6):` 6 有 4 个除数，即 1、2、3 和 6。
> 3.  `arr[2]( = 4):` 4 有 3 个除数，即 1、2 和 4。
> 因此，只有 2 个数组元素，即{3，4}，其除数为素数。
> ***输入:** `arr[] = {10，13，17，25}`*
> ***输出:** `3`*

**天真法:**解决给定问题最简单的方法是求每个数组元素的除数，检查除数是否为素数。如果发现为真，则增加 `计数`。否则，检查下一个元素。检查所有数组元素后，打印获得的 `计数`。
***时间复杂度:**`O(N^(3/2))`*
***辅助空间:** `O(1)`*

**高效方法:**上述方法可以通过使用厄拉多塞的筛预计算素数来优化。按照以下步骤解决给定的问题:
*   初始化一个变量，比如说 `计数`，来存储数组元素的计数，数组元素的除数是一个质数。
*   使用厄拉多塞的筛，将所有质数存储到布尔数组的最大元素，比如说 `质数`。
*   现在找到元素的除数直到数组的最大元素，并将它们存储在一个数组中，比如 `计数除数[]`。
*   遍历给定的数组 `arr[]`，对于每个元素 `arr[i]`，如果 `count divider[arr[i]]` 的值是质数，那么将 `计数` 增加 `1`。否则，检查下一个元素。
*   完成上述步骤后，打印 `计数` 的值作为结果。

下面是上述方法的实现:

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to count the array elements
// whose count of divisors is prime
int primeDivisors(int arr[], int N)
{
    // Stores the maximum element
    int K = arr[0];

    // Find the maximum element
    for (int i = 1; i < N; i++) {
        K = max(K, arr[i]);
    }

    // Store if i-th element is
    // prime(0) or non-prime(1)
    int prime[K + 1] = { 0 };

    // Base Case
    prime[0] = 1;
    prime[1] = 1;

    for (int i = 2; i < K + 1; i++) {

        // If i is a prime number
        if (!prime[i]) {

            // Mark all multiples
            // of i as non-prime
            for (int j = 2 * i;
                 j < K + 1; j += i) {

                prime[j] = 1;
            }
        }
    }

    // Stores the count of divisors
    int factor[K + 1] = { 0 };

    // Base Case
    factor[0] = 0;
    factor[1] = 1;

    for (int i = 2; i < K + 1; i++) {

        factor[i] += 1;

        // Iterate to count factors
        for (int j = i; j < K + 1;
             j += i) {

            factor[j] += 1;
        }
    }

    // Stores the count of array
    // elements whose count of
    // divisors is a prime number
    int count = 0;

    // Traverse the array arr[]
    for (int i = 0; i < N; i++) {

        // If count of divisors is prime
        if (prime[factor[arr[i]]] == 0)
            count++;
    }

    // Return the resultant count
    return count;
}

// Driver Code
int main()
{
    int arr[] = { 10, 13, 17, 25 };
    int N = sizeof(arr) / sizeof(arr[0]);
    cout << primeDivisors(arr, N);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for the above approach
public class GFG
{

    // Function to count the array elements
    // whose count of divisors is prime
    public static int primeDivisors(int[] arr, int N)
    {

        // Stores the maximum element
        int K = arr[0];

        // Find the maximum element
        for (int i = 1; i < N; i++) {
            K = Math.max(K, arr[i]);
        }

        // Store if i-th element is
        // prime(0) or non-prime(1)
        int[] prime = new int[K + 1];

        // Base Case
        prime[0] = 1;
        prime[1] = 1;

        for (int i = 2; i < K + 1; i++) {

            // If i is a prime number
            if (prime[i] == 0) {

                // Mark all multiples
                // of i as non-prime
                for (int j = 2 * i; j < K + 1; j += i) {

                    prime[j] = 1;
                }
            }
        }

        // Stores the count of divisors
        int[] factor = new int[K + 1];

        // Base Case
        factor[0] = 0;
        factor[1] = 1;

        for (int i = 2; i < K + 1; i++) {

            factor[i] += 1;

            // Iterate to count factors
            for (int j = i; j < K + 1; j += i) {

                factor[j] += 1;
            }
        }

        // Stores the count of array
        // elements whose count of
        // divisors is a prime number
        int count = 0;

        // Traverse the array arr[]
        for (int i = 0; i < N; i++) {

            // If count of divisors is prime
            if (prime[factor[arr[i]]] == 0)
                count++;
        }

        // Return the resultant count
        return count;
    }

    // Driver Code
    public static void main(String args[]) {
      int[] arr = { 10, 13, 17, 25 };
        int N = arr.length;
       System.out.println(primeDivisors(arr, N));

    }
}

// This code is contributed by SoumikMondal.
```

## 蟒蛇 3

```python
# Python3 program for the above approach

# Function to count the array elements
# whose count of divisors is prime
def primeDivisors(arr, N):

    # Stores the maximum element
    K = arr[0]

    # Find the maximum element
    for i in range(1, N):
        K = max(K, arr[i])

    # Store if i-th element is
    # prime(0) or non-prime(1)
    prime = [0] * (K + 1)

    # Base Case
    prime[0] = 1
    prime[1] = 1

    for i in range(2, K + 1):

        # If i is a prime number
        if (not prime[i]):

            # Mark all multiples
            # of i as non-prime
            for j in range(2 * i, K + 1, i):
                prime[j] = 1

    # Stores the count of divisors
    factor = [0] * (K + 1)

    # Base Case
    factor[0] = 0
    factor[1] = 1

    for i in range(2, K + 1):
        factor[i] += 1

        # Iterate to count factors
        for j in range(i, K + 1, i):
            factor[j] += 1

    # Stores the count of array
    # elements whose count of
    # divisors is a prime number
    count = 0

    # Traverse the array arr[]
    for i in range(N):

        # If count of divisors is prime
        if (prime[factor[arr[i]]] == 0):
            count += 1

    # Return the resultant count
    return count

# Driver Code
if __name__ == '__main__':

    arr = [ 10, 13, 17, 25 ]
    N = len(arr)

    print (primeDivisors(arr, N))

# This code is contributed by mohit kumar 29
```

## C#

```csharp
// C# program for the above approach
using System;
class GFG
{
    // Function to count the array elements
    // whose count of divisors is prime
    static int primeDivisors(int[] arr, int N)
    {
        // Stores the maximum element
        int K = arr[0];
        // Find the maximum element
        for (int i = 1; i < N; i++) {
            K = Math.Max(K, arr[i]);
        }
        // Store if i-th element is
        // prime(0) or non-prime(1)
        int[] prime = new int[K + 1];
        // Base Case
        prime[0] = 1;
        prime[1] = 1;
        for (int i = 2; i < K + 1; i++) {
            // If i is a prime number
            if (prime[i] == 0) {
                // Mark all multiples
                // of i as non-prime
                for (int j = 2 * i; j < K + 1; j += i) {
                    prime[j] = 1;
                }
            }
        }
        // Stores the count of divisors
        int[] factor = new int[K + 1];
        // Base Case
        factor[0] = 0;
        factor[1] = 1;
        for (int i = 2; i < K + 1; i++) {
            factor[i] += 1;
            // Iterate to count factors
            for (int j = i; j < K + 1; j += i) {
                factor[j] += 1;
            }
        }
        // Stores the count of array
        // elements whose count of
        // divisors is a prime number
        int count = 0;
        // Traverse the array arr[]
        for (int i = 0; i < N; i++) {
            // If count of divisors is prime
            if (prime[factor[arr[i]]] == 0)
                count++;
        }
        // Return the resultant count
        return count;
    }
    // Driver Code
    public static void Main()
    {
        int[] arr = { 10, 13, 17, 25 };
        int N = arr.Length;
        Console.WriteLine(primeDivisors(arr, N));
    }
}
// This code is contributed by ukasp.
```

## JavaScript

```javascript
<script>
// JavaScript program for the above approach
// Function to count the array elements
// whose count of divisors is prime
function primeDivisors(arr, N)
{
    // Stores the maximum element
    var K = arr[0];
    var i,j;
    // Find the maximum element
    for (i = 1; i < N; i++) {
        K = Math.max(K, arr[i]);
    }
    // Store if i-th element is
    // prime(0) or non-prime(1)
    var prime = Array(K + 1).fill(0);
    // Base Case
    prime[0] = 1;
    prime[1] = 1;
    for (i = 2; i < K + 1; i++) {
        // If i is a prime number
        if (prime[i]==0) {
            // Mark all multiples
            // of i as non-prime
            for (j = 2 * i;
                 j < K + 1; j += i) {
                prime[j] = 1;
            }
        }
    }
    // Stores the count of divisors
    var factor = Array(K + 1).fill(0);
    // Base Case
    factor[0] = 0;
    factor[1] = 1;
    for (i = 2; i < K + 1; i++) {
        factor[i] += 1;
        // Iterate to count factors
        for (j = i; j < K + 1;
             j += i) {
            factor[j] += 1;
        }
    }
    // Stores the count of array
    // elements whose count of
    // divisors is a prime number
    var count = 0;
    // Traverse the array arr[]
    for (i = 0; i < N; i++) {
        // If count of divisors is prime
        if (prime[factor[arr[i]]] == 0)
            count++;
    }
    // Return the resultant count
    return count;
}
// Driver Code
    var arr = [10, 13, 17, 25];
    var N = arr.length;
    document.write(primeDivisors(arr, N));
</script>
```

### `Output:`

### `时间复杂度:` O(M*log M)，其中 `M` 是给定数组的最大元素。
### `辅助空间:` O(M)