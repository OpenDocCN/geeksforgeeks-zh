# 从右边的偶数位置找到一个包含 N–1 组位的数字

> 原文:[https://www . geesforgeks . org/find-a-number-contained-n-1-set-bit-at-even-positions-from-right/](https://www.geeksforgeeks.org/find-a-number-containing-n-1-set-bits-at-even-positions-from-the-right/)

给定一个正整数 **N** ，任务是找到一个包含**(N–1)**的数字，该数字在从右边开始的每个偶数索引处(基于 1)以二进制形式设置位。
**例:**

> **输入:** N = 2
> **输出:**2
> 2 的二进制表示为 10，其中
> 1 设置位位于右侧的偶数位置。
> **输入:** N = 4
> **输出:**42
> 42 的二进制表示为 101010

**观察:**如果我们检查出二进制形式的数字，那么结果是这样的:

<figure class="table">

| n | Decimal equivalent | Binary equivalent |
| one | Zero | Zero |
| Two | Two | Ten |

</figure>

**天真方法:**正如我们在表中看到的，我们的二进制等价物总是在前一个字符串的最后添加一个“10”。因此，我们可以生成一个由子字符串“10”串联 N-1 次组成的二进制字符串，然后打印它的十进制等价物。
以下是上述办法的实施情况:

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

#define ll long long int

// Function to return the string generated
// by appending "10" n-1 times
string constructString(ll n)
{
    // Initialising string as empty
    string s = "";
    for (ll i = 0; i < n; i++) {
        s += "10";
    }
    return s;
}

// Function to return the decimal equivalent
// of the given binary string
ll binaryToDecimal(string n)
{
    string num = n;
    ll dec_value = 0;

    // Initializing base value to 1
    // i.e 2^0
    ll base = 1;

    ll len = num.length();
    for (ll i = len - 1; i >= 0; i--) {
        if (num[i] == '1')
            dec_value += base;
        base = base * 2;
    }

    return dec_value;
}

// Function that calls the constructString
// and binarytodecimal and returns the answer
ll findNumber(ll n)
{
    string s = constructString(n - 1);
    ll num = binaryToDecimal(s);
    return num;
}

// Driver code
int main()
{
    ll n = 4;

    cout << findNumber(n);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java implementation of above approach
import java.util.*;

class GFG
{

// Function to return the String generated
// by appending "10" n-1 times
static String constructString(int n)
{
    // Initialising String as empty
    String s = "";
    for (int i = 0; i < n; i++)
    {
        s += "10";
    }
    return s;
}

// Function to return the decimal equivalent
// of the given binary String
static int binaryToDecimal(String n)
{
    String num = n;
    int dec_value = 0;

    // Initializing base value to 1
    // i.e 2^0
    int base = 1;

    int len = num.length();
    for (int i = len - 1; i >= 0; i--)
    {
        if (num.charAt(i) == '1')
            dec_value += base;
        base = base * 2;
    }

    return dec_value;
}

// Function that calls the constructString
// and binarytodecimal and returns the answer
static int findNumber(int n)
{
    String s = constructString(n - 1);
    int num = binaryToDecimal(s);
    return num;
}

// Driver code
public static void main(String[] args)
{
    int n = 4;

    System.out.println(findNumber(n));
}
}

/* This code is contributed by PrinciRaj1992 */
```

## 计算机编程语言

```cpp
# Python3 implementation of the approach

# Function to return the generated
# by appending "10" n-1 times
def constructString(n):

    # Initialising as empty
    s = ""
    for i in range(n):
        s += "10"

    return s

# Function to return the decimal equivaLent
# of the given binary string
def binaryToDecimal(n):

    num = n
    dec_value = 0

    # Initializing base value to 1
    # i.e 2^0
    base = 1

    Len = len(num)
    for i in range(Len - 1,-1,-1):
        if (num[i] == '1'):
            dec_value += base
        base = base * 2

    return dec_value

# Function that calls the constructString
# and binarytodecimal and returns the answer
def findNumber(n):

    s = constructString(n - 1)
    num = binaryToDecimal(s)
    return num

# Driver code
n = 4

print(findNumber(n))

# This code is contributed by mohit kumar 29
```

## C#

```cpp
// C# implementation of above approach
using System;

class GFG
{

// Function to return the String generated
// by appending "10" n-1 times
static String constructString(int n)
{

    // Initialising String as empty
    String s = "";
    for (int i = 0; i < n; i++)
    {
        s += "10";
    }
    return s;
}

// Function to return the decimal equivalent
// of the given binary String
static int binaryToDecimal(String n)
{
    String num = n;
    int dec_value = 0;

    // Initializing base value to 1
    // i.e 2^0
    int base_t = 1;

    int len = num.Length;
    for (int i = len - 1; i >= 0; i--)
    {
        if (num[i] == '1')
            dec_value = dec_value + base_t;
        base_t = base_t * 2;
    }

    return dec_value;
}

// Function that calls the constructString
// and binarytodecimal and returns the answer
static int findNumber(int n)
{
    String s = constructString(n - 1);
    int num = binaryToDecimal(s);
    return num;
}

// Driver code
static public void Main ()
{
    int n = 4;
    Console.Write(findNumber(n));
}
}

// This code is contributed by ajit
```

## java 描述语言

```cpp
<script>

// JavaScript implementation of above approach

// Function to return the String generated
// by appending "10" n-1 times
function constructString(n)
{
    // Initialising String as empty
    var s = "";
    for (var i = 0; i < n; i++)
    {
        s += "10";
    }
    return s;
}

// Function to return the decimal equivalent
// of the given binary String
function binaryToDecimal(n)
{
    var num = n;
    var dec_value = 0;

    // Initializing base value to 1
    // i.e 2^0
    var base = 1;

    var len = num.length;
    for (var i = len - 1; i >= 0; i--)
    {
        if (num.charAt(i) == '1')
            dec_value += base;
        base = base * 2;
    }

    return dec_value;
}

// Function that calls the constructString
// and binarytodecimal and returns the answer
function findNumber(n)
{
    var s = constructString(n - 1);
    var num = binaryToDecimal(s);
    return num;
}

// Driver code
var n = 4;

document.write(findNumber(n));

// This code is contributed by Amit Katiyar

</script>
```

**Output:** 

```cpp
42
```

**高效方法:**如果我们将数字转换为基数 4，我们可以看到一个有趣的模式如下:

<figure class="table">2 55

| n | Decimal equivalent | Binary equivalent | Base _ 4 |
| one | Zero | Zero | Zero |
| Twenty-two |
| four | forty-two | One hundred and one thousand and ten | Two hundred and twenty-two |
| One hundred and seventy | Ten million one hundred and one thousand and ten | Two thousand two hundred and twenty-two |

T68</figure>

我们实际上是在 base4 中为每个**nT5【术语】追加**2**，即对于 **n = 7** 而言，我们在 base4 中的数字应该是**(n–1)**，即 **6 个连续的 2**。
现在我们要记住一点，因为我们知道，如果我们从任何基数 **m** 转换到基数 **10** 即小数，那么解就是**(n0 * m<sup>0</sup>+n1 * m<sup>1</sup>+N2 * m<sup>2</sup>+…。+ n * m <sup>n</sup> )** 。所以由于我们的基数是 **4** 通过进一步的计算我们可以发现我们需要的个数 **n** 可以利用 **O(1)** 时间复杂度中的推导公式来找到。
**配方:**** 

> A(n) =地板((2/3)*(4<sup>n–1</sup>))

以下是上述方法的实现:

## C++

```cpp
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

#define ll long long int

// Function to compute number
// using our deduced formula
ll findNumber(int n)
{
    // Initialize num to n-1
    ll num = n - 1;
    num = 2 * (ll)pow(4, num);
    num = floor(num / 3.0);
    return num;
}

// Driver code
int main()
{
    int n = 5;
    cout << findNumber(n);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java implementation of the approach
import java.io.*;

class GFG
{

// Function to compute number
// using our deduced formula
static int findNumber(int n)
{
    // Initialize num to n-1
    int num = n - 1;
    num = 2 * (int)Math.pow(4, num);
    num = (int)Math.floor(num / 3.0);
    return num;
}

// Driver code
public static void main (String[] args)
{
    int n = 5;
    System.out.println (findNumber(n));
}
}

// The code is contributed by ajit.
```

## 蟒蛇 3

```cpp
# Python3 implementation of the approach

# Function to compute number
# using our deduced formula
def findNumber(n) :

    # Initialize num to n-1
    num = n - 1;
    num = 2 * (4 ** num);
    num = num // 3;
    return num;

# Driver code
if __name__ == "__main__" :

    n = 5;
    print(findNumber(n));

# This code is contributed by AnkitRai01
```

## C#

```cpp
// C# implementation of the approach
using System;

class GFG
{

// Function to compute number
// using our deduced formula
static int findNumber(int n)
{
    // Initialize num to n-1
    int num = n - 1;
    num = 2 * (int)Math.Pow(4, num);
    num = (int)Math.Floor(num / 3.0);
    return num;
}

// Driver code
static public void Main ()
{

    int n = 5;
    Console.Write(findNumber(n));
}
}

// The code is contributed by Tushil.
```

## java 描述语言

```cpp
<script>
    // Javascript implementation of the approach

    // Function to compute number
    // using our deduced formula
    function findNumber(n)
    {
        // Initialize num to n-1
        let num = n - 1;
        num = 2 * Math.pow(4, num);
        num = Math.floor(num / 3.0);
        return num;
    }

    let n = 5;
    document.write(findNumber(n));

</script>
```

**Output:** 

```cpp
170
```