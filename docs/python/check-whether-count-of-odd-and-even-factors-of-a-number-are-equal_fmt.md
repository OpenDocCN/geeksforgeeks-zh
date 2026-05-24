# 检查一个数的奇数和偶数因子的计数是否相等

> 原文: [https://www.geeksforgeeks.org/check-whether-count-of-odd-and-even-factors-of-a-number-are-equal/](https://www.geeksforgeeks.org/check-whether-count-of-odd-and-even-factors-of-a-number-are-equal/)

给定一个数字 `N`，任务是找出 `N` 是否有相等数量的奇偶因子。

**例:**

> **输入:** `N = 10`
> **输出:** YES
> **解释:** 10 有两个奇数因子(1 和 5)和两个偶数因子(2 和 10)
> **输入:** `N = 24`
> **输出:** NO
> **解释:** 24 有两个奇数因子(1 和 3)和六个偶数因子(2、4、6、8、12 和 24)

**天真的做法:** [找出所有的除数](https://www.geeksforgeeks.org/find-all-divisors-of-a-natural-number-set-2/)检查奇数除数和偶数除数的计数是否相同。以下是上述办法的实施情况。

## C++

```cpp
// C++ solution for the above approach
#include <bits/stdc++.h>
using namespace std;
#define lli long long int

// Function to check condition
void isEqualFactors(lli N)
{
    // Initialize even_count
    // and od_count
    lli ev_count = 0, od_count = 0;

    // loop runs till square root
    for (lli i = 1;
         i <= sqrt(N) + 1; i++) {

        if (N % i == 0) {
            if (i == N / i) {
                if (i % 2 == 0)
                    ev_count += 1;
                else
                    od_count += 1;
            }

            else {
                if (i % 2 == 0)
                    ev_count += 1;
                else
                    od_count += 1;

                if ((N / i) % 2 == 0)
                    ev_count += 1;

                else
                    od_count += 1;
            }
        }
    }

    if (ev_count == od_count)
        cout << "YES" << endl;
    else
        cout << "NO" << endl;
}

// Driver Code
int main()
{
    lli N = 10;
    isEqualFactors(N);

    return 0;
}
```

## Java

```java
// Java solution for the above approach
class GFG{

// Function to check condition
static void isEqualFactors(int N)
{

    // Initialize even_count
    // and od_count
    int ev_count = 0, od_count = 0;

    // Loop runs till square root
    for(int i = 1;
            i <= Math.sqrt(N) + 1; i++)
    {
       if (N % i == 0)
       {
           if (i == N / i)
           {
               if (i % 2 == 0)
                   ev_count += 1;
               else
                   od_count += 1;
           }
           else
           {
               if (i % 2 == 0)
                   ev_count += 1;
               else
                   od_count += 1;

               if ((N / i) % 2 == 0)
                   ev_count += 1;
               else
                   od_count += 1;
           }
       }
    }

    if (ev_count == od_count)
        System.out.print("YES" + "\n");
    else
        System.out.print("NO" + "\n");
}

// Driver Code
public static void main(String[] args)
{
    int N = 10;

    isEqualFactors(N);
}
}

// This code is contributed by amal kumar choubey
```

## Python 3

```python
# Python3 code for the naive approach
import math

# Function to check condition
def isEqualFactors(N):

    # Initialize even_count
    # and od_count
    ev_count = 0
    od_count = 0

    # loop runs till square root
    for i in range(1, (int)(math.sqrt(N)) + 2) :
        if (N % i == 0):
            if(i == N // i):
                if(i % 2 == 0):
                    ev_count += 1
                else:
                    od_count += 1

            else:
                if(i % 2 == 0):
                    ev_count += 1
                else:
                    od_count += 1

                if((N // i) % 2 == 0):
                    ev_count += 1;
                else:
                    od_count += 1;

    if (ev_count == od_count):
        print("YES")
    else:
        print("NO")

# Driver Code
N = 10
isEqualFactors(N)
```

## C#

```csharp
// C# solution for the above approach
using System;

class GFG{

// Function to check condition
static void isEqualFactors(int N)
{

    // Initialize even_count
    // and od_count
    int ev_count = 0, od_count = 0;

    // Loop runs till square root
    for(int i = 1;
            i <= Math.Sqrt(N) + 1; i++)
    {
        if (N % i == 0)
        {
            if (i == N / i)
            {
                if (i % 2 == 0)
                    ev_count += 1;
                else
                    od_count += 1;
            }
            else
            {
                if (i % 2 == 0)
                    ev_count += 1;
                else
                    od_count += 1;

                if ((N / i) % 2 == 0)
                    ev_count += 1;
                else
                    od_count += 1;
            }
        }
    }

    if (ev_count == od_count)
        Console.Write("YES" + "\n");
    else
        Console.Write("NO" + "\n");
}

// Driver Code
public static void Main(String[] args)
{
    int N = 10;

    isEqualFactors(N);
}
}

// This code is contributed by gauravrajput1
```

## JavaScript

```javascript
<script>
// Javascript program for the above approach

// Function to check condition
function isEqualFactors(N)
{

    // Initialize even_count
    // and od_count
    let ev_count = 0, od_count = 0;

    // Loop runs till square root
    for(let i = 1;
            i <= Math.sqrt(N) + 1; i++)
    {
       if (N % i == 0)
       {
           if (i == N / i)
           {
               if (i % 2 == 0)
                   ev_count += 1;
               else
                   od_count += 1;
           }
           else
           {
               if (i % 2 == 0)
                   ev_count += 1;
               else
                   od_count += 1;

               if ((N / i) % 2 == 0)
                   ev_count += 1;
               else
                   od_count += 1;
           }
       }
    }

    if (ev_count == od_count)
        document.write("YES" + "\n");
    else
        document.write("NO" + "\n");
}

    // Driver Code

    let N = 10;

    isEqualFactors(N);

</script>
```

**Output:**

```
YES
```

**时间复杂度:** `O(sqrt(N))`
**辅助空间:** `O(1)`

## 高效解决方案

必须进行以下观察以优化上述方法:

*   根据**唯一因式分解定理**，任何数都可以用素数幂的乘积来表示。所以，`N` 可以表示为:
    > `N = P1^A1 * P2^A2 * P3^A3 * ….. * PK^AK`，其中，每个 `Pi` 为素数，每个 `Ai` 为正整数 (`1 <= i <= K`)。

*   使用组合法则，`N` 的任何除数的形式为:
    > `D = P1^B1 * P2^B2 * P3^B3 * ….. * PK^BK`，其中 `Bi` 为整数，`0 <= Bi <= Ai` 为 `1 <= i <= K`。

*   如果一个除数的素因子分解中不包含 2，它就是奇数。所以，如果 `P1 = 2`，那么 `B1` 一定是 **0**。只有一种方法可以做到。
*   对于偶数除数，`B1` 可以用 1(或)2(或)…)代替。`A1` 得到一个除数。可以用 `B1` 的方式来完成。
*   现在对其他人来说，每个 `Bi` 可以用 0(或)1(或)2 代替。(或)`Ai` 为 `1 <= i <= K`。可以通过 `(Ai + 1)` 种方式完成。
*   根据基本原则:
    *   **奇数除数**为: **X** = 1 * `(A2+1) * (A3+1) * ….. * (AK+1)`。
    *   同样，**偶数除数**为: **Y** = `A1 * (A2+1) * (A3+1) * …. * (AK+1)`。
*   对于偶数除数等于奇数除数的 `X`，`Y` 应该相等。这只有在 **`A1 = 1`** 时才有可能。

因此，如果一个数的素因子分解为 2 的 1(并且只有 1)次幂，那么它的偶数和奇数除数相等**。**

按照以下步骤解决问题:

1.  对于给定的数字 `N`，检查它是否能被 2 整除。
2.  如果数字能被 2 整除，那么检查它是否能被 `2^2` 整除。如果是，那么这个数就不会有相等数量的奇数和偶数因子。如果不是，那么这个数将有相等数量的奇数和偶数因子。
3.  如果这个数不能被 2 整除，那么这个数永远不会有任何偶数因子，因此它不会有相等数量的奇数和偶数因子。

下面是上述方法的实现。

## C

```c
// C code for the above approach
#include <stdio.h>
#define lli long long int

// Function to check condition
void isEqualFactors(lli N)
{
    if ((N % 2 == 0)
        && (N % 4 != 0))
        printf("YES\n");
    else
        printf("NO\n");
}

// Driver Code
int main()
{
    lli N = 10;
    isEqualFactors(N);

    N = 125;
    isEqualFactors(N);

    return 0;
}
```

## C++

```cpp
// C++ code for the above approach
#include <bits/stdc++.h>
using namespace std;
#define lli long long int

// Function to check condition
void isEqualFactors(lli N)
{
    if ((N % 2 == 0)
        and (N % 4 != 0))
        cout << "YES" << endl;
    else
        cout << "NO" << endl;
}

// Driver Code
int main()
{
    lli N = 10;
    isEqualFactors(N);

    N = 125;
    isEqualFactors(N);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// JAVA code for the above approach
public class GFG {

    // Function to check condition
    static void isEqualFactors(int N)
    {
        if ((N % 2 == 0)
            && (N % 4 != 0))
            System.out.println("YES");

        else
            System.out.println("NO");
    }

    // Driver code
    public static void main(String args[])
    {
        int N = 10;
        isEqualFactors(N);

        N = 125;
        isEqualFactors(N);
    }
}
```

## 计算机编程语言

```python
# Python code for the above approach

# Function to check condition
def isEqualFactors(N):
    if ( ( N % 2 == 0 ) and ( N % 4 != 0) ):
        print("YES")
    else:
        print("NO")

# Driver Code
N = 10
isEqualFactors(N)

N = 125;
isEqualFactors(N)
```

## C#

```csharp
// C# code for the above approach
using System;

class GFG {

    // Function to check condition
    static void isEqualFactors(int N)
    {
        if ((N % 2 == 0)
            && (N % 4 != 0))
            Console.WriteLine("YES");

        else
            Console.WriteLine("NO");
    }

    // Driver code
    public static void Main()
    {
        int N = 10;
        isEqualFactors(N);

        N = 125;
        isEqualFactors(N);
    }
}
```

## java 描述语言

```javascript
<script>

// Javascript code for the above approach

// Function to check condition
function isEqualFactors(N)
{
    if ((N % 2 == 0)
        && (N % 4 != 0))
        document.write("YES<br>");
    else
        document.write("NO<br>");
}

// Driver Code
var N = 10;
isEqualFactors(N);
N = 125;
isEqualFactors(N);

</script>
```

`Output:`

```
YES
NO
```

`时间复杂度:` O(1)
`辅助空间:` O(1)