# 高效寻找一个数的奇偶性

> 原文:[https://www . geesforgeks . org/find-the-parity-of-number-effective/](https://www.geeksforgeeks.org/finding-the-parity-of-a-number-efficiently/)

给定一个整数 n，任务是编写一个程序来寻找给定数的奇偶性。
**注**:一个数的奇偶性是用来定义一个数的集合位数(二进制表示的 1 位)的总数是偶数还是奇数。如果一个数的二进制表示中的集合比特的总数是偶数，那么这个数被称为具有偶数奇偶校验，否则，它将具有奇数奇偶校验。

**示例**:

> **输入** : N = 13
> **输出**:奇偶性
> **解释:**
> 13 的二进制表示为(1101)
> 
> **输入** : N = 9 (1001)
> 输出:偶宇称

通过执行以下操作，可以有效地计算由 32 位表示的数字的奇偶性。
让给定的数字为 x，然后执行以下操作:

*   y = x^(x>>1)
*   y = y^(y>>2)
*   y = y^(y>>4)
*   y = y^(y>>8)
*   y = y^(y>>16)

现在，y 中最右边的位将代表 x 的奇偶性。如果最右边的位是 1，那么 x 将具有奇数奇偶性，如果是 0，那么 x 将具有偶数奇偶性。
因此，为了提取 y 的最后一位，用 1 执行 y 的逐位“与”运算。

**这为什么管用？**

> 考虑我们想要找到 n = 150 = 1001 0110(二进制)的奇偶性。
> 
> 1.让我们把这个数分成两部分，进行异或运算，赋给 n: n = n ^ (n >> 4) = 1001 ^ 0110 = 1111。
> 
> 不同的位导致结果中的 1 位，而相似的位导致 0。我们基本上已经考虑了所有 8 位，以达到这个中间结果。因此，实际上，我们甚至取消了数字中的平价。
> 
> 现在再次重复第 1 步，直到只剩下一点。
> n = n ^(n>>2)= 11 ^ 11 = 00
> n = n ^(n>>1)= 0 ^ 0 = 0
> 最终结果= n & 1 = 0
> 
> **另一个例子:**
> 
> n = 1000 0101
> n = n ^(n>>4)= 1000 ^ 0101 = 1101
> n = n ^(n>>2)= 11 ^ 01 = 10
> n = n ^(n>>1)= 1 ^ 0 = 1
> 最终结果= n & 1 = 1

```cpp
if(y&1==1)
    odd Parity
else
    even Parity
```

下面是上述方法的实现:

## C++

```cpp
// Program to find the parity of a given number
#include <bits/stdc++.h>

using namespace std;

// Function to find the parity
bool findParity(int x)
{
    int y = x ^ (x >> 1);
    y = y ^ (y >> 2);
    y = y ^ (y >> 4);
    y = y ^ (y >> 8);
    y = y ^ (y >> 16);

    // Rightmost bit of y holds the parity value
    // if (y&1) is 1 then parity is odd else even
    if (y & 1)
        return 1;
    return 0;
}

// Driver code
int main()
{
    (findParity(9)==0)?cout<<"Even Parity\n":
                            cout<<"Odd Parity\n";

    (findParity(13)==0)?cout<<"Even Parity\n":
                            cout<<"Odd Parity\n";

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Program to find the
// parity of a given number
import java.io.*;

class GFG
{

// Function to find the parity
static boolean findParity(int x)
{
    int y = x ^ (x >> 1);
        y = y ^ (y >> 2);
        y = y ^ (y >> 4);
        y = y ^ (y >> 8);
        y = y ^ (y >> 16);

    // Rightmost bit of y holds
    // the parity value
    // if (y&1) is 1 then parity
    // is odd else even
    if ((y & 1) > 0)
        return true;
    return false;
}

// Driver code
public static void main (String[] args)
{
    if((findParity(9) == false))
        System.out.println("Even Parity");
    else
        System.out.println("Odd Parity");

    if(findParity(13) == false)
        System.out.println("Even Parity");
    else
        System.out.println("Odd Parity");
}
}

// This Code is Contributed by chandan_jnu.
```

## 蟒蛇 3

```cpp
# Program to find the
# parity of a given number

# Function to find the parity
def findParity(x):
    y = x ^ (x >> 1);
    y = y ^ (y >> 2);
    y = y ^ (y >> 4);
    y = y ^ (y >> 8);
    y = y ^ (y >> 16);

    # Rightmost bit of y holds
    # the parity value if (y&1)
    # is 1 then parity is odd
    # else even
    if (y & 1):
        return 1;
    return 0;

# Driver code
if(findParity(9) == 0):
    print("Even Parity");
else:
    print("Odd Parity\n");

if(findParity(13) == 0):
    print("Even Parity");
else:
    print("Odd Parity");

# This code is contributed by mits
```

## C#

```cpp
// Program to find the
// parity of a given number
using System;

class GFG
{

// Function to find the parity
static bool findParity(int x)
{
    int y = x ^ (x >> 1);
        y = y ^ (y >> 2);
        y = y ^ (y >> 4);
        y = y ^ (y >> 8);
        y = y ^ (y >> 16);

    // Rightmost bit of y holds
    // the parity value
    // if (y&1) is 1 then parity
    // is odd else even
    if ((y & 1) > 0)
        return true;
    return false;
}

// Driver code
public static void Main ()
{
    if((findParity(9) == false))
        Console.WriteLine("Even Parity");
    else
        Console.WriteLine("Odd Parity");

    if(findParity(13) == false)
        Console.WriteLine("Even Parity");
    else
        Console.WriteLine("Odd Parity");
}
}

// This Code is Contributed
// by chandan_jnu
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// Program to find the
// parity of a given number

// Function to find the parity
function findParity($x)
{
    $y = $x ^ ($x >> 1);
    $y = $y ^ ($y >> 2);
    $y = $y ^ ($y >> 4);
    $y = $y ^ ($y >> 8);
    $y = $y ^ ($y >> 16);

    // Rightmost bit of y holds
    // the parity value if (y&1)
    // is 1 then parity is odd
    // else even
    if ($y & 1)
        return 1;
    return 0;
}

// Driver code
(findParity(9) == 0) ?
 print("Even Parity\n"):
 print("Odd Parity\n");

(findParity(13) == 0) ?
print("Even Parity\n"):
print("Odd Parity\n");

// This Code is Contributed by mits
?>
```

## java 描述语言

```cpp
<script>
// Javascript Program to find the parity of a given number

// Function to find the parity
function findParity(x) {
    let y = x ^ (x >> 1);
    y = y ^ (y >> 2);
    y = y ^ (y >> 4);
    y = y ^ (y >> 8);
    y = y ^ (y >> 16);

    // Rightmost bit of y holds the parity value
    // if (y&1) is 1 then parity is odd else even
    if (y & 1)
        return 1;
    return 0;
}

// Driver code

(findParity(9) == 0) ? document.write("Even Parity<br>") :
    document.write("Odd Parity<br>");

(findParity(13) == 0) ? document.write("Even Parity<br>") :
    document.write("Odd Parity<br>");

// This code is contributed by _saurabh_jaiswal
</script>
```

**Output:** 

```cpp
Even Parity
Odd Parity
```

**时间复杂度:**O(1)
T3】辅助空间: O(1)