# 圣埃克苏佩里数

> 原文: [https://www.geeksforgeeks.org/saint-exupery-numbers/](https://www.geeksforgeeks.org/saint-exupery-numbers/)

`圣埃克苏佩里数`是一个数 `N`，满足 `N` 是毕达哥拉斯三角形三边的乘积。
圣埃克苏佩里数的一些例子是：
> 60, 480, 780, 1620, 2040, 3840, 4200, 6240, 7500, 12180….

### 检查 N 是否是圣埃克苏佩里数

给定一个数字 `N`，任务是检查 `N` 是否为`圣埃克苏佩里数`。如果 `N` 是圣埃克苏佩里数，则打印`"Yes"`，否则打印`"No"`。

**示例:**

> **输入:** `N = 60`
> **输出:** `Yes`
> **解释:**
> `60 = 3 * 4 * 5` 且 `3^2 + 4^2 = 5^2`。
> **输入:** `N = 120`
> **输出:** `No`

**朴素方法:** 一个简单的解决方案是运行三个嵌套循环来生成所有可能的三元组，对于每个三元组，检查它是否是毕达哥拉斯三元组并且其乘积是否等于 `N`。这个解的时间复杂度为 `O(n^3)`。

**高效方法:** 思路是运行两个循环，其中第一个循环从 `i = 1` 运行到 `n/3`，第二个循环从 `j = i+1` 运行到 `n/2`。在第二个循环中，我们检查 `(n / i / j)` 是否等于 `k`，并且 `i * i + j * j == k * k`。

下面是上述方法的实现：

## C++

```cpp
// C++ implementation to check if N
// is a Saint-Exupery number

#include <bits/stdc++.h>
using namespace std;

// Function to check if a number is
//  a Saint-Exupery number
bool isSaintExuperyNum(int n)
{
    // Considering triplets in
    // sorted order. The value
    // of first element in sorted
    // triplet can be at-most n/3.
    for (int i = 1; i <= n / 3; i++) {

        // The value of second
        // element must be less
        // than equal to n/2
        for (int j = i + 1; j <= n / 2; j++) {
            int k = n / i / j;
            if (i * i + j * j == k * k) {
                if (i * j * k == n)
                    return true;
                ;
            }
        }
    }

    return false;
}

// Driver Code
int main()
{
    // Given Number N
    int N = 60;

    // Function Call
    if (isSaintExuperyNum(N))
        cout << "Yes";
    else
        cout << "No";
    return 0;
}
```

## Java

```java
// Java program for above approach
class GFG{

// Function to check if a number is
// a Saint-Exupery number
static boolean isSaintExuperyNum(int n)
{
    // Considering triplets in
    // sorted order. The value
    // of first element in sorted
    // triplet can be at-most n/3.
    for (int i = 1; i <= n / 3; i++)
    {

        // The value of second
        // element must be less
        // than equal to n/2
        for (int j = i + 1; j <= n / 2; j++)
        {
            int k = n / i / j;
            if (i * i + j * j == k * k)
            {
                if (i * j * k == n)
                    return true;
            }
        }
    }

    return false;
}

// Driver Code
public static void main(String[] args)
{
    // Given Number N
    int N = 60;

    // Function Call
    if (isSaintExuperyNum(N))
        System.out.print("Yes");
    else
        System.out.print("No");
}
}

// This code is contributed by Shubham Prakash
```

## Python 3

```python
# Python3 implementation to check if N
# is a Saint-Exupery number

# Function to check if a number is
# a Saint-Exupery number
def isSaintExuperyNum(n):

    # Considering triplets in
    # sorted order. The value
    # of first element in sorted
    # triplet can be at-most n/3.
    for i in range(1, (n // 3) + 1):

        # The value of second
        # element must be less
        # than equal to n/2
        for j in range(i + 1, (n // 2) + 1):
            k = n / i / j
            if i * i + j * j == k * k:
                if i * j * k == n:
                    return True

    return False

# Driver Code

# Given Number N
N = 60

# Function Call
if isSaintExuperyNum(N):
    print("Yes")
else:
    print("No")

# This code is contributed by
# divyamohan123
```

## C#

```csharp
// C# program for above approach
using System;
class GFG{

// Function to check if a number is
// a Saint-Exupery number
static bool isSaintExuperyNum(int n)
{
    // Considering triplets in
    // sorted order. The value
    // of first element in sorted
    // triplet can be at-most n/3.
    for (int i = 1; i <= n / 3; i++)
    {

        // The value of second
        // element must be less
        // than equal to n/2
        for (int j = i + 1; j <= n / 2; j++)
        {
            int k = n / i / j;
            if (i * i + j * j == k * k)
            {
                if (i * j * k == n)
                    return true;
            }
        }
    }

    return false;
}

// Driver Code
public static void Main()
{
    // Given Number N
    int N = 60;

    // Function Call
    if (isSaintExuperyNum(N))
        Console.Write("Yes");
    else
        Console.Write("No");
}
}

// This code is contributed by Code_Mech
```

## JavaScript

```javascript
<script>

// Javascript program for above approach

    // Function to check if a number is
    // a Saint-Exupery number
    function isSaintExuperyNum( n) {
        // Considering triplets in
        // sorted order. The value
        // of first element in sorted
        // triplet can be at-most n/3.
        for ( i = 1; i <= n / 3; i++) {

            // The value of second
            // element must be less
            // than equal to n/2
            for ( j = i + 1; j <= n / 2; j++) {
                let k = n / i / j;
                if (i * i + j * j == k * k) {
                    if (i * j * k == n)
                        return true;
                }
            }
        }

        return false;
    }

    // Driver Code

        // Given Number N
        let N = 60;

        // Function Call
        if (isSaintExuperyNum(N))
            document.write("Yes");
        else
            document.write("No");

// This code contributed by gauravrajput1

</script>
```

**输出:**

```
Yes
```

**时间复杂度:** `O(n^2)`

**参考:** [http://www.numbersaplenty.com/set/Saint-Exupery_number/](http://www.numbersaplenty.com/set/Saint-Exupery_number/)