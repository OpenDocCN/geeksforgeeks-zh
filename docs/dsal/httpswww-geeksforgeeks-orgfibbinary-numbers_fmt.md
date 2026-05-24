# 二进制数（二进制中没有连续的 1）

> 原文：[https://www.geeksforgeeks.org/fibbinary-numbers/](https://www.geeksforgeeks.org/fibbinary-numbers/)

给定 `N`，检查该数是否为二进制数。Fibbinary 数是整数，其二进制表示不包含连续的 1。

**示例：**

```
Input : 10
Output : YES
Explanation: 1010 is the binary representation 
             of 10 which does not contains any 
             consecutive 1's.

Input : 11
Output : NO
Explanation: 1011 is the binary representation 
             of 11, which contains consecutive 
             1's 
```

这样做的想法是右移数字，直到 `n != 0`。对于 1 的每个二进制表示，检查找到的最后一位是否为 1。通过做 `a(n & 1)` 得到整数的二进制表示的最后一位。如果二进制表示的最后一位是 1，右移之前的前一位也是 1，我们会遇到连续的 1。因此我们得出结论，它不是一个二进制数。

前几个数字是：

```
0, 2, 4, 8, 10, 16, 18, 20.......
```

## C++

```
// CPP program to check if a number
// is fibinnary number or not
#include <iostream>
using namespace std;

// function to check if binary
// representation of an integer
// has consecutive 1s
bool checkFibinnary(int n)
{
    // stores the previous last bit
    // initially as 0
    int prev_last = 0;

    while (n)
    {
        // if current last bit and
        // previous last bit is 1
        if ((n & 1) && prev_last)
            return false;

        // stores the last bit
        prev_last = n & 1;

        // right shift the number
        n >>= 1;
    }

    return true;
}

// Driver code to check above function
int main()
{
    int n = 10;
    if (checkFibinnary(n))
        cout << "YES";
    else
        cout << "NO";
    return 0;
}
```

## Java

```
// Java program to check if a number
// is fibinnary number or not
class GFG {

    // function to check if binary
    // representation of an integer
    // has consecutive 1s
    static boolean checkFibinnary(int n)
    {

        // stores the previous last bit
        // initially as 0
        int prev_last = 0;

        while (n != 0)
        {

            // if current last bit and
            // previous last bit is 1
            if ((n & 1) != 0 && prev_last != 0)

                return false;

            // stores the last bit
            prev_last = n & 1;

            // right shift the number
            n >>= 1;
        }

        return true;
    }

    // Driver code to check above function
    public static void main(String[] args)
    {
        int n = 10;

        if (checkFibinnary(n) == true)
            System.out.println("YES");
        else
            System.out.println("NO");
    }
}

// This code is contributed by
// Smitha Dinesh Semwal
```

## Python 3

```
# Python 3 program to check if a
# number is fibinnary number or
# not

# function to check if binary
# representation of an integer
# has consecutive 1s
def checkFibinnary(n):

    # stores the previous last bit
    # initially as 0
    prev_last = 0

    while (n):

        # if current last bit and
        # previous last bit is 1
        if ((n & 1) and prev_last):
            return False

        # stores the last bit
        prev_last = n & 1

        # right shift the number
        n >>= 1

    return True

# Driver code
n = 10

if (checkFibinnary(n)):
    print("YES")
else:
    print("NO")

# This code is contributed by Smitha Dinesh Semwal
```

## C#

```
// C# program to check if a number
// is fibinnary number or not
using System;

class GFG {

    // function to check if binary
    // representation of an integer
    // has consecutive 1s
    static bool checkFibinnary(int n)
    {

        // stores the previous last bit
        // initially as 0
        int prev_last = 0;

        while (n != 0)
        {

            // if current last bit and
            // previous last bit is 1
            if ((n & 1) != 0 && prev_last != 0)

                return false;

            // stores the last bit
            prev_last = n & 1;

            // right shift the number
            n >>= 1;
        }

        return true;
    }

    // Driver code to check above function
    public static void Main()
    {
        int n = 10;

        if (checkFibinnary(n) == true)
            Console.WriteLine("YES");
        else
            Console.WriteLine("NO");
    }
}

// This code is contributed by vt_m.
```

## PHP

```
<?php
// PHP program to check if a number
// is fibinnary number or not

// function to check if binary
// representation of an integer
// has consecutive 1s
function checkFibinnary($n)
{
    // stores the previous last bit
    // initially as 0
    $prev_last = 0;

    while ($n)
    {
        // if current last bit and
        // previous last bit is 1
        if (($n & 1) && $prev_last)
            return false;

        // stores the last bit
        $prev_last = $n & 1;

        // right shift the number
        $n >>= 1;
    }
    return true;
}

// Driver code
$n = 10;
if (checkFibinnary($n))
    echo "YES";
else
    echo "NO";

// This code is contributed by mits
?>
```

## JavaScript

```
<script>
    // javascript program to check if a number
    // is fibinnary number or not   
    // function to check if binary
    // representation of an integer
    // has consecutive 1s
    function checkFibinnary(n) {

        // stores the previous last bit
        // initially as 0
        var prev_last = 0;

        while (n != 0) {

            // if current last bit and
            // previous last bit is 1
            if ((n & 1) != 0 && prev_last != 0)

                return false;

            // stores the last bit
            prev_last = n & 1;

            // right shift the number
            n >>= 1;
        }

        return true;
    }

    // Driver code to check above function

    var n = 10;

    if (checkFibinnary(n) == true)
        document.write("YES");
    else
        document.write("NO");

// This code contributed by Rajput-Ji
</script>
```

**输出：**

```
YES
```

**时间复杂度：** `O(log(n))`

[二进制数(二进制中没有连续的 1)–O(1)接近](https://www.geeksforgeeks.org/fibbinary-numbers-no-consecutive-1s-binary-o1-approach/)