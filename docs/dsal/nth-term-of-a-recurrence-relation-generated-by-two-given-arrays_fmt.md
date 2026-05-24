# 由两个给定数组生成的递归关系的第 n 项

> 原文: [https://www.geeksforgeeks.org/nth-term-of-a-recurrence-relation-generated-by-two-given-arrays/](https://www.geeksforgeeks.org/nth-term-of-a-recurrence-relation-generated-by-two-given-arrays/)

给定一个整数 `N` 和两个大小为 `K` 的数组 `F[]` 和 `C[]`，分别表示下面递推关系的第一个 `K` 项和第一个 `K` 项的系数。

> `F_N = C_1 * F_{N–1} + C_2 * F_{N–2} + C_3 * F_{N–3} + … + C_K * F_{N–K}`。

任务是找到递归关系的第 n 项。由于数量可能很大，取模至 `10^9 + 7`。

## 示例

**输入:** `N = 10`，`K = 2`，`F[] = {0, 1}`，`C[] = {1, 1}`
**输出:** `55`
**解释:**
递推关系为 `F_N = F_{N–1} + F_{N–2}`，且 `F_0 = 0`，`F_1 = 1`。
该系列的剩余项可以计算为先前的 `K` 项的和，并与存储在 `C[]` 中的系数进行相应的相乘。
因此，`F_10 = 55`。

**输入:** `N = 5`，`K = 3`，`F[] = {1, 2, 3}`，`C[] = {1, 1, 1}`
**输出:** `20`
**解释:**
上述递推关系的顺序为 1, 2, 3, 6, 11, 20, 37, 68, …。
每下一项都是前 (`K = 3`) 项的和，基础条件 `F_0 = 1`，`F_1 = 2`，`F_2 = 3`。
因此，`F_5 = 20`。

## 暴力方法

想法是通过在先前的 `K` 项的帮助下计算每个项，使用给定的[递归关系](https://www.geeksforgeeks.org/different-types-recurrence-relations-solutions/)生成序列。序列形成后，打印第 `N` 项。

下面是上述方法的实现：

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

int mod = 1e9 + 7;

// Function to calculate Nth term of
// general recurrence relations
void NthTerm(int F[], int C[], int K, int n)
{
    // Stores the generated sequence
    int ans[n + 1] = { 0 };

    for (int i = 0; i < K; i++)
        ans[i] = F[i];

    for (int i = K; i <= n; i++) {
        for (int j = i - K; j < i; j++) {
            // Current term is sum of
            // previous k terms
            ans[i] += ans[j];
            ans[i] %= mod;
        }
    }

    // Print the nth term
    cout << ans[n] << endl;
}

// Driver Code
int main()
{
    // Given Array F[] and C[]
    int F[] = { 0, 1 };
    int C[] = { 1, 1 };

    // Given N and K
    int K = 2;
    int N = 10;

    // Function Call
    NthTerm(F, C, K, N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.util.*;
import java.lang.*;

class GFG{

static double mod = 1e9 + 7;

// Function to calculate Nth term of
// general recurrence relations
static void NthTerm(int F[], int C[], int K, int n)
{
    // Stores the generated sequence
    int ans[] = new int[n + 1 ];

    for(int i = 0; i < K; i++)
        ans[i] = F[i];

    for(int i = K; i <= n; i++)
    {
        for(int j = i - K; j < i; j++)
        {
            // Current term is sum of
            // previous k terms
            ans[i] += ans[j];
            ans[i] %= mod;
        }
    }

    // Print the nth term
    System.out.println(ans[n]);
}

// Driver Code
public static void main (String[] args)
{
    // Given Array F[] and C[]
    int F[] = { 0, 1 };
    int C[] = { 1, 1 };

    // Given N and K
    int K = 2;
    int N = 10;

    // Function call
    NthTerm(F, C, K, N);
}
}

// This code is contributed by jana_sayantan
```

### Python 3

```python
# Python3 program for the above approach
mod = 1e9 + 7

# Function to calculate Nth term of
# general recurrence relations
def NthTerm(F, C, K, n):
    # Stores the generated sequence
    ans = [0] * (n + 1)

    i = 0
    while i < K:
        ans[i] = F[i]
        i += 1

    i = K
    while i <= n:
        j = i - K
        while j < i:
            # Current term is sum of
            # previous k terms
            ans[i] += ans[j]
            ans[i] %= mod
            j += 1
        i += 1

    # Print the nth term
    print(int(ans[n]))

# Driver code
if __name__ == '__main__':
    # Given Array F[] and C[]
    F = [ 0, 1 ]
    C = [ 1, 1 ]

    # Given N and K
    K = 2
    N = 10

    # Function call
    NthTerm(F, C, K, N)

# This code is contributed by jana_sayantan
```

### C#

```csharp
// C# program for the above approach
using System;
class GFG{

static double mod = 1e9 + 7;

// Function to calculate Nth term of
// general recurrence relations
static void NthTerm(int [] F, int [] C, int K, int n)
{
    // Stores the generated sequence
    int []ans = new int[n + 1];

    for(int i = 0; i < K; i++)
        ans[i] = F[i];

    for(int i = K; i <= n; i++)
    {
        for(int j = i - K; j < i; j++)
        {
            // Current term is sum of
            // previous k terms
            ans[i] += ans[j];
            ans[i] %= (int)mod;
        }
    }

    // Print the nth term
    Console.WriteLine(ans[n]);
}

// Driver Code
public static void Main (String[] args)
{
    // Given Array F[] and C[]
    int [] F= {0, 1};
    int [] C= {1, 1};

    // Given N and K
    int K = 2;
    int N = 10;

    // Function call
    NthTerm(F, C, K, N);
}
}

// This code is contributed by jana_sayantan
```

### JavaScript

```javascript
<script>
// JavaScript program for the above approach
let mod = 1e9 + 7;

// Function to calculate Nth term of
// general recurrence relations
function NthTerm(F, C, K, n)
{
    // Stores the generated sequence
    let ans = new Uint8Array(n + 1);

    for (let i = 0; i < K; i++)
        ans[i] = F[i];

    for (let i = K; i <= n; i++) {
        for (let j = i - K; j < i; j++) {
            // Current term is sum of
            // previous k terms
            ans[i] += ans[j];
            ans[i] %= mod;
        }
    }

    // Print the nth term
    document.write(ans[n] + "<br>");
}

// Driver Code
    // Given Array F[] and C[]
    let F = [ 0, 1 ];
    let C = [ 1, 1 ];

    // Given N and K
    let K = 2;
    let N = 10;

    // Function Call
    NthTerm(F, C, K, N);

// This code is contributed by Surbhi Tyagi.
</script>
```

**输出:**

```
55
```

**时间复杂度:** `O(N^2)`
**辅助空间:** `O(N)`

## 有效方法

递归关系的第 `N` 项可以通过使用[矩阵求幂](https://www.geeksforgeeks.org/matrix-exponentiation/)来找到。以下是步骤：

*   让我们将初始状态视为：
    > `F = [f_0, f_1, f_2, ..., f_{k-1}]`
*   将尺寸为 `K^2` 的矩阵定义为：
    > `T = [[0, 0, 0, ..., C_k],`
    > `[1, 0, 0, ..., C_{k-1}],`
    > `[0, 1, 0, ..., C_{k-2}],`
    > `[...],`
    > `[0, 0, 0, ..., C_2],`
    > `[0, 0, 0, ..., 1, C_1]]`
*   使用[二进制幂](https://www.geeksforgeeks.org/modular-exponentiation-power-in-modular-arithmetic/)计算矩阵 `T[][]` 的第 n 次幂。
*   现在，将 `F[]` 乘以 `T[][]` 的 n 次方得出：
    > `F * T^N = [F_N, F_{N+1}, F_{N+2}, ..., F_{N+K}]`
*   结果矩阵的第一项 `F * T^N` 是要求的结果。

以下是上述方法的实现：

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

int mod = 1e9 + 7;

// Declare T[][] as global matrix
int T[2000][2000];

// Result matrix
int result[2000][2000];

// Function to multiply two matrices
void mul_2(int K)
{
    // Create an auxiliary matrix to
    // store elements of the
    // multiplication matrix
    int temp[K + 1][K + 1];
    memset(temp, 0, sizeof temp);

    // Iterate over range [0, K]
    for (int i = 1; i <= K; i++) {

        for (int j = 1; j <= K; j++) {

            for (int k = 1; k <= K; k++) {

                // Update temp[i][j]
                temp[i][j]
                    = (temp[i][j]
                       + (T[i][k] * T[k][j])
                             % mod)
                      % mod;
            }
        }
    }

    // Update the final matrix
    for (int i = 1; i <= K; i++) {
        for (int j = 1; j <= K; j++) {
            T[i][j] = temp[i][j];
        }
    }
}

// Function to multiply two matrices
void mul_1(int K)
{
    // Create an auxiliary matrix to
    // store elements of the
    // multiplication matrix
    int temp[K + 1][K + 1];
    memset(temp, 0, sizeof temp);

    // Iterate over range [0, K]
    for (int i = 1; i <= K; i++) {

        for (int j = 1; j <= K; j++) {

            for (int k = 1; k <= K; k++) {

                // Update temp[i][j]
                temp[i][j]
                    = (temp[i][j]
                       + (result[i][k] * T[k][j])
                             % mod)
                      % mod;
            }
        }
    }

    // Update the final matrix
    for (int i = 1; i <= K; i++) {
        for (int j = 1; j <= K; j++) {
            result[i][j] = temp[i][j];
        }
    }
}

// Function to calculate matrix^n
// using binary exponentaion
void matrix_pow(int K, int n)
{
    // Initialize result matrix
    // and unity matrix
    for (int i = 1; i <= K; i++) {
        for (int j = 1; j <= K; j++) {
            if (i == j)
                result[i][j] = 1;
        }
    }

    while (n > 0) {
        if (n % 2 == 1)
            mul_1(K);
        mul_2(K);
        n /= 2;
    }
}

// Function to calculate nth term
// of general recurrence
int NthTerm(int F[], int C[], int K,
            int n)
{

    // Fill T[][] with appropriate value
    for (int i = 1; i <= K; i++)
        T[i][K] = C[K - i];

    for (int i = 1; i <= K; i++)
        T[i + 1][i] = 1;

    // Function Call to calculate T^n
    matrix_pow(K, n);

    int answer = 0;

    // Calculate nth term as first
    // element of F*(T^n)
    for (int i = 1; i <= K; i++) {
        answer += F[i - 1] * result[i][1];
    }

    // Print the result
    cout << answer << endl;
    return 0;
}

// Driver Code
int main()
{
    // Given Initial terms
    int F[] = { 1, 2, 3 };

    // Given coefficients
    int C[] = { 1, 1, 1 };

    // Given K
    int K = 3;

    // Given N
    int N = 10;

    // Function Call
    NthTerm(F, C, K, N);

    return 0;
}
```

## Java

```java
// Java program for
// the above approach
import java.util.*;
class GFG{

static int mod = (int) (1e9 + 7);

// Declare T[][] as global matrix
static int [][]T = new int[2000][2000];

// Result matrix
static int [][]result = new int[2000][2000];

// Function to multiply two matrices
static void mul_2(int K)
{
  // Create an auxiliary matrix to
  // store elements of the
  // multiplication matrix
  int [][]temp = new int[K + 1][K + 1];

  // Iterate over range [0, K]
  for (int i = 1; i <= K; i++)
  {
    for (int j = 1; j <= K; j++)
    {
      for (int k = 1; k <= K; k++)
      {
        // Update temp[i][j]
        temp[i][j] = (temp[i][j] +
                     (T[i][k] * T[k][j]) %
                      mod) % mod;
      }
    }
  }

  // Update the final matrix
  for (int i = 1; i <= K; i++)
  {
    for (int j = 1; j <= K; j++)
    {
      T[i][j] = temp[i][j];
    }
  }
}

// Function to multiply two matrices
static void mul_1(int K)
{
  // Create an auxiliary matrix to
  // store elements of the
  // multiplication matrix
  int [][]temp = new int[K + 1][K + 1];

  // Iterate over range [0, K]
  for (int i = 1; i <= K; i++)
  {
    for (int j = 1; j <= K; j++)
    {
      for (int k = 1; k <= K; k++)
      {
        // Update temp[i][j]
        temp[i][j] = (temp[i][j] +
                     (result[i][k] * T[k][j]) %
                      mod) % mod;
      }
    }
  }

  // Update the final matrix
  for (int i = 1; i <= K; i++)
  {
    for (int j = 1; j <= K; j++)
    {
      result[i][j] = temp[i][j];
    }
  }
}

// Function to calculate matrix^n
// using binary exponentaion
static void matrix_pow(int K, int n)
{
  // Initialize result matrix
  // and unity matrix
  for (int i = 1; i <= K; i++)
  {
    for (int j = 1; j <= K; j++)
    {
      if (i == j)
        result[i][j] = 1;
    }
  }

  while (n > 0)
  {
    if (n % 2 == 1)
      mul_1(K);
    mul_2(K);
    n /= 2;
  }
}

// Function to calculate nth term
// of general recurrence
static int NthTerm(int F[], int C[],
                   int K, int n)
{
  // Fill T[][] with appropriate value
  for (int i = 1; i <= K; i++)
    T[i][K] = C[K - i];

  for (int i = 1; i <= K; i++)
    T[i + 1][i] = 1;

  // Function Call to calculate T^n
  matrix_pow(K, n);

  int answer = 0;

  // Calculate nth term as first
  // element of F * (T ^ n)
  for (int i = 1; i <= K; i++)
  {
    answer += F[i - 1] * result[i][1];
  }

  // Print the result
  System.out.print(answer + "\n");
  return 0;
}

// Driver Code
public static void main(String[] args)
{
  // Given Initial terms
  int F[] = {1, 2, 3};

  // Given coefficients
  int C[] = {1, 1, 1};

  // Given K
  int K = 3;

  // Given N
  int N = 10;

  // Function Call
  NthTerm(F, C, K, N);
}
}

// This code is contributed by 29AjayKumar
```

# 使用矩阵快速幂计算线性递推数列的第N项

## 蟒蛇 3

```python
# Python3 program for
# the above approach
mod = 1e9 + 7

# Declare T[][] as global matrix
T = [[0 for x in range (2000)]
        for y in range (2000)]

# Result matrix
result = [[0 for x in range (2000)]
             for y in range (2000)]

# Function to multiply two matrices
def mul_2(K):

    # Create an auxiliary matrix to
    # store elements of the
    # multiplication matrix
    temp = [[0 for x in range (K + 1)]
               for y in range (K + 1)]

    # Iterate over range [0, K]
    for i in range (1, K + 1):
        for j in range (1, K + 1):
            for k in range (1, K + 1):

                # Update temp[i][j]
                temp[i][j] = ((temp[i][j] +
                              (T[i][k] * T[k][j]) %
                               mod) % mod)

    # Update the final matrix
    for i in range (1, K + 1):
        for j in range (1, K + 1):
            T[i][j] = temp[i][j]

# Function to multiply two matrices
def mul_1(K):

    # Create an auxiliary matrix to
    # store elements of the
    # multiplication matrix
    temp = [[0 for x in range (K + 1)]
               for y in range (K + 1)]

    # Iterate over range [0, K]
    for i in range (1, K + 1):
        for j in range (1, K + 1):
            for k in range (1, K + 1):

                # Update temp[i][j]
                temp[i][j] = ((temp[i][j] +
                              (result[i][k] * T[k][j]) %
                               mod) % mod)

    # Update the final matrix
    for i in range (1, K + 1):
        for j in range (1, K + 1):
            result[i][j] = temp[i][j]

# Function to calculate matrix^n
# using binary exponentaion
def matrix_pow(K, n):

    # Initialize result matrix
    # and unity matrix
    for i in range (1, K + 1):
        for j in range (1, K + 1):
            if (i == j):
                result[i][j] = 1

    while (n > 0):
        if (n % 2 == 1):
            mul_1(K)
        mul_2(K)
        n //= 2

# Function to calculate nth term
# of general recurrence
def NthTerm(F, C, K, n):

    # Fill T[][] with appropriate value
    for i in range (1, K + 1):
        T[i][K] = C[K - i]

    for i in range (1, K + 1):
        T[i + 1][i] = 1

    # Function Call to calculate T^n
    matrix_pow(K, n)

    answer = 0

    # Calculate nth term as first
    # element of F*(T^n)
    for i in range (1, K + 1):
        answer += F[i - 1] * result[i][1]

    # Print the result
    print(int(answer))

# Driver Code
if __name__ == "__main__":

    # Given Initial terms
    F = [1, 2, 3]

    # Given coefficients
    C = [1, 1, 1]

    # Given K
    K = 3

    # Given N
    N = 10

    # Function Call
    NthTerm(F, C, K, N)

# This code is contributed by Chitranayal
```

## C\#

```csharp
// C# program for
// the above approach
using System;
class GFG{

static int mod = (int) (1e9 + 7);

// Declare T[,] as global matrix
static int [,]T = new int[2000, 2000];

// Result matrix
static int [,]result = new int[2000, 2000];

// Function to multiply two matrices
static void mul_2(int K)
{
  // Create an auxiliary matrix to
  // store elements of the
  // multiplication matrix
  int [,]temp = new int[K + 1,
                        K + 1];

  // Iterate over range [0, K]
  for (int i = 1; i <= K; i++)
  {
    for (int j = 1; j <= K; j++)
    {
      for (int k = 1; k <= K; k++)
      {
        // Update temp[i,j]
        temp[i, j] = (temp[i, j] +
                     (T[i, k] * T[k, j]) %
                      mod) % mod;
      }
    }
  }

  // Update the readonly matrix
  for (int i = 1; i <= K; i++)
  {
    for (int j = 1; j <= K; j++)
    {
      T[i, j] = temp[i, j];
    }
  }
}

// Function to multiply two matrices
static void mul_1(int K)
{
  // Create an auxiliary matrix to
  // store elements of the
  // multiplication matrix
  int [,]temp = new int[K + 1,
                        K + 1];

  // Iterate over range [0, K]
  for (int i = 1; i <= K; i++)
  {
    for (int j = 1; j <= K; j++)
    {
      for (int k = 1; k <= K; k++)
      {
        // Update temp[i,j]
        temp[i,j] = (temp[i, j] +
                    (result[i, k] * T[k, j]) %
                     mod) % mod;
      }
    }
  }

  // Update the readonly matrix
  for (int i = 1; i <= K; i++)
  {
    for (int j = 1; j <= K; j++)
    {
      result[i, j] = temp[i, j];
    }
  }
}

// Function to calculate matrix^n
// using binary exponentaion
static void matrix_pow(int K, int n)
{
  // Initialize result matrix
  // and unity matrix
  for (int i = 1; i <= K; i++)
  {
    for (int j = 1; j <= K; j++)
    {
      if (i == j)
        result[i, j] = 1;
    }
  }

  while (n > 0)
  {
    if (n % 2 == 1)
      mul_1(K);
    mul_2(K);
    n /= 2;
  }
}

// Function to calculate nth term
// of general recurrence
static int NthTerm(int []F, int []C,
                   int K, int n)
{
  // Fill T[,] with appropriate value
  for (int i = 1; i <= K; i++)
    T[i, K] = C[K - i];

  for (int i = 1; i <= K; i++)
    T[i + 1, i] = 1;

  // Function Call to calculate T^n
  matrix_pow(K, n);

  int answer = 0;

  // Calculate nth term as first
  // element of F * (T ^ n)
  for (int i = 1; i <= K; i++)
  {
    answer += F[i - 1] * result[i, 1];
  }

  // Print the result
  Console.Write(answer + "\n");
  return 0;
}

// Driver Code
public static void Main(String[] args)
{
  // Given Initial terms
  int []F = {1, 2, 3};

  // Given coefficients
  int []C = {1, 1, 1};

  // Given K
  int K = 3;

  // Given N
  int N = 10;

  // Function Call
  NthTerm(F, C, K, N);
}
}

// This code is contributed by Rajput-Ji
```

# JavaScript 实现

```javascript
<script>
    // Javascript program for the above approach

    let mod = (1e9 + 7);

    // Declare T[][] as global matrix
    let T = new Array(2000);

    // Result matrix
    let result = new Array(2000);

    for (let i = 0; i < 2000; i++)
    {
        T[i] = new Array(2000);
        result[i] = new Array(2000);
        for (let j = 0; j < 2000; j++)
        {
            T[i][j] = 0;
            result[i][j] = 0;
        }
    }

    // Function to multiply two matrices
    function mul_2(K)
    {
      // Create an auxiliary matrix to
      // store elements of the
      // multiplication matrix
      let temp = new Array(K + 1);
      for (let i = 0; i <= K; i++)
      {
          temp[i] = new Array(K + 1);
        for (let j = 0; j <= K; j++)
        {
            temp[i][j] = 0;
        }
      }

      // Iterate over range [0, K]
      for (let i = 1; i <= K; i++)
      {
        for (let j = 1; j <= K; j++)
        {
          for (let k = 1; k <= K; k++)
          {
            // Update temp[i][j]
            temp[i][j] = (temp[i][j] +
                         (T[i][k] * T[k][j]) %
                          mod) % mod;
          }
        }
      }

      // Update the final matrix
      for (let i = 1; i <= K; i++)
      {
        for (let j = 1; j <= K; j++)
        {
          T[i][j] = temp[i][j];
        }
      }
    }

    // Function to multiply two matrices
    function mul_1(K)
    {
      // Create an auxiliary matrix to
      // store elements of the
      // multiplication matrix
      let temp = new Array(K + 1);
      for (let i = 0; i <= K; i++)
      {
          temp[i] = new Array(K + 1);
        for (let j = 0; j <= K; j++)
        {
            temp[i][j] = 0;
        }
      }

      // Iterate over range [0, K]
      for (let i = 1; i <= K; i++)
      {
        for (let j = 1; j <= K; j++)
        {
          for (let k = 1; k <= K; k++)
          {
            // Update temp[i][j]
            temp[i][j] = (temp[i][j] +
                         (result[i][k] * T[k][j]) %
                          mod) % mod;
          }
        }
      }

      // Update the final matrix
      for (let i = 1; i <= K; i++)
      {
        for (let j = 1; j <= K; j++)
        {
          result[i][j] = temp[i][j];
        }
      }
    }

    // Function to calculate matrix^n
    // using binary exponentaion
    function matrix_pow(K, n)
    {
      // Initialize result matrix
      // and unity matrix
      for (let i = 1; i <= K; i++)
      {
        for (let j = 1; j <= K; j++)
        {
          if (i == j)
            result[i][j] = 1;
        }
      }

      while (n > 0)
      {
        if (n % 2 == 1)
          mul_1(K);
        mul_2(K);
        n = parseInt(n / 2, 10);
      }
    }

    // Function to calculate nth term
    // of general recurrence
    function NthTerm(F, C, K, n)
    {
      // Fill T[][] with appropriate value
      for (let i = 1; i <= K; i++)
        T[i][K] = C[K - i];

      for (let i = 1; i <= K; i++)
        T[i + 1][i] = 1;

      // Function Call to calculate T^n
      matrix_pow(K, n);

      let answer = 0;

      // Calculate nth term as first
      // element of F * (T ^ n)
      for (let i = 1; i <= K; i++)
      {
        answer += F[i - 1] * result[i][1];
      }

      // Print the result
      document.write(answer + "</br>");
      return 0;
    }

    // Given Initial terms
    let F = [1, 2, 3];

    // Given coefficients
    let C = [1, 1, 1];

    // Given K
    let K = 3;

    // Given N
    let N = 10;

    // Function Call
    NthTerm(F, C, K, N);

// This code is contributed by mukesh07.
</script>
```

`Output:`

```

```

`时间复杂度:` `O(K^3 log(N))`
`辅助空间:` `O(K*K)`