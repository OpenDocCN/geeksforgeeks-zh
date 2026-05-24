# 找到给定序列的第 k 个位置元素

> 原文: [https://www.geeksforgeeks.org/find-the-kth-position-element-of-the-given-sequence/](https://www.geeksforgeeks.org/find-the-kth-position-element-of-the-given-sequence/)

给定两个整数 `N` 和 `K`，任务是在一个特定序列的第 `K` 个位置找到元素。该序列的生成规则是：先写下从 `1` 到 `N` 的所有奇数（按递增顺序），然后写下从 `1` 到 `N` 的所有偶数（按递增顺序）。

**举例:**

> **输入:** `N = 10`，`K = 3`
> **输出:** `5`
> 所需顺序为 `1、3、5、7、9、2、4、6、8、10`。
> **输入:** `N = 7`，`K = 7`
> **输出:** `6`

**进场:** 已知第 `N` 个偶数由 `2 * K` 给出，第 `N` 个奇数由 `2 * K - 1` 给出。但是由于这里偶数写在 `(N + 1) / 2` 个奇数之后。因此，第 `K` 个偶数由 `2 * (K - (N + 1) / 2)` 给出，奇数将保持与 `2 * K - 1` 相同。以下是上述方法的实现：

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the kth number
// from the required sequence
int kthNum(int n, int k)
{

    // Count of odd integers
    // in the sequence
    int a = (n + 1) / 2;

    // kth number is even
    if (k > a)
        return (2 * (k - a));

    // It is odd
    return (2 * k - 1);
}

// Driver code
int main()
{
    int n = 7, k = 7;

    cout << kthNum(n, k);

    return 0;
}
```

## Java

```java
// Java implementation of the approach
class GFG
{

// Function to return the kth number
// from the required sequence
static int kthNum(int n, int k)
{

    // Count of odd integers
    // in the sequence
    int a = (n + 1) / 2;

    // kth number is even
    if (k > a)
        return (2 * (k - a));

    // It is odd
    return (2 * k - 1);
}

// Driver code
public static void main(String []args)
{
    int n = 7, k = 7;

    System.out.println(kthNum(n, k));
}
}

// This code is contributed by Rajput-Ji
```

## Python 3

```python
# Python3 implementation of the approach

# Function to return the kth number
# from the required sequence
def kthNum(n, k) :

    # Count of odd integers
    # in the sequence
    a = (n + 1) // 2;

    # kth number is even
    if (k > a) :
        return (2 * (k - a));

    # It is odd
    return (2 * k - 1);

# Driver code
if __name__ == "__main__" :

    n = 7; k = 7;

    print(kthNum(n, k));

# This code is contributed by AnkitRai01
```

## C#

```csharp
// C# implementation of the approach
using System;

class GFG
{

// Function to return the kth number
// from the required sequence
static int kthNum(int n, int k)
{

    // Count of odd integers
    // in the sequence
    int a = (n + 1) / 2;

    // kth number is even
    if (k > a)
        return (2 * (k - a));

    // It is odd
    return (2 * k - 1);
}

// Driver code
public static void Main(String []args)
{
    int n = 7, k = 7;

    Console.WriteLine(kthNum(n, k));
}
}

// This code is contributed by PrinciRaj1992
```

## JavaScript

```javascript
<script>

// Javascript implementation of the approach

// Function to return the kth number
// from the required sequence
function kthNum(n, k)
{
    // Count of odd integers
    // in the sequence
    var a = (n + 1) / 2;

    // kth number is even
    if (k > a)
        return (2 * (k - a));

    // It is odd
    return (2 * k - 1);
}

// Driver code
var n = 7, k = 7;
document.write(kthNum(n, k));

</script>
```

**Output:**

**时间复杂度:** `O(1)`