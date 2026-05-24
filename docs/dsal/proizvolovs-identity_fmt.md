# 普罗兹沃洛夫的身份

> 原文: [https://www.geeksforgeeks.org/proizvolovs-identity/](https://www.geeksforgeeks.org/proizvolovs-identity/)

给定两个大小为 `N` 的数组 `A` 和 `B`。数组 `A` 为递增顺序，`B` 为递减顺序。两个数组都是从 `1` 到 `2N` 的数字的子序列。任务是求两个数组的绝对差之和。

> `sum = | A1–B1|+| A2–B2|+| A3–B3|+…+| AN–BN|`

**例:**

> **输入:** `A[] = {1，2，3，4，5}`，`B[] = {10，9，8，7，6}`
> **输出:** `25`
> **输入:** `A[] = {1，5，6，8，10，12}`，`B[] = {11，9，7，4，3，2}`
> **输出:** `36`

**天真法:** 天真法是运行一个循环，求绝对差的和。

**有效方法:** [Proizvolov 的恒等式](https://en.wikipedia.org/wiki/Proizvolov%27s_identity)是关于正整数的差的和的恒等式。它指出，如果我们首先取 `2N` 个整数，并将它们分成两个子集 `N` 个数字。
按递增顺序排列一个子集: `A1 < A2 < A3 < … < AN`
按降序排列另一个子集: `B1 > B2 > B3 > … > BN`
那么总和 `| A1–B1|+| A2–B2|+| A3–B3|+…+| AN–BN|` 始终等于 `N^2`。

以下是上述方法的实现:

## C++

```cpp
// CPP program to implement proizvolov's identity
#include<bits/stdc++.h>
using namespace std;

// Function to implement proizvolov's identity
int proizvolov(int a[], int b[], int n)
{
    // According to proizvolov's identity
    return n*n;
}

// Driver code
int main()
{
    int a[] = {1, 5, 6, 8, 10}, b[] = {9, 7, 4, 3, 2};

    int n = sizeof(a) / sizeof(a[0]);

    // Function call
    cout << proizvolov(a, b, n);

    return 0;
}
```

## Java

```java
// Java program to implement proizvolov's identity
class GFG
{
    // Function to implement proizvolov's identity
    static int proizvolov(int a [], int b [], int n)
    {
        // According to proizvolov's identity
        return n * n;
    }

    // Driver code
    public static void main (String[] args)
    {
        int a [] = {1, 5, 6, 8, 10};
        int b [] = {9, 7, 4, 3, 2};

        int n = a.length;

        // Function call
        System.out.println(proizvolov(a, b, n));
    }
}

// This code is contributed by ihritik
```

## Python 3

```python
# Python3 program to implement
# proizvolov's identity

# Function to implement
# proizvolov's identity
def proizvolov(a, b, n):
    return n * n

# Driver code
a = [ 1, 5, 6, 8, 10 ]
b = [ 9, 7, 4, 3, 2 ]
n = len(a)

# Function call
print(proizvolov(a, b, n, ))

# This code is contributed by nidhiva
```

## C#

```csharp
// C# program to implement proizvolov's identity
using System;

class GFG
{
    // Function to implement proizvolov's identity
    static int proizvolov(int [] a,
                          int [] b, int n)
    {
        // According to proizvolov's identity
        return n * n;
    }

    // Driver code
    public static void Main ()
    {
        int [] a = {1, 5, 6, 8, 10};
        int [] b = {9, 7, 4, 3, 2};

        int n = a.Length;

        // Function call
        Console.WriteLine(proizvolov(a, b, n));
    }
}

// This code is contributed by ihritik
```

## JavaScript

```javascript
<script>

// Javascript program to implement
// proizvolov's identity

// Function to implement proizvolov's identity
function proizvolov(a, b, n)
{
    // According to proizvolov's identity
    return n*n;
}

// Driver code
    let a = [1, 5, 6, 8, 10], b = [9, 7, 4, 3, 2];

    let n = a.length;

    // Function call
    document.write(proizvolov(a, b, n));

</script>
```

**Output:**

```