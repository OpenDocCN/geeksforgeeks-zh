# 尺函数系列第 n 项

> 原文: [https://www.geeksforgeeks.org/nth-term-of-ruler-function-series/](https://www.geeksforgeeks.org/nth-term-of-ruler-function-series/)

给定一个正整数 `N`，任务是找到**尺函数系列**的第 `N` 项。

> **尺函数系列**是一个系列，以 1 为第一项，通过执行以下两个操作形成:
> *   追加序列中不存在的最小正整数。
> *   然后，将所有数字追加到最后一个数字之前。

## 示例

> **输入:** `N = 5`
> **输出:** 1
> **说明:** 尺函数序列由 `{1, 2, 1, 3, 1, 2, 1, 4, …..}` 组成。因此，该系列的第 5 项为 1。
>
> **输入:** `N = 8`
> **输出:** 4

## 朴素方法

解决给定问题的最简单方法是生成系列直到第 `N` 项，然后打印第 `N` 项。

*   **时间复杂度:** `O(N)`
*   **辅助空间:** `O(N)`

## 有效方法

上述方法也可以基于以下观察进行优化，即**尺函数系列**中的第 `N` 项等于 `(N ^ (N–1))` 中的[设置位数](https://www.geeksforgeeks.org/count-set-bits-in-an-integer/)，如下图所示:

*   0 和 1 的按位异或中的设置位数 = 1
*   1 和 2 的按位异或中的设置位数 = 2
*   2 和 3 的按位异或中的设置位数 = 1
*   3 和 4 的按位异或中的设置位数 = 3
*   4 和 5 的按位异或中的设置位数 = 1
*   5 和 6 的按位异或中的设置位数 = 2
*   6 和 7 的按位异或中的设置位数 = 1
*   7 和 8 的按位异或中的设置位数 = 4
*   等等…

因此，从上面的观察来看，**尺函数系列**的第 `N` 项是由 `N` 和 `(N–1)` 的[按位异或](https://www.geeksforgeeks.org/bitwise-operators-in-c-cpp/)给出的。

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to count the number
// of set bits in the number N
int setBits(long n)
{
    // Store the number of setbits
    int count = 0;

    while (n > 0) {

        // Update the value of n
        n = n & (n - 1);

        // Update the count
        count++;
    }

    // Return the total count
    return count;
}

// Function to find the Nth term of
// the Ruler Function Series
void findNthTerm(int N)
{
    // Store the result
    int x = setBits(N ^ (N - 1));

    // Print the result
    cout << x;
}

// Driver Code
int main()
{
    int N = 8;
    findNthTerm(N);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;
import java.lang.*;
import java.util.*;

class GFG{

// Function to count the number
// of set bits in the number N
static int setBits(long n)
{

    // Store the number of setbits
    int count = 0;

    while (n > 0)
    {

        // Update the value of n
        n = n & (n - 1);

        // Update the count
        count++;
    }

    // Return the total count
    return count;
}

// Function to find the Nth term of
// the Ruler Function Series
static void findNthTerm(int N)
{

    // Store the result
    int x = setBits(N ^ (N - 1));

    // Print the result
    System.out.println(x);
}

// Driver Code
public static void main(String[] args)
{
    int N = 8;

    findNthTerm(N);
}
}

// This code is contributed by Kingash
```

### Python 3

```python
# Python3 program for the above approach

# Function to count the number
# of set bits in the number N
def setBits(n):

    # Store the number of setbits
    count = 0

    while (n > 0):

        # Update the value of n
        n = n & (n - 1)

        # Update the count
        count += 1

    # Return the total count
    return count

# Function to find the Nth term of
# the Ruler Function Series
def findNthTerm(N):

    # Store the result
    x = setBits(N ^ (N - 1))

    # Print the result
    print(x)

# Driver Code
N = 8

findNthTerm(N)

# This code is contributed by Ankita saini
```

### C#

```csharp
// C# program for the above approach
using System;
class GFG {

    // Function to count the number
    // of set bits in the number N
    static int setBits(long n)
    {

        // Store the number of setbits
        int count = 0;

        while (n > 0) {

            // Update the value of n
            n = n & (n - 1);

            // Update the count
            count++;
        }

        // Return the total count
        return count;
    }

    // Function to find the Nth term of
    // the Ruler Function Series
    static void findNthTerm(int N)
    {

        // Store the result
        int x = setBits(N ^ (N - 1));

        // Print the result
        Console.WriteLine(x);
    }

    // Driver Code
    public static void Main(string[] args)
    {
        int N = 8;

        findNthTerm(N);
    }
}

// This code is contributed by ukasp.
```

### JavaScript

```javascript
<script>

// Javascript program for the above approach

// Function to count the number
// of set bits in the number N
function setBits(n)
{

    // Store the number of setbits
    var count = 0;

    while (n > 0)
    {

        // Update the value of n
        n = n & (n - 1);

        // Update the count
        count++;
    }

    // Return the total count
    return count;
}

// Function to find the Nth term of
// the Ruler Function Series
function findNthTerm(N)
{

    // Store the result
    var x = setBits(N ^ (N - 1));

    // Print the result
    document.write(x);
}

// Driver code
var N = 8;

findNthTerm(N);

// This code is contributed by Khushboogoyal499

</script>
```

**输出:**

```
4
```

*   **时间复杂度:** `O(log N)`
*   **辅助空间:** `O(1)`