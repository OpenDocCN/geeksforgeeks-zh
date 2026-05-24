# 用递归求一个数的位数和的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-程序使用递归查找数字的位数总和/](https://www.geeksforgeeks.org/c-sharp-program-to-find-sum-of-digits-of-a-number-using-recursion/)

给定一个数，我们需要用递归求该数的位数之和。在 C# 中，递归是函数直接或间接调用自身的过程，相应的函数称为递归函数。它很容易用来解决问题，就像在这篇文章中使用递归，我们会找到一个数字的位数之和。

**例**

```cs
Input: 456
Output: 15

Input: 123
Output: 6
```

**进场:**

> 要使用递归查找数字的位数总和，请遵循以下方法:
> 
> *   我们用参数 n 调用 SumOfDigits 函数。
> *   在函数中，最后一个数字由 n % 10 检索。
> *   该函数被递归调用，参数为 n / 10。[即 n % 10+sumofgit(n/10)]
> *   该函数被递归调用，直到 n > 0。

**例 1:**

## C#

```cs
// C# program to find the sum of digits of a number
// using recursion
using System;

class GFG{

// Method to check sum of digit using recursion
static int SumOfDigit(int n)
{

    // If the n value is zero then we
    // return sum as 0.
    if (n == 0)
        return 0;

    // Last digit + recursivly calling n/10
    return(n % 10 + SumOfDigit(n / 10));
}

// Driver code
public static void Main()
{
    int n = 123;
    int ans = SumOfDigit(n);

    Console.Write("Sum = " + ans);
}
}
```

**Output**

```cs
Sum = 6
```

**例 2:**

## C#

```cs
// C# program to find the sum of digits of a number 
// using recursion
// Here, we take input from user
using System;

class GFG{

// Method to check sum of digit using recursion
static int SumOfDigit(int n)
{

    // If the n value is zero then we return sum as 0.
    if (n == 0)
        return 0;

    // Last digit + recursivly calling n/10
    return (n % 10 + SumOfDigit(n / 10));
}

// Driver code
public static void Main()
{
    int number, res;

    // Taking input from user
    Console.WriteLine("Hi! Enter the Number: ");
    number = int.Parse(Console.ReadLine());
    res = SumOfDigit(number);

    // Displaying the output
    Console.WriteLine("Sum of Digits is {0}", res);
    Console.ReadLine();
}
}
```

**输出:**

```cs
Hi! Enter the Number:
12345
The Sum of Digits is 15
```