# 用 C# 中的异或运算符进行号码交换的程序

> 原文:[https://www . geesforgeks . org/program-to-swap-numbers-use-xor-operator-in-c-sharp/](https://www.geeksforgeeks.org/program-to-swap-numbers-using-xor-operator-in-c-sharp/)

C# 程序使用按位异或运算交换两个数字。给定两个变量，x 和 y，用异或语句交换两个变量。

**示例:**

```cs
Input: 300 400 

Output: 400 300 

Explanation: 
x = 300 y = 400 
x = 400 y = 300
```

## C#

```cs
// C# Program to Swap the two Numbers
// using Bitwise XOR Operation
using System;
using System.Text;

namespace Test {
class GFG {

  static void Main(string[] args) {
    int x, y;
    Console.WriteLine("Enter two numbers \n");
    x = int.Parse(Console.ReadLine());
    y = int.Parse(Console.ReadLine());

    // printing the numbers before swapping
    Console.WriteLine("Numbers before swapping");
    Console.WriteLine("x = {0} \t b = {1}", x, y);

    // swapping
    x = x ^ y;
    y = x ^ y;
    x = x ^ y;

    // printing the numbers after swapping
    Console.WriteLine("Numbers after swapping");
    Console.WriteLine("x = {0} \t b = {1}", x, y);

    Console.ReadLine();
  }
}
}
```

**输出:**

```cs
Enter two numbers 

Numbers before swapping
x = 300      b = 400
Numbers after swapping
x = 400      b = 300

```