# 打印数组中所有可能的带素数异或的对

> 原文: [https://www.geeksforgeeks.org/print-all-possible-pair-with-prime-xor-in-the-array/](https://www.geeksforgeeks.org/print-all-possible-pair-with-prime-xor-in-the-array/)

给定一个 `N` 个正整数的数组 `arr[]`。任务是打印所有可能的对，使得它们的**异或**是一个素数。

**举例:**

> **输入:** `arr[] = {1, 3, 6, 11}`
> **输出:** `(1, 3) (1, 6) (3, 6) (6, 11)`
> **解释:**
> 以上对的异或:
> `1^3 = 2`
> `1^6 = 7`
> `3^6 = 5`
> `6^11 = 13`
> **输入:** `arr[] = { 22, 58, 63, 0 }`

**进场:**

1.  使用厄拉多塞的筛生成所有质数。
2.  对于给定数组中所有可能的对，检查该对的**异或**是否为素数。
3.  如果一对的**异或**是质数，则打印该对，否则检查下一对。

以下是上述方法的实现:

## C++ 实现

```cpp
// C++ implementation of the above approach
#include <bits/stdc++.h>
using namespace std;
const int sz = 1e5;
bool isPrime[sz + 1];

// Function for Sieve of Eratosthenes
void generatePrime()
{
    int i, j;
    memset(isPrime, true, sizeof(isPrime));

    isPrime[0] = isPrime[1] = false;

    for (i = 2; i * i <= sz; i++) {

        // If i is prime, then make all
        // multiples of i false
        if (isPrime[i]) {
            for (j = i * i; j < sz; j += i) {
                isPrime[j] = false;
            }
        }
    }
}

// Function to print all Pairs whose
// XOR is prime
void Pair_of_PrimeXor(int A[], int n)
{

    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {

            // if A[i]^A[j] is prime,
            // then print this pair
            if (isPrime[(A[i] ^ A[j])]) {

                cout << "(" << A[i]
                     << ", " << A[j] << ") ";
            }
        }
    }
}

// Driver Code
int main()
{
    int A[] = { 1, 3, 6, 11 };
    int n = sizeof(A) / sizeof(A[0]);

    // Generate all the prime number
    generatePrime();

    // Function Call
    Pair_of_PrimeXor(A, n);
    return 0;
}
```

## Java 实现

```java
// Java implementation of the above approach
class GFG
{
static int sz = (int) 1e5;
static boolean []isPrime = new boolean[sz + 1];

// Function for Sieve of Eratosthenes
static void generatePrime()
{
    int i, j;
    for (i = 2; i  <= sz; i++)
        isPrime[i] = true;

    for (i = 2; i * i <= sz; i++) {

        // If i is prime, then make all
        // multiples of i false
        if (isPrime[i]) {
            for (j = i * i; j < sz; j += i) {
                isPrime[j] = false;
            }
        }
    }
}

// Function to print all Pairs whose
// XOR is prime
static void Pair_of_PrimeXor(int A[], int n)
{

    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {

            // if A[i]^A[j] is prime,
            // then print this pair
            if (isPrime[(A[i] ^ A[j])]) {

                System.out.print("(" +  A[i]
                    + ", " +  A[j]+ ") ");
            }
        }
    }
}

// Driver Code
public static void main(String[] args)
{
    int A[] = { 1, 3, 6, 11 };
    int n = A.length;

    // Generate all the prime number
    generatePrime();

    // Function Call
    Pair_of_PrimeXor(A, n);
}
}

// This code is contributed by sapnasingh4991
```

## Python 实现

```python
# Python implementation of the above approach
sz = 10**5
isPrime = [True]*(sz + 1)

# Function for Sieve of Eratosthenes
def generatePrime():
    i, j = 0, 0
    isPrime[0] = isPrime[1] = False

    for i in range(2, sz + 1):
        if i * i > sz:
            break

        # If i is prime, then make all
        # multiples of i false
        if (isPrime[i]):
            for j in range(i*i, sz, i):
                isPrime[j] = False

# Function to print all Pairs whose
# XOR is prime
def Pair_of_PrimeXor(A, n):

    for i in range(n):
        for j in range(i + 1, n):

            # if A[i]^A[j] is prime,
            # then print this pair
            if (isPrime[(A[i] ^ A[j])]):

                print("(",A[i],",",A[j],")",end=" ")

# Driver Code
if __name__ == '__main__':
    A = [1, 3, 6, 11]
    n =len(A)

    # Generate all the prime number
    generatePrime()

    # Function Call
    Pair_of_PrimeXor(A, n)

# This code is contributed by mohit kumar 29
```

## C# 实现

```csharp
// C# implementation of the above approach
using System;

class GFG
{
static int sz = (int) 1e5;
static bool []isPrime = new bool[sz + 1];

// Function for Sieve of Eratosthenes
static void generatePrime()
{
    int i, j;
    for (i = 2; i  <= sz; i++)
        isPrime[i] = true;

    for (i = 2; i * i <= sz; i++) {

        // If i is prime, then make all
        // multiples of i false
        if (isPrime[i]) {
            for (j = i * i; j < sz; j += i) {
                isPrime[j] = false;
            }
        }
    }
}

// Function to print all Pairs whose
// XOR is prime
static void Pair_of_PrimeXor(int []A, int n)
{

    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {

            // if A[i]^A[j] is prime,
            // then print this pair
            if (isPrime[(A[i] ^ A[j])]) {

                Console.Write("(" +  A[i]
                    + ", " +  A[j]+ ") ");
            }
        }
    }
}

// Driver Code
public static void Main(String[] args)
{
    int []A = { 1, 3, 6, 11 };
    int n = A.Length;

    // Generate all the prime number
    generatePrime();

    // Function Call
    Pair_of_PrimeXor(A, n);
}
}

// This code is contributed by Rajput-Ji
```

## JavaScript 实现

```javascript
<script>

// Javascript implementation of
// the above approach

const sz = 100000;
let isPrime = new Array(sz + 1).fill(true);

// Function for Sieve of Eratosthenes
function generatePrime()
{
    let i, j;

    isPrime[0] = isPrime[1] = false;

    for (i = 2; i * i <= sz; i++) {

        // If i is prime, then make all
        // multiples of i false
        if (isPrime[i]) {
            for (j = i * i; j < sz; j += i) {
                isPrime[j] = false;
            }
        }
    }
}

// Function to print all Pairs whose
// XOR is prime
function Pair_of_PrimeXor(A, n)
{

    for (let i = 0; i < n; i++) {
        for (let j = i + 1; j < n; j++) {

            // if A[i]^A[j] is prime,
            // then print this pair
            if (isPrime[(A[i] ^ A[j])]) {

                document.write("(" + A[i]
                     + ", " + A[j] + ") ");
            }
        }
    }
}

// Driver Code
    let A = [ 1, 3, 6, 11 ];
    let n = A.length;

    // Generate all the prime number
    generatePrime();

    // Function Call
    Pair_of_PrimeXor(A, n);

</script>
```

**输出:**

```
(1, 3) (1, 6) (3, 6) (6, 11)
```

**时间复杂度:** `O(N^2)`，其中 `N` 为给定数组的长度。

**辅助空间:** `O(sz)`