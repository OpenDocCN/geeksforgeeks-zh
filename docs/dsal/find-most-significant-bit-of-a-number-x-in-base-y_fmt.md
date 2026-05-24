# 在基数 Y 中找出数字 X 的最高有效位

> 原文：[https://www.geeksforgeeks.org/find-most-significant-bit-of-a-number-x-in-base-y/](https://www.geeksforgeeks.org/find-most-significant-bit-of-a-number-x-in-base-y/)

给定两个正整数 `X` 和 `Y`，任务是在给定的基数 `Y` 中找到 `X` 的[MSB](https://www.geeksforgeeks.org/find-significant-set-bit-number/)。

**示例：**

> **输入：** `X = 55`，`Y = 3`
> **输出：** `2`
> **说明：**
> `55` 为 `2001`（3 进制），第一位数字为 `2`。
> **输入：** `X = 123`，`Y = 10`
> **输出：** `1`
> **说明：**
> `123` 是以 `10` 为基数的 `123`，第一位数字为 `1`。

**方法：**
让任务在基数 `Y = 10` 中找到 `X = 1234` 的第一位数字，这样得到第一位数字 = `1`：

> 将 `1234` 除以 `1000`
> = `X/10^3`
> = `X/10^(X–1 中的位数)`
> = `X/10^(log(X)/log(10))` (表示基数 `10`)

对于任何其他基数，我们可以用 `Y` 代替 `10`，因此，我们可以用公式计算基数 `Y` 中一个数字 `X` 的第一位数字：

> `X/Y^(log(X)/log(Y))`

下面是上述方法的实现：

## C++

```cpp
// C++ Program to find the
// first digit of X in base Y

#include <bits/stdc++.h>
using namespace std;

// Function to find the first
// digit of X in base Y
void first_digit(int x, int y)
{
    // calculating number of digits of
    // x in base y
    int length = log(x) / log(y) + 1;

    // finding first digit of x in base y
    int first_digit = x / pow(y, length - 1);

    cout << first_digit;
}

// Driver code
int main()
{
    int X = 55, Y = 3;

    first_digit(X, Y);

    return 0;
}
```

## Java

```java
// Java Program to find the
// first digit of X in base Y
import java.util.*;
class GFG{

// Function to find the first
// digit of X in base Y
static void first_digit(int x, int y)
{
    // calculating number of digits of
    // x in base y
    int length = (int)(Math.log(x) /
                       Math.log(y) + 1);

    // finding first digit of x in base y
    int first_digit = (int)(x / Math.pow(y,
                                length - 1));

    System.out.println(first_digit);
}

// Driver code
public static void main(String args[])
{
    int X = 55, Y = 3;

    first_digit(X, Y);
}
}

// This code is contributed by AbhiThakur
```

## Python 3

```python
# Python3 program to find the
# first digit of X in base Y
import math

# Function to find the first
# digit of X in base Y
def first_digit(x, y):

    # Calculating number of digits of
    # x in base y
    length = int (math.log(x) /
                  math.log(y) + 1)

    # Finding first digit of x in base y
    first_digit = x / math.pow(y, length - 1)

    print(int(first_digit))

# Driver code
X = 55
Y = 3

first_digit(X, Y)

# This code is contributed by ishayadav181
```

## C#

```csharp
// C# Program to find the
// first digit of X in base Y
using System;
class GFG{

// Function to find the first
// digit of X in base Y
static void first_digit(int x, int y)
{
    // calculating number of digits of
    // x in base y
    int length = (int)(Math.Log(x) /
                       Math.Log(y) + 1);

    // finding first digit of x in base y
    int first_digit = (int)(x / Math.Pow(y,
                                length - 1));

    Console.Write(first_digit);
}

// Driver code
public static void Main()
{
    int X = 55, Y = 3;

    first_digit(X, Y);
}
}

// This code is contributed by Akanksha_Rai
```

## JavaScript

```javascript
<script>

// Javascript Program to find the
// first digit of X in base Y

// Function to find the first
// digit of X in base Y
function first_digit(x, y)
{
    // calculating number of digits of
    // x in base y
    var length = parseInt(Math.log(x) / Math.log(y)) + 1;

    // finding first digit of x in base y
    var first_digit = parseInt(x / Math.pow(y, length - 1));

    document.write( first_digit);
}

// Driver code
var X = 55, Y = 3;
first_digit(X, Y);

</script>
```

**输出：**

```
2
```

**时间复杂度：** `O(1)`

**辅助空间：** `O(1)`