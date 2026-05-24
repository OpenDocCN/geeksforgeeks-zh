# 求要加到 `N` 上的最小数，使之成为 `K` 的幂

> 原文：[https://www.geeksforgeeks.org/find-the-minimum-number-to-be-added-to-n-to-make-it-a-power-of-k/](https://www.geeksforgeeks.org/find-the-minimum-number-to-be-added-to-n-to-make-it-a-power-of-k/)

给定两个正整数 `N` 和 `K`，任务是找到要加到 `N` 上的最小数，使其成为 `K` 的幂。

**示例：**

> **输入：** `N = 9`，`K = 10`
> **输出：** `1`
> **解释：**
> `9 + 1 = 10 = 10^1`
>
> **输入：** `N = 20`，`K = 5`
> **输出：** `5`
> **解释：**
> `20 + 5 = 25 = 5^2`

**逼近：** 解决这个问题的思路是观察到 `N` 可以形成的 `K` 的最小幂是 `K` 的下一个更大的幂。所以，思路是找到 `K` 的下一个更大的幂，然后找到 `N` 和这个数的差。下一个更大的 `K` 的幂可以通过公式找到：

> `K^(int(log(N)/log(K)) + 1)`

因此，可以通过下式计算出要相加的最小数：

> 最小数量 = `K^(int(log(N)/log(K)) + 1) - N`

以下是上述方法的实现：

## C++

```cpp
// C++ program to find the minimum number
// to be added to N to make it a power of K

#include <bits/stdc++.h>
#define ll long long int
using namespace std;

// Function to return the minimum number
// to be added to N to make it a power of K.
int minNum(int n, int k)
{
    int x = (int)(log(n) / log(k)) + 1;

    // Computing the difference between
    // then next greater power of K
    // and N
    int mn = pow(k, x) - n;
    return mn;
}

// Driver code
int main()
{
    int n = 20, k = 5;
    cout << minNum(n, k);
    return 0;
}
```

## Java

```java
// Java program to find the minimum number
// to be added to N to make it a power of K

class GFG{

// Function to return the minimum number
// to be added to N to make it a power of K.
static int minNum(int n, int k)
{
    int x = (int)(Math.log(n) / Math.log(k)) + 1;

    // Computing the difference between
    // then next greater power of K
    // and N
    int mn = (int) (Math.pow(k, x) - n);
    return mn;
}

// Driver code
public static void main(String[] args)
{
    int n = 20, k = 5;
    System.out.print(minNum(n, k));
}
}

// This code is contributed by Amit Katiyar
```

## Python 3

```python
# Python3 program to find the minimum number
# to be added to N to make it a power of K
import math

# Function to return the minimum number
# to be added to N to make it a power of K.
def minNum(n, k):

    x = int((math.log(n) // math.log(k))) + 1

    # Computing the difference between
    # then next greater power of K
    # and N
    mn = pow(k, x) - n
    return mn

# Driver code
if __name__=='__main__':

    n = 20
    k = 5
    print(minNum(n, k))

# This code is contributed by rutvik_56
```

## C#

```csharp
// C# program to find the minimum number
// to be added to N to make it a power of K
using System;
class GFG{

// Function to return the minimum number
// to be added to N to make it a power of K.
static int minNum(int n, int k)
{
    int x = (int)(Math.Log(n) /
                  Math.Log(k)) + 1;

    // Computing the difference between
    // then next greater power of K
    // and N
    int mn = (int)(Math.Pow(k, x) - n);
    return mn;
}

// Driver code
public static void Main(string[] args)
{
    int n = 20, k = 5;
    Console.Write(minNum(n, k));
}
}

// This code is contributed by Ritik Bansal
```

## JavaScript

```javascript
<script>

// Javascript program to find the minimum number
// to be added to N to make it a power of K

// Function to return the minimum number
// to be added to N to make it a power of K.
function minNum(n, k)
{
    var x = parseInt(Math.log(n) / Math.log(k)) + 1;

    // Computing the difference between
    // then next greater power of K
    // and N
    var mn = Math.pow(k, x) - n;
    return mn;
}

// Driver code
var n = 20, k = 5;
document.write( minNum(n, k));

</script>
```

**Output:**

```
5
```

时间复杂度：`O(log n)`

辅助空间：`O(1)`