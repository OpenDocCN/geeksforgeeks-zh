# 打印给定数字单位位数的倍数

> 原文:[https://www . geeksforgeeks . org/print-给定数字的单位倍数/](https://www.geeksforgeeks.org/print-multiples-of-unit-digit-of-given-number/)

给定一个数字![N  ](img/05447a6f3ec73065b361522074101320.png "Rendered by QuickLaTeX.com")。任务是打印 **N** 单位位数从 **N** 到 **N** 的倍数。
**注**:如果单位数字为 **0** ，则打印 **10** 的倍数。
**举例:**

```cpp
Input : 39 
Output : 9 18 27 36
Explanation : The unit digit of 39 is 9.
So the multiples of 9 between 9 and 39 are:
9, 18, 27, 36

Input : 25
Output : 5 10 15 20 25
```

**简单方法**

1.  找到输入数字的单位数字。N 的单位数字将是(N%10)，即 N 除以 10 后的余数。
2.  检查单位数字是否为 0。
    *   如果是，那么考虑倍数为 10。
3.  打印单位数字的倍数，直到它小于或等于输入数字。

以下是上述方法的实现:

## C++

```cpp
// C++ program to print multiples of
// Unit Digit of Given Number
#include <iostream>

using namespace std;

// Function to print the multiples
// of unit digit
void printMultiples(int n)
{
    // Find the unit digit of
    // the given number
    int unit_digit = n % 10;

    // if the unit digit is 0 then
    // change it to 10
    if (unit_digit == 0)
        unit_digit = 10;

    // print the multiples of unit digit
    // until the multiple is less than
    // or equal to n
    for (int i = unit_digit; i <= n; i += unit_digit)
        cout << i << " ";
}

// Driver Code
int main()
{
    int n = 39;

    printMultiples(n);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to print multiples of
// Unit Digit of Given Number
import java.io.*;

class GFG
{

// Function to print the multiples
// of unit digit
static void printMultiples(int n)
{
    // Find the unit digit of
    // the given number
    int unit_digit = n % 10;

    // if the unit digit is 0 then
    // change it to 10
    if (unit_digit == 0)
        unit_digit = 10;

    // print the multiples of unit digit
    // until the multiple is less than
    // or equal to n
    for (int i = unit_digit; i <= n; i += unit_digit)
        System.out.print( i + " ");
}

    // Driver Code
    public static void main (String[] args)
    {
        int n = 39;
        printMultiples(n);
    }
}

// This code is contributed by inder_mca
```

## 蟒蛇 3

```cpp
# Python3 program to print multiples
# of Unit Digit of Given Number

# Function to print the multiples
# of unit digit
def printMultiples(n):

    # Find the unit digit of
    # the given number
    unit_digit = n % 10

    # if the unit digit is 0 then
    # change it to 10
    if (unit_digit == 0):
        unit_digit = 10

    # print the multiples of unit digit
    # until the multiple is less than
    # or equal to n
    for i in range(unit_digit, n + 1,
                   unit_digit):
        print(i, end = " ")

# Driver Code
n = 39

printMultiples(n)

# This code is contributed by Mohit Kumar
```

## C#

```cpp
// C# program to print multiples of
// Unit Digit of Given Number
using System;

class GFG
{

    // Function to print the multiples
    // of unit digit
    static void printMultiples(int n)
    {
        // Find the unit digit of
        // the given number
        int unit_digit = n % 10;

        // if the unit digit is 0 then
        // change it to 10
        if (unit_digit == 0)
            unit_digit = 10;

        // print the multiples of unit digit
        // until the multiple is less than
        // or equal to n
        for (int i = unit_digit; i <= n; i += unit_digit)
            Console.Write( i + " ");
    }

        // Driver Code
        public static void Main ()
        {
            int n = 39;
            printMultiples(n);
        }
}

// This code is contributed by Ryuga
```

## java 描述语言

```cpp
<script>

      // JavaScript program to print multiples of
      // Unit Digit of Given Number

      // Function to print the multiples
      // of unit digit
      function printMultiples(n)
      {
        // Find the unit digit of
        // the given number
        var unit_digit = parseInt(n % 10);

        // if the unit digit is 0 then
        // change it to 10
        if (unit_digit == 0) unit_digit = 10;

        // print the multiples of unit digit
        // until the multiple is less than
        // or equal to n
        for (var i = unit_digit; i <= n;
        i += unit_digit)
          document.write(i + " ");
      }

      // Driver Code
      var n = 39;
      printMultiples(n);

</script>
```

**Output:** 

```cpp
9 18 27 36
```