# 包含所有元素的子集的斐波那契和< = k

> 原文:[https://www . geesforgeks . org/Fibonacci-sum-subset-elements/](https://www.geeksforgeeks.org/fibonacci-sum-subset-elements/)

给定一个由 n 个元素组成的数组，任务是求数组子集的斐波那契和，其中子集的每个元素<= k. 
精确地说，求**F(A<sub>i1</sub>)+F(A<sub>I2</sub>)+F(A<sub>i3</sub>)+…+F(A<sub>IX</sub>)**，其中(A <sub>i1</sub> ，A <sub>i2</sub> ，…， A <sub>ix</sub> ) < = K 和 1 < = (i <sub>1</sub> ，i <sub>2</sub> ，…，i <sub>x</sub> ) < = n .这里， **F(i)** 是 **i <sup>第</sup>个斐波那契数**
例:

```cpp
Input : arr = {1, 2, 3, 4, 2, 7}
        Query 1 : K = 2
        Query 2 : K = 6
Output : 3
         8
```

**说明:**
在**查询 1** 中，子集 **{1，2，2}** 就是这样一个子集，在这种情况下，子集内的所有元素都是< = k，即< = 2。子集的斐波那契和= F(1)+F(2)+F(2)= 1+1+1 =**3**
在**查询 2** 中，子集 **{1，2，3，4，2}** 是这样一个子集，其中子集内的所有元素都是< = k，即本例中的< = 6。子集的斐波那契和= F(1)+F(2)+F(3)+F(4)+F(2)= 1+1+2+3+1 =**8**
使用两种不同的查询技术来解决这个问题，即:
1)在线查询，
2)离线查询
在这两种方法中，唯一常见的步骤是生成第 n 个<sup>斐波那契数。使用[和](https://www.geeksforgeeks.org/program-for-nth-fibonacci-number/)生成第 n 个<sup>斐波那契数的有效技术。
这种生成斐波那契数的方法在两种查询技术中都很常见。现在，看看如何使用这两种技术生成的斐波那契数。
**方法 1(在线查询):**
在这种技术中，在查询到达时进行处理。首先，按升序对数组进行排序。获得特定 k 的查询后，在这个排序的数组上使用二分搜索法来查找最后一个索引，其中数组的值是& < = k。让我们称这个位置为 x。
现在，由于数组是排序的，</sup></sup> 

```cpp
For all i <= x, a[i] <= x
i.e
a[i] <= a[x] for all i ∈ [1, x]
```

所以，重点关注的子集是 A <sub>1</sub> ，A <sub>2</sub> ，A <sub>3</sub> ，…。排序数组 A 中的 A <sub>x</sub> ，斐波那契和为:**F(A<sub>1</sub>)+F(A<sub>2</sub>)+F(A<sub>3</sub>)+…+F(A<sub>x</sub>)**
使用[前缀和数组](https://www.geeksforgeeks.org/prefix-sum-array-implementation-applications-competitive-programming/)高效的求子集 A <sub>1</sub> ，A <sub>2【的和 A <sub>x</sub> 。
如果 prefixbsum[I]存储斐波那契和直到排序数组 A 的第 I<sup>个索引，那么，数组子集从 1 到 x 的斐波那契和，就是 prefixbsum[x]
这样，**子集[1…x]= prefixbsum[x]**，prefixbsum[x]可以计算如下:
**prefixbsum[x]= prefixbsum**</sup></sub> 

## C++

```cpp
// C++ program to find fibonacci sum of
// subarray where all elements <= k
#include <bits/stdc++.h>

using namespace std;

// Helper function that multiplies 2 matrices
// F and M of size 2*2, and puts the multiplication
// result back to F[][]
void multiply(int F[2][2], int M[2][2])
{
    int x = F[0][0] * M[0][0] + F[0][1] * M[1][0];
    int y = F[0][0] * M[0][1] + F[0][1] * M[1][1];
    int z = F[1][0] * M[0][0] + F[1][1] * M[1][0];
    int w = F[1][0] * M[0][1] + F[1][1] * M[1][1];

    F[0][0] = x;
    F[0][1] = y;
    F[1][0] = z;
    F[1][1] = w;
}

/* Helper function that calculates F[][]
   raise to the power n and puts the
   result in F[][]  */
void power(int F[2][2], int n)
{
    int i;
    int M[2][2] = { { 1, 1 }, { 1, 0 } };

    // n - 1 times multiply the
    // matrix to {{1, 0}, {0, 1}}
    for (i = 2; i <= n; i++)
        multiply(F, M);
}

// Returns the nth fibonacci number
int fib(int n)
{
    int F[2][2] = { { 1, 1 }, { 1, 0 } };
    if (n == 0)
        return 0;
    power(F, n - 1);

    return F[0][0];
}

int findLessThanK(int arr[], int n, int k)
{
    // find first index which is > k
    // using lower_bound
    return (lower_bound(arr, arr + n, k + 1)
                        - arr);
}

// Function to build Prefix Fibonacci Sum
int* buildPrefixFibonacciSum(int arr[], int n)
{
    // Allocate memory to prefix
    // fibonacci sum array
    int* prefixFibSum = new int[n];

    // Traverse the array from 0 to n - 1,
    // when at the ith index then we calculate
    // the a[i]th fibonacci number and calculate
    // the fibonacci sum till the ith index as
    // the sum of fibonacci sum till index i - 1
    // and the a[i]th fibonacci number
    for (int i = 0; i < n; i++)
    {
        int currFibNumber = fib(arr[i]);
        if (i == 0) {
            prefixFibSum[i] = currFibNumber;
        }
        else {
            prefixFibSum[i] = prefixFibSum[i - 1]
                              + currFibNumber;
        }
    }
    return prefixFibSum;
}

// Return the answer for each query
int processQuery(int arr[], int prefixFibSum[],
                 int n, int k)
{

    // index stores the index till where
    // the array elements are less than k
    int lessThanIndex = findLessThanK(arr, n, k);

    if (lessThanIndex == 0)
        return 0;
    return prefixFibSum[lessThanIndex - 1];
}

// Driver Code
int main()
{
    int arr[] = { 1, 2, 3, 4, 2, 7 };
    int n = sizeof(arr) / sizeof(arr[0]);

    // sort the array arr
    sort(arr, arr + n);

    // Build the prefix fibonacci sum array
    int* prefixFibSum =
         buildPrefixFibonacciSum(arr, n);

    // query array stores q queries
    int query[] = { 2, 6 };
    int q = sizeof(query) / sizeof(query[0]);

    for (int i = 0; i < q; i++) {
        int k = query[i];
        int ans =
            processQuery(arr, prefixFibSum, n, k);

        cout << "Query  " << i + 1 << " : "
             << ans << endl;
    }
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find fibonacci sum of
// subarray where all elements <= k
import java.util.*;

class GFG
{

    // Helper function that multiplies 2 matrices
    // F and M of size 2*2, and puts the multiplication
    // result back to F[][]
    static void multiply(int[][] F, int[][] M)
    {
        int x = F[0][0] * M[0][0] + F[0][1] * M[1][0];
        int y = F[0][0] * M[0][1] + F[0][1] * M[1][1];
        int z = F[1][0] * M[0][0] + F[1][1] * M[1][0];
        int w = F[1][0] * M[0][1] + F[1][1] * M[1][1];

        F[0][0] = x;
        F[0][1] = y;
        F[1][0] = z;
        F[1][1] = w;
    }

    /*
    * Helper function that calculates F[][]
    raise to the power n and puts the
    * result in F[][]
    */
    static void power(int[][] F, int n)
    {
        int i;
        int[][] M = { { 1, 1 }, { 1, 0 } };

        // n - 1 times multiply the
        // matrix to {{1, 0}, {0, 1}}
        for (i = 2; i <= n; i++)
            multiply(F, M);
    }

    // Returns the nth fibonacci number
    static int fib(int n)
    {
        int[][] F = { { 1, 1 }, { 1, 0 } };
        if (n == 0)
            return 0;
        power(F, n - 1);

        return F[0][0];
    }

    static int findLessThanK(int arr[], int n, int k)
    {
        // find first index which is > k
        // using lower_bound
        return (lower_bound(arr, 0, n, k + 1));
    }

    static int lower_bound(int[] a, int low,
                       int high, int element)
    {
        while (low < high)
        {
            int middle = low + (high - low) / 2;
            if (element > a[middle])
                low = middle + 1;
            else
                high = middle;
        }
        return low;
    }

    // Function to build Prefix Fibonacci Sum
    static int[] buildPrefixFibonacciSum(int arr[], int n)
    {
        // Allocate memory to prefix
        // fibonacci sum array
        int[] prefixFibSum = new int[n];

        // Traverse the array from 0 to n - 1,
        // when at the ith index then we calculate
        // the a[i]th fibonacci number and calculate
        // the fibonacci sum till the ith index as
        // the sum of fibonacci sum till index i - 1
        // and the a[i]th fibonacci number
        for (int i = 0; i < n; i++)
        {
            int currFibNumber = fib(arr[i]);
            if (i == 0)
            {
                prefixFibSum[i] = currFibNumber;
            }
            else
            {
                prefixFibSum[i] = prefixFibSum[i - 1] +
                                        currFibNumber;
            }
        }
        return prefixFibSum;
    }

    // Return the answer for each query
    static int processQuery(int arr[], int prefixFibSum[],
                                            int n, int k)
    {

        // index stores the index till where
        // the array elements are less than k
        int lessThanIndex = findLessThanK(arr, n, k);

        if (lessThanIndex == 0)
            return 0;
        return prefixFibSum[lessThanIndex - 1];
    }

    // Driver Code
    public static void main(String[] args)
    {
        int arr[] = { 1, 2, 3, 4, 2, 7 };
        int n = arr.length;

        // sort the array arr
        Arrays.sort(arr);

        // Build the prefix fibonacci sum array
        int[] prefixFibSum = buildPrefixFibonacciSum(arr, n);

        // query array stores q queries
        int query[] = { 2, 6 };
        int q = query.length;

        for (int i = 0; i < q; i++)
        {
            int k = query[i];
            int ans = processQuery(arr, prefixFibSum, n, k);

            System.out.print("Query " + (i + 1) + " : " + ans + "\n");
        }
    }
}

// This code is contributed by Rajput-Ji
```

## C#

```cpp
// C# program to find fibonacci sum of
// subarray where all elements <= k
using System;

class GFG
{

    // Helper function that multiplies 2 matrices
    // F and M of size 2*2, and puts the multiplication
    // result back to F[,]
    static void multiply(int[,] F, int[,] M)
    {
        int x = F[0, 0] * M[0, 0] + F[0, 1] * M[1, 0];
        int y = F[0, 0] * M[0, 1] + F[0, 1] * M[1, 1];
        int z = F[1, 0] * M[0, 0] + F[1, 1] * M[1, 0];
        int w = F[1, 0] * M[0, 1] + F[1, 1] * M[1, 1];

        F[0, 0] = x;
        F[0, 1] = y;
        F[1, 0] = z;
        F[1, 1] = w;
    }

    /*
    * Helper function that calculates F[,]
    raise to the power n and puts the
    * result in F[,]
    */
    static void power(int[,] F, int n)
    {
        int i;
        int[,] M = { { 1, 1 }, { 1, 0 } };

        // n - 1 times multiply the
        // matrix to {{1, 0}, {0, 1}}
        for (i = 2; i <= n; i++)
            multiply(F, M);
    }

    // Returns the nth fibonacci number
    static int fib(int n)
    {
        int[,] F = {{ 1, 1 }, { 1, 0 }};
        if (n == 0)
            return 0;
        power(F, n - 1);

        return F[0, 0];
    }

    static int findLessThanK(int []arr, int n, int k)
    {
        // find first index which is > k
        // using lower_bound
        return (lower_bound(arr, 0, n, k + 1));
    }

    static int lower_bound(int[] a, int low,
                    int high, int element)
    {
        while (low < high)
        {
            int middle = low + (high - low) / 2;
            if (element > a[middle])
                low = middle + 1;
            else
                high = middle;
        }
        return low;
    }

    // Function to build Prefix Fibonacci Sum
    static int[] buildPrefixFibonacciSum(int []arr, int n)
    {
        // Allocate memory to prefix
        // fibonacci sum array
        int[] prefixFibSum = new int[n];

        // Traverse the array from 0 to n - 1,
        // when at the ith index then we calculate
        // the a[i]th fibonacci number and calculate
        // the fibonacci sum till the ith index as
        // the sum of fibonacci sum till index i - 1
        // and the a[i]th fibonacci number
        for (int i = 0; i < n; i++)
        {
            int currFibNumber = fib(arr[i]);
            if (i == 0)
            {
                prefixFibSum[i] = currFibNumber;
            }
            else
            {
                prefixFibSum[i] = prefixFibSum[i - 1] +
                                        currFibNumber;
            }
        }
        return prefixFibSum;
    }

    // Return the answer for each query
    static int processQuery(int []arr, int []prefixFibSum,
                                            int n, int k)
    {

        // index stores the index till where
        // the array elements are less than k
        int lessThanIndex = findLessThanK(arr, n, k);

        if (lessThanIndex == 0)
            return 0;
        return prefixFibSum[lessThanIndex - 1];
    }

    // Driver Code
    public static void Main(String[] args)
    {
        int []arr = { 1, 2, 3, 4, 2, 7 };
        int n = arr.Length;

        // sort the array arr
        Array.Sort(arr);

        // Build the prefix fibonacci sum array
        int[] prefixFibSum = buildPrefixFibonacciSum(arr, n);

        // query array stores q queries
        int []query = {2, 6};
        int q = query.Length;

        for (int i = 0; i < q; i++)
        {
            int k = query[i];
            int ans = processQuery(arr, prefixFibSum, n, k);

            Console.Write("Query " + (i + 1) + " : " + ans + "\n");
        }
    }
}

// This code is contributed by PrinciRaj1992
```

## java 描述语言

```cpp
<script>
// Javascript program to find fibonacci sum of
// subarray where all elements <= k

// Helper function that multiplies 2 matrices
// F and M of size 2*2, and puts the multiplication
// result back to F[,]
function multiply(F, M) {
    let x = F[0][0] * M[0][0] + F[0][1] * M[1][0];
    let y = F[0][0] * M[0][1] + F[0][1] * M[1][1];
    let z = F[1][0] * M[0][0] + F[1][1] * M[1][0];
    let w = F[1][0] * M[0][1] + F[1][1] * M[1][1];

    F[0][0] = x;
    F[0][1] = y;
    F[1][0] = z;
    F[1][1] = w;
}

/*
* Helper function that calculates F[,]
raise to the power n and puts the
* result in F[,]
*/
function power(F, n) {
    let i;
    let M = [[1, 1], [1, 0]];

    // n - 1 times multiply the
    // matrix to {{1, 0}, {0, 1}}
    for (i = 2; i <= n; i++)
        multiply(F, M);
}

// Returns the nth fibonacci number
function fib(n) {
    let F = [[1, 1], [1, 0]];
    if (n == 0)
        return 0;
    power(F, n - 1);

    return F[0][0];
}

function findLessThanK(arr, n, k) {
    // find first index which is > k
    // using lower_bound
    return (lower_bound(arr, 0, n, k + 1));
}

function lower_bound(a, low, high, element) {
    while (low < high) {
        let middle = Math.floor(low + (high - low) / 2);
        if (element > a[middle])
            low = middle + 1;
        else
            high = middle;
    }
    return low;
}

// Function to build Prefix Fibonacci Sum
function buildPrefixFibonacciSum(arr, n) {
    // Allocate memory to prefix
    // fibonacci sum array
    let prefixFibSum = new Array(n);

    // Traverse the array from 0 to n - 1,
    // when at the ith index then we calculate
    // the a[i]th fibonacci number and calculate
    // the fibonacci sum till the ith index as
    // the sum of fibonacci sum till index i - 1
    // and the a[i]th fibonacci number
    for (let i = 0; i < n; i++) {
        let currFibNumber = fib(arr[i]);
        if (i == 0) {
            prefixFibSum[i] = currFibNumber;
        }
        else {
            prefixFibSum[i] = prefixFibSum[i - 1] +
                currFibNumber;
        }
    }
    return prefixFibSum;
}

// Return the answer for each query
function processQuery(arr, prefixFibSum, n, k) {

    // index stores the index till where
    // the array elements are less than k
    let lessThanIndex = findLessThanK(arr, n, k);

    if (lessThanIndex == 0)
        return 0;
    return prefixFibSum[lessThanIndex - 1];
}

// Driver Code

let arr = [1, 2, 3, 4, 2, 7];
let n = arr.length;

// sort the array arr
arr.sort((a, b) => a - b);

// Build the prefix fibonacci sum array
let prefixFibSum = buildPrefixFibonacciSum(arr, n);

// query array stores q queries
let query = [2, 6];
let q = query.length;

for (let i = 0; i < q; i++) {
    let k = query[i];
    let ans = processQuery(arr, prefixFibSum, n, k);

    document.write("Query " + (i + 1) + " : " + ans + "<br>");
}

// This code is contributed by gfgking

</script>
```

## 蟒蛇 3

```cpp
# Python3 program to find fibonacci sum of
# subarray where all elements <= k

from bisect import bisect

# Helper function that multiplies 2 matrices
# F and M of size 2*2, and puts the multiplication
# result back to F
def multiply(F, M):
    x = F[0][0] * M[0][0] + F[0][1] * M[1][0]
    y = F[0][0] * M[0][1] + F[0][1] * M[1][1]
    z = F[1][0] * M[0][0] + F[1][1] * M[1][0]
    w = F[1][0] * M[0][1] + F[1][1] * M[1][1]

    F[0][0] = x
    F[0][1] = y
    F[1][0] = z
    F[1][1] = w

# Helper function that calculates F
# raise to the power n and puts the
# result in F
def power(F, n):
    M = [[1, 1], [1, 0]]

    # n - 1 times multiply the
    # matrix to [[1, 0], [0, 1]]
    for i in range(1, n):
        multiply(F, M)

# Returns the nth fibonacci number
def fib(n):
    F = [[1, 1], [1, 0]]
    if (n == 0):
        return 0
    power(F, n - 1)

    return F[0][0]

def findLessThanK(arr, n, k):
    # find first index which is > k
    # using bisect
    return (bisect(arr, k))

#  Function to build Prefix Fibonacci Sum
def buildPrefixFibonacciSum(arr, n):
    # Allocate memory to prefix
    # fibonacci sum array
    prefixFibSum = [0]*n

    # Traverse the array from 0 to n - 1,
    # when at the ith index then we calculate
    # the a[i]th fibonacci number and calculate
    # the fibonacci sum till the ith index as
    # the sum of fibonacci sum till index i - 1
    # and the a[i]th fibonacci number
    for i in range(n):
        currFibNumber = fib(arr[i])
        if (i == 0):
            prefixFibSum[i] = currFibNumber
        else:
            prefixFibSum[i] = prefixFibSum[i - 1] + currFibNumber
    return prefixFibSum

# Return the answer for each query

def processQuery(arr, prefixFibSum, n, k):

    # index stores the index till where
    # the array elements are less than k
    lessThanIndex = findLessThanK(arr, n, k)

    if (lessThanIndex == 0):
        return 0
    return prefixFibSum[lessThanIndex - 1]

# Driver Code
if __name__ == '__main__':
    arr = [1, 2, 3, 4, 2, 7]
    n = len(arr)

    # sort the array arr
    arr.sort()

    # Build the prefix fibonacci sum array
    prefixFibSum = buildPrefixFibonacciSum(arr, n)

    # query array stores q queries
    query = [2, 6]
    q = len(query)

    for i in range(q):
        k = query[i]
        ans = processQuery(arr, prefixFibSum, n, k)

        print("Query  {} : {}".format(i+1, ans))

# This code is contributed by Amartya Ghosh
```

**Output:** 

```cpp
Query  1 : 3
Query  2 : 8
```

**时间复杂度:** O(nlogn + qlogn)
***辅助空间:** O(N)*
**方法二(离线查询):**
在离线查询中，按照特定的顺序存储查询并计算每个查询的答案，并按照原来指定的顺序存储和输出查询的结果。
将每个查询存储为一对整数，其中该对的第一个成员是该查询的查询参数 K，该对的第二个成员是查询最初发生的索引。
例如，如果查询如下:
查询 1:K = 13；
查询 2:K = 3；
查询 3:K = 8；
然后，将查询 1 存储为，其中 13 是该查询的 K 值，1 是指定它是 1 <sup>st</sup> 查询的索引，类似地，查询 2 和查询 3 分别表示为和。
曾经，所有的单个查询被表示为整数对，以递增的方式在 K 的基础上对查询对的数组进行排序。
例如，排序后的上述查询看起来像{3，8，13}。
**查询排序背后的思想:**
查询排序背后的主要思想是，当某个子集的元素对于某些查询 q <sub>i</sub> 小于 K 时，那么对于所有查询 q<sub>j</sub>I<j，从而 K <sub>i</sub> < = K <sub>j</sub> 这些元素都存在，因此如果元素数组和查询(按 K 排序)都被排序，那么在一个上维护两个指针
i，指向数组的 i <sup>第</sup>个索引，
j，指向查询数组的 j <sup>第</sup>个索引
然后，考虑以下伪代码:

```cpp
while (i <= query[j].K) {
     fibonacciSum  = fibonacciSum + a[i]th Fibonacci number
     i = i + 1
}
```

因此，当子集中的元素小于或等于当前查询对的第一个成员(即 K)时，继续前进到下一个元素，同时将所需的斐波那契数添加到当前总和中。一旦当前元素变得大于当前查询的参数 K，则将 sum 的当前值存储在大小为 q 的辅助数组 ans 中(即查询数)，该数组位于当前查询对的第 2 <sup>和第</sup>成员所指向的索引处(即当前查询发生的原始索引处)。

```cpp
ans[query[j].original index] = current value of fibonacciSum
```

最后，打印 ans 数组，该数组按照最初出现的顺序存储所有查询的结果。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to find fibonacci sum of
// subarray where all elements <= k
#include <bits/stdc++.h>

using namespace std;

// structure where K is the query parameter
// and original index is the index where the
// query was originally present at.
struct offlineQuery {
    int K, originalIndex;
};

// function tp compare queries
bool cmp(offlineQuery q1, offlineQuery q2)
{
    return q1.K < q2.K;
}

/* Helper function that multiplies 2 matrices
  F and M of size 2*2, and puts the multiplication
  result back to F[][] */
void multiply(int F[2][2], int M[2][2])
{
    int x = F[0][0] * M[0][0] + F[0][1] * M[1][0];
    int y = F[0][0] * M[0][1] + F[0][1] * M[1][1];
    int z = F[1][0] * M[0][0] + F[1][1] * M[1][0];
    int w = F[1][0] * M[0][1] + F[1][1] * M[1][1];

    F[0][0] = x;
    F[0][1] = y;
    F[1][0] = z;
    F[1][1] = w;
}

/* Helper function that calculates F[][] raise
   to the power n and puts the result in F[][]  */
void power(int F[2][2], int n)
{
    int i;
    int M[2][2] = { { 1, 1 }, { 1, 0 } };

    // n - 1 times multiply the
    // matrix to {{1, 0}, {0, 1}}
    for (i = 2; i <= n; i++)
        multiply(F, M);
}

// Returns the nth fibonacci number
int fib(int n)
{
    int F[2][2] = { { 1, 1 }, { 1, 0 } };
    if (n == 0)
        return 0;
    power(F, n - 1);

    return F[0][0];
}

// Return the answer for each query
int* processQuery(int arr[], int queries[],
                  int n, int q)
{
    // build offline queries where each query
    // is of type offlineQuery which stores
    // both K and original Index of the query
    // in the queries array
    offlineQuery* offlineQueries =
                  new offlineQuery[q];

    // Allocate memory to store ans of each query
    int* ans = new int[q];

    for (int i = 0; i < q; i++) {
        int original_index = i;
        int K = queries[i];
        offlineQueries[i].K = K;
        offlineQueries[i].originalIndex =
                          original_index;
    }

    // sort offlineQueries[]
    sort(offlineQueries, offlineQueries + q, cmp);

    // i is pointing to the current position
    // array arr fibonacciSum store the
    // fibonacciSum till ith index
    int i = 0, fibonacciSum = 0;

    for (int j = 0; j < q; j++)
    {
        int currK = offlineQueries[j].K;
        int currQueryIndex =
            offlineQueries[j].originalIndex;

        // keep insering elements to subset
        // while elements are less than
        // current query's K value
        while (i < n && arr[i] <= currK)
        {
            fibonacciSum += fib(arr[i]);
            i++ ;
        }

        // store the current value of
        // fibonacci sum in the array ans
        // which stores results for the
        // queries in the original order
        ans[currQueryIndex] = fibonacciSum;
    }

    return ans;
}

// Driver Code
int main()
{
    int arr[] = { 1, 2, 3, 4, 2, 7 };
    int n = sizeof(arr) / sizeof(arr[0]);

    // sort the array arr
    sort(arr, arr + n);

    // query array stores q queries
    int queries[] = { 2, 10, 6 };
    int q = sizeof(queries) / sizeof(queries[0]);

    // res stores the result of each query
    int* res = processQuery(arr, queries, n, q);

    for (int i = 0; i < q; i++) {
        int ans = res[i];
        cout << "Query  " << i + 1 << " : "
             << ans << endl;
    }
    return 0;
}
```

## 蟒蛇 3

```cpp
# Python3 program to find fibonacci sum of
# subarray where all elements <= k

from bisect import bisect

# Helper function that multiplies 2 matrices
# F and M of size 2*2, and puts the multiplication
# result back to F

def multiply(F, M):
    x = F[0][0] * M[0][0] + F[0][1] * M[1][0]
    y = F[0][0] * M[0][1] + F[0][1] * M[1][1]
    z = F[1][0] * M[0][0] + F[1][1] * M[1][0]
    w = F[1][0] * M[0][1] + F[1][1] * M[1][1]

    F[0][0] = x
    F[0][1] = y
    F[1][0] = z
    F[1][1] = w

# Helper function that calculates F
# raise to the power n and puts the
# result in F

def power(F, n):
    M = [[1, 1], [1, 0]]

    # n - 1 times multiply the
    # matrix to [[1, 0], [0, 1]]
    for i in range(1, n):
        multiply(F, M)

# Returns the nth fibonacci number

def fib(n):
    F = [[1, 1], [1, 0]]
    if (n == 0):
        return 0
    power(F, n - 1)

    return F[0][0]

# Return the answer for each query
def processQuery(arr, queries, n, q):
    # build offline queries where each query
    # is of type tuple which stores
    # both K and original Index of the query
    # in the queries array

    offlineQueries = [None]*q

    # Allocate memory to store ans of each query
    ans = [0]*q

    for i in range(q) :
        original_index = i
        K = queries[i]
        offlineQueries[i]= (K,original_index)

    # sort offlineQueries
    offlineQueries.sort()

    # i is pointing to the current position
    # array arr fibonacciSum store the
    # fibonacciSum till ith index
    i,fibonacciSum = 0,0

    for j in range(q):
        currK = offlineQueries[j][0]
        currQueryIndex =offlineQueries[j][1]

        # keep insering elements to subset
        # while elements are less than
        # current query's K value
        while (i < n and arr[i] <= currK):
            fibonacciSum += fib(arr[i])
            i+=1

        # store the current value of
        # fibonacci sum in the array ans
        # which stores results for the
        # queries in the original order
        ans[currQueryIndex] = fibonacciSum

    return ans

# Driver Code
if __name__ == '__main__':
    arr = [ 1, 2, 3, 4, 2, 7 ]
    n = len(arr)

    # sort the array arr
    arr.sort()

    # query array stores q queries
    queries = [ 2, 10, 6 ]
    q = len(queries)

    # res stores the result of each query
    res = processQuery(arr, queries, n, q)

    for i in range(q):
        ans = res[i]
        print("Query  {} : {}".format(i+1, ans))
```

**Output:** 

```cpp
Query  1 : 3
Query  2 : 21
Query  3 : 8
```

**时间复杂度:** O(nlogn + qlogq)
***辅助空间:** O(q)*