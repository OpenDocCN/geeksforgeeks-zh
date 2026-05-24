# 使用位屏蔽将 2 的幂与所需的和相乘

> 原文：[https://www.geeksforgeeks.org/powers-of-2-to-required-sum-using-bit-masking/](https://www.geeksforgeeks.org/powers-of-2-to-required-sum-using-bit-masking/)

给定一个整数 `N`，任务是找出将 2 的[次幂相加后得出的整数 `N`](https://www.geeksforgeeks.org/highest-power-2-less-equal-given-number/)。

**举例：**

> **输入：** `N = 12345`
> **输出：** `0、3、4、5、12、13`
> **解释：**
> `12345 = 2^0+2^3+2^4+2^5+2^12+2^13`
> **输入：** `N = 10000`
> **输出：** `4、8、9、10、13`
> **解释：**

## 进场

*   由于每个数字都可以表示为 2 的幂之和，因此任务是当在 `N` 的二进制表示中设置了第 `i` 位时，打印每个 `i`。

> **说明：**
> `(29)_10 = (11101)_2`
> 因此，在 29 中，`{0，2，3，4}` 是设置位的索引。
> `2^0+2^2+2^3+2^4 = 1+4+8+16 = 29`

*   为了检查第 `i` 位是否置位，我们只需要检查：

> `if(N & (1<< i)) == 1`
> **插图：**
> `(29)_10 = (11101)_2`
> `0` 位：`11101 & 1 = 1`
> `1` 位：`11101 & 10 = 0`
> `2` 位：`11101 & 100 = 1`

下面是上述方法的实现。

## C++

```cpp
// C++ Program to split N
// into numbers which when
// added after being raised
// to the power of 2 gives N

#include <bits/stdc++.h>
using namespace std;

// Function to print the numbers
// which raised to power of 2
// adds up to N
void PowerOfTwo(long long N)
{
    for (int i = 0; i < 64; i++) {
        long long x = 1;

        // Checking if i-th bit is
        // set in N or not by
        // shifting 1 i bits to
        // the left and performing
        // AND with N
        if (N & (x << i))
            cout << i << " ";
    }
}

// Driver Code
int main()
{

    long long N = 12345;
    PowerOfTwo(N);

    return 0;
}
```

## Java

```java
// Java Program to split N
// into numbers which when
// added after being raised
// to the power of 2 gives N
class GFG{

// Function to print the numbers
// which raised to power of 2
// adds up to N
static void PowerOfTwo(long N)
{
    for (int i = 0; i < 64; i++)
    {
        long x = 1;

        // Checking if i-th bit is
        // set in N or not by
        // shifting 1 i bits to
        // the left and performing
        // AND with N
        if ((N & (x << i)) > 0)
            System.out.print(i + " ");
    }
}

// Driver Code
public static void main(String[] args)
{
    long N = 12345;
    PowerOfTwo(N);
}
}

// This code is contributed by Amit Katiyar
```

## Python 3

```python
# Python3 program to split N
# into numbers which when
# added after being raised
# to the power of 2 gives N

# Function to print the numbers
# which raised to power of 2
# adds up to N
def PowerOfTwo(N):

    for i in range(0, 64):
        x = 1

        # Checking if i-th bit is
        # set in N or not by
        # shifting 1 i bits to
        # the left and performing
        # AND with N
        if (N & (x << i)) > 0:
            print(i, end = " ")

# Driver Code
if __name__ == "__main__":

    # Given number
    N = 12345;

    # Function call
    PowerOfTwo(N)

# This code is contributed by rock_cool
```

## C#

```csharp
// C# Program to split N
// into numbers which when
// added after being raised
// to the power of 2 gives N
using System;
class GFG{

// Function to print the numbers
// which raised to power of 2
// adds up to N
static void PowerOfTwo(long N)
{
    for (int i = 0; i < 64; i++)
    {
        long x = 1;

        // Checking if i-th bit is
        // set in N or not by
        // shifting 1 i bits to
        // the left and performing
        // AND with N
        if ((N & (x << i)) > 0)
            Console.Write(i + " ");
    }
}

// Driver Code
public static void Main()
{
    long N = 12345;
    PowerOfTwo(N);
}
}

// This code is contributed by Nidhi_biet
```

## JavaScript

```javascript
<script>

// Javascript Program to split N
// into numbers which when
// added after being raised
// to the power of 2 gives N

// Function to print the numbers
// which raised to power of 2
// adds up to N
function PowerOfTwo(N)
{
    for (var i = 0; i < 64; i++) {
        var x = 1;

        // Checking if i-th bit is
        // set in N or not by
        // shifting 1 i bits to
        // the left and performing
        // AND with N
        if ((N & (x * Math.pow(2,i))) >0)
            document.write( i + " ");
    }
}

// Driver Code
var N = 12345;
PowerOfTwo(N);

// This code is contributed by importantly.
</script>
```

**Output：**

```
0 3 4 5 12 13
```

**时间复杂度：** `O(log N)`
**空间复杂度：** `O(1)`

如需替代方法，请参考[2 的 2 次方求和](https://www.geeksforgeeks.org/powers-2-required-sum/)。