# 通过重新排列位来最大化数量

> 原文:[https://www . geesforgeks . org/maximum-number-重排-bits/](https://www.geeksforgeeks.org/maximize-number-rearranging-bits/)

给定一个无符号数，用给定的无符号数的位数找出可以形成的最大数。

**示例:**

```cpp
Input : 1 (0000....0001)
Output : 2147483648 (1000....0000)

Input : 7 (0000....0111)
Output : 3758096384 (0111....0000)
```

**方法 1(简单)**
1。使用简单的十进制到二进制表示技术找到数字的二进制表示。
2。计数二进制表示中等于“n”的设置位数。
3。创建一个二进制表示，其“n”个最高有效位设置为 1。
4。将二进制表示转换回数字。

## C++

```cpp
// An simple C++ program to find
// minimum number formed by bits of a
// given number.
#include <bits/stdc++.h>
#define ll unsigned int
using namespace std;

// Returns maximum number formed by
// bits of a given number.
ll maximize(ll a)
{
    // _popcnt32(a) gives number of 1's
    // present in binary representation of a.
    ll n = _popcnt32(a);

    // Set most significant n bits of res.
    ll res = 0;
    for (int i=1; i<=n; i++)
       res |= (1 << (32 - i));

    return res;
}

// Driver function.
int main()
{
    ll a = 1;
    cout << maximize(a) << endl;
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// An simple Java program to find
// minimum number formed by bits
// of a given number.
import java.io.*;

class GFG
{
    private static int _popcnt32(long number)
    {
        int counter = 0;

        while(number > 0)
        {
            if(number % 2 == 1)
            {
                counter++ ;
            }

            //or number = number >> 1
            number = number / 2;
        }
        return counter;
    }

    // Returns maximum number formed
    // by bits of a given number.
    static long maximize(long a)
    {
        // _popcnt32(a) gives number
        // of 1's present in binary
        // representation of a.
        int n = _popcnt32(a);

        // Set most significant
        // n bits of res.
        long res = 0;
        for (int i = 1; i <= n; i++)
        res = (int)res | (1 << (32 - i));

        return Math.abs(res);
    }

    // Driver Code
    public static void main(String args[])
    {
        long a = 1;
        System.out.print(maximize(a));
    }
}

// This code is contributed by
// Manish Shaw(manishshaw1)
```

## 蟒蛇 3

```cpp
# An simple Python program to
# find minimum number formed
# by bits of a given number.
def _popcnt32(number) :
    counter = 0

    while(number > 0) :
        if(number % 2 == 1) :
            counter = counter + 1

        # or number = number >> 1
        number = int(number / 2)

    return counter

# Returns maximum number formed
# by bits of a given number.
def maximize(a) :

    # _popcnt32(a) gives number
    # of 1's present in binary
    # representation of a.
    n = _popcnt32(a)

    # Set most significant
    # n bits of res.
    res = 0
    for i in range(1, n + 1) :
        res = int(res |
                 (1 << (32 - i)))

    return abs(res)

# Driver Code
a = 1
print (maximize(a))

# This code is contributed by
# Manish Shaw(manishshaw1)
```

## C#

```cpp
// An simple C# program to find
// minimum number formed by bits
// of a given number.
using System;

class GFG
{

    // Returns maximum number formed
    // by bits of a given number.
    static long maximize(long a)
    {
        // _popcnt32(a) gives number
        // of 1's present in binary
        // representation of a.
        string binaryString = Convert.ToString(a, 2);
        int n = binaryString.Split(new [] {'0'},
                StringSplitOptions.RemoveEmptyEntries).Length;

        // Set most significant n bits of res.
        long res = 0;
        for (int i = 1; i <= n; i++)
        res = (int)res | (1 << (32 - i));

        return Math.Abs(res);
    }

    // Driver Code.
    static void Main()
    {
        long a = 1;
        Console.WriteLine(maximize(a));
    }
}
// This code is contributed by
// Manish Shaw(manishshaw1)
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// An simple PHP program to find
// minimum number formed by bits
// of a given number.
function _popcnt32($number)
{
    $counter = 0;

    while($number > 0)
    {
        if($number % 2 == 1)
        {
            $counter++ ;
        }

        //or number = number >> 1
        $number = intval($number / 2);
    }
    return $counter;
}

// Returns maximum number formed
// by bits of a given number.
function maximize($a)
{
    // _popcnt32(a) gives number
    // of 1's present in binary
    // representation of a.
    $n = _popcnt32($a);

    // Set most significant
    // n bits of res.
    $res = 0;
    for ($i = 1; $i <= $n; $i++)
    $res = intval($res |
                 (1 << (32 - $i)));

    return abs($res);
}

// Driver Code
$a = 1;
echo (maximize($a));

// This code is contributed by
// Manish Shaw(manishshaw1)
?>
```

## java 描述语言

```cpp
<script>

// An simple JavaScript program to find
// minimum number formed by bits of a
// given number.

function _popcnt32(number)
{
    var counter = 0;

    while(number > 0)
    {
        if(number % 2 == 1)
        {
            counter++ ;
        }

        //or number = number >> 1
        number = parseInt(number / 2);
    }
    return counter;
}

// Returns maximum number formed by
// bits of a given number.
function maximize(a)
{
    // _popcnt32(a) gives number of 1's
    // present in binary representation of a.
    var n = _popcnt32(a);

    // Set most significant n bits of res.
    var res = 0;
    for (var i=1; i<=n; i++)
       res |= (1 << (32 - i));

    return Math.abs(res);
}

// Driver function.
var a = 1;
document.write(maximize(a));

</script>
```

**Output:** 

```cpp
2147483648
```