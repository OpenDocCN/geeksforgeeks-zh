# 找出给定范围内最大的双胞胎

> 原文：[https://www.geeksforgeeks.org/find-the-largest-twins-in-given-range/](https://www.geeksforgeeks.org/find-the-largest-twins-in-given-range/)

给定范围 [`low`..`high`]，打印给定范围内最大的孪生数（包括 `low` 和 `high`）。如果两个数是素数，相差 2，那么这两个数就是[双胞胎](https://www.geeksforgeeks.org/twin-prime-numbers/)。

**例：**

```
Input: low = 10, high = 100
Output: Largest twins in given range: (71, 73)

Input: low = 1, high = 20
Output: Largest twins in given range: (17, 19)
```

一个**简单的解决方案**是从 `high` 开始，对于每个数字 `x`，检查 `x` 和 `x–2` 是否是素数。这里 `x` 从 `high` 到 `low` 变化，步长为 2。

一种**高效解决方案**是使用[厄拉多塞筛](https://www.geeksforgeeks.org/sieve-of-eratosthenes/)：

1.  创建布尔数组 `prime[0 ... high]` 并将所有条目初始化为 `true`。如果 `i` 不是素数，`prime[i]` 的值最终将为 `false`，否则为 `true`。
2.  从 `p = 2` 循环到 `high`。
    *   如果 `prime[p]` 为 `true`，则 `p` 是素数。
    *   将 `p` 的所有倍数标记为非素数（`prime[i] = false`）。
3.  从 `high` 循环到 `low`，并使用步骤 2 中构建的 `prime[]` 数组打印第一对孪生素数。

## C++

```cpp
// C++ program to find the largest twin in given range
#include <bits/stdc++.h>
using namespace std;

// Function to find twins
void printTwins(int low, int high)
{
    // Create a boolean array "prime[0..high]" and initialize
    // all entries it as true. A value in prime[i] will finally
    // be false if i is Not a prime, else true.
    bool prime[high + 1], twin = false;
    memset(prime, true, sizeof(prime));

    prime[0] = prime[1] = false;

    // Look for the smallest twin
    for (int p = 2; p <= floor(sqrt(high)) + 1; p++) {

        // If p is not marked, then it is a prime
        if (prime[p]) {

            // Update all multiples of p
            for (int i = p * 2; i <= high; i += p)
                prime[i] = false;
        }
    }

    // Now print the largest twin in range
    for (int i = high; i >= low; i--) {
        if (prime[i] && (i - 2 >= low && prime[i - 2] == true)) {
            cout << "Largest twins in given range: ("
                 << i - 2 << ", " << i << ")";
            twin = true;
            break;
        }
    }

    if (twin == false)
        cout << "No such pair exists" << endl;
}

// Driver program
int main()
{
    printTwins(10, 100);

    return 0;
}
```

## Java

```java
// Java program to find the
// largest twin in given range
import java.io.*;

class GFG
{

// Function to find twins
static void printTwins(int low, int high)
{
    // Create a boolean array
    // "prime[0..high]" and initialize
    // all entries it as true. A value
    // in prime[i] will finally be false
    // if i is Not a prime, else true.
    boolean prime[] = new boolean[high + 1];
    boolean twin = false;
    for(int i = 0; i < high + 1; i++)
    prime[i] = true;

    prime[0] = prime[1] = false;

    // Look for the smallest twin
    for (int p = 2;
             p <= Math.floor(Math.sqrt(high)) + 1; p++)
    {

        // If p is not marked,
        // then it is a prime
        if (prime[p])
        {

            // Update all multiples of p
            for (int i = p * 2; i <= high; i += p)
                prime[i] = false;
        }
    }

    // Now print the largest twin in range
    for (int i = high; i >= low; i--)
    {
        if (prime[i] && (i - 2 >= low &&
            prime[i - 2] == true))
        {
            System.out.println("Largest twins in given range: (" +
                                      (i - 2) + ", " + (i) + ")");
            twin = true;
            break;
        }
    }

    if (twin == false)
        System.out.println("No such pair exists");
}

// Driver Code
public static void main (String[] args)
{
    printTwins(10, 100);
}
}

// This code is contributed
// by inder_verma.
```

## Python 3

```python
# Python 3 program to find the largest twin
# in given range

# Function to find twins
from math import sqrt,floor
def printTwins(low, high):

    # Create a boolean array "prime[0..high]"
    # and initialize all entries it as true.
    # A value in prime[i] will finally
    # be false if i is Not a prime, else true.
    prime = [True for i in range(high + 1)]
    twin = False

    prime[0] = False
    prime[1] = False

    # Look for the smallest twin
    k = floor(sqrt(high)) + 2
    for p in range(2, k, 1):

        # If p is not marked, then it
        # is a prime
        if (prime[p]):

            # Update all multiples of p
            for i in range(p * 2, high + 1, p):
                prime[i] = False

    # Now print the largest twin in range
    i = high
    while(i >= low):
        if (prime[i] and (i - 2 >= low and
                          prime[i - 2] == True)):
            print("Largest twins in given range:(", (i - 2),   
                                         ",", (i), ")")
            twin = True
            break

        i -= 1

    if (twin == False):
        print("No such pair exists")

# Driver Code
if __name__ == '__main__':
    printTwins(10, 100)

# This code is contributed by
# Sanjit_Prasad
```

## C#

```csharp
// C# program to find the
// largest twin in given range
class GFG
{

// Function to find twins
static void printTwins(int low, int high)
{
    // Create a boolean array
    // "prime[0..high]" and initialize
    // all entries it as true. A value
    // in prime[i] will finally be false
    // if i is Not a prime, else true.
    bool[] prime = new bool[high + 1];
    bool twin = false;
    for(int i = 0; i < high + 1; i++)
    prime[i] = true;

    prime[0] = prime[1] = false;

    // Look for the smallest twin
    for (int p = 2;
             p <= System.Math.Floor(
                         System.Math.Sqrt(high)) + 1; p++)
    {

        // If p is not marked,
        // then it is a prime
        if (prime[p])
        {

            // Update all multiples of p
            for (int i = p * 2; i <= high; i += p)
                prime[i] = false;
        }
    }

    // Now print the largest twin in range
    for (int i = high; i >= low; i--)
    {
        if (prime[i] && (i - 2 >= low &&
            prime[i - 2] == true))
        {
            System.Console.WriteLine("Largest twins in given range: (" +
                                (i - 2) + ", " + (i) + ")");
            twin = true;
            break;
        }
    }

    if (twin == false)
        System.Console.WriteLine("No such pair exists");
}

// Driver Code
public static void Main()
{
    printTwins(10, 100);
}
}

// This code is contributed
// by mits
```

## PHP

```php
<?php
//PHP program to find the largest twin in given range
// Function to find twins
function printTwins($low, $high)
{
    // Create a boolean array "prime[0..high]" and initialize
    // all entries it as true. A value in prime[i] will finally
    // be false if i is Not a prime, else true.
    $prime[$high + 1]=array();
    $twin = false;
    $prime = array_fill(0, ($high + 1), true);

    $prime[0] = $prime[1] = false;

    // Look for the smallest twin
    for ($p = 2; $p <= floor(sqrt($high)) + 1; $p++) {

        // If p is not marked, then it is a prime
        if ($prime[$p]) {

            // Update all multiples of p
            for ($i = $p * 2; $i <= $high; $i += $p)
                $prime[$i] = false;
        }
    }

    // Now print the largest twin in range
    for ($i = $high; $i >= $low; $i--) {
        if ($prime[$i] && ($i - 2 >= $low && $prime[$i - 2] == true)) {
            echo "Largest twins in given range: (",
                $i - 2 , ", " , $i , ")";
            $twin = true;
            break;
        }
    }

    if ($twin == false)
         echo "No such pair exists" ;
}

// Driver program
    printTwins(10, 100);

#This code is contributed by ajit.
?>
```

## java 描述语言

```javascript
<script>

    // Javascript program to find the
    // largest twin in given range

    // Function to find twins
    function printTwins(low, high)
    {
        // Create a boolean array
        // "prime[0..high]" and initialize
        // all entries it as true. A value
        // in prime[i] will finally be false
        // if i is Not a prime, else true.
        let prime = new Array(high + 1);
        let twin = false;
        for(let i = 0; i < high + 1; i++)
            prime[i] = true;

        prime[0] = prime[1] = false;

        // Look for the smallest twin
        for (let p = 2; p <=
        Math.floor(Math.sqrt(high)) + 1; p++)
        {

            // If p is not marked,
            // then it is a prime
            if (prime[p])
            {

                // Update all multiples of p
                for (let i = p * 2; i <= high; i += p)
                    prime[i] = false;
            }
        }

        // Now print the largest twin in range
        for (let i = high; i >= low; i--)
        {
            if (prime[i] && (i - 2 >= low &&
            prime[i - 2] == true))
            {
                document.write(
                "Largest twins in given range: (" +
                (i - 2) + ", " + (i) + ")" + "</br>"
                );
                twin = true;
                break;
            }
        }

        if (twin == false)
            document.write("No such pair exists");
    }

    printTwins(10, 100);

</script>
```

**Output:**

```
Largest twins in given range: (71, 73)
```