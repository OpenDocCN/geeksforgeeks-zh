# 基数 B 中最大的 N 位数

> 原文：[https://www.geeksforgeeks.org/largest-n-digit-number-in-base-b/](https://www.geeksforgeeks.org/largest-n-digit-number-in-base-b/)

给定一个正整数 `N` 和基数 `B`，任务是找到十进制形式的基数 `B` 的最大 `N` 位数。

**示例：**

> **输入：** `N = 2`，`B = 10`
> **输出：** 99
>
> **输入：** `N = 2`，`B = 5`
> **输出：** 24

**方法：**
由于 `B` 基数中有 `B` 位数，所以用这些位数我们可以创建长度为 `N` 的 `B^N` 字符串，它们代表的整数范围为 `0` 到 `B^N–1`。
因此，十进制形式的最大 `N` 位数基数 `B` 由 `B^N–1` 给出。

下面是上述方法的实现：

## C++

```cpp
// C++ program for the approach
#include <bits/stdc++.h>
using namespace std;

// Function to print the largest
// N-digit numbers of base b
void findNumbers(int n, int b)
{

    // Find the largest N digit
    // number in base b using the
    // formula B^N - 1
    int largest = pow(b, n) - 1;

    // Print the largest number
    cout << largest << endl;
}

// Driver Code
int main()
{
    // Given Number and Base
    int N = 2, B = 5;

    // Function Call
    findNumbers(N, B);

    return 0;
}
```

## Java

```java
// Java program for the approach
import java.util.*;
class GFG{

// Function to print the largest
// N-digit numbers of base b
static void findNumbers(int n, int b)
{

    // Find the largest N digit
    // number in base b using the
    // formula B^N - 1
    double largest = Math.pow(b, n) - 1;

    // Print the largest number
    System.out.println(largest);
}

// Driver Code
public static void main(String []args)
{
    // Given Number and Base
    int N = 2, B = 5;

    // Function Call
    findNumbers(N, B);
}
}

// This code is contributed by Ritik Bansal
```

## Python 3

```python
# Python3 program for the above approach

# Function to print the largest
# N-digit numbers of base b
def findNumbers(n, b):

    # Find the largest N digit
    # number in base b using the
    # formula B^N - 1
    largest = pow(b, n) - 1

    # Print the largest number
    print(largest)

# Driver Code

# Given number and base
N, B = 2, 5

# Function Call
findNumbers(N, B)

# This code is contributed by jrishabh99
```

## C#

```csharp
// C# program for the approach
using System;
class GFG{

// Function to print the largest
// N-digit numbers of base b
static void findNumbers(int n, int b)
{

    // Find the largest N digit
    // number in base b using the
    // formula B^N - 1
    double largest = Math.Pow(b, n) - 1;

    // Print the largest number
    Console.Write(largest);
}

// Driver Code
public static void Main(String []args)
{
    // Given Number and Base
    int N = 2, B = 5;

    // Function Call
    findNumbers(N, B);
}
}

// This code is contributed by shivanisinghss2110
```

## JavaScript

```javascript
<script>
// javascript program for the approach

// Function to print the largest
// N-digit numbers of base b
function findNumbers( n,  b)
{

    // Find the largest N digit
    // number in base b using the
    // formula B^N - 1
    let largest = Math.pow(b, n) - 1;

    // Print the largest number
     document.write(largest);
}

// Driver Code

    // Given Number and Base
    let N = 2, B = 5;

    // Function Call
    findNumbers(N, B);

    // This code is contributed by aashish1995

</script>
```

**输出：**

```
24
```

**时间复杂度：** `O(1)`
**辅助空间：** `O(1)`