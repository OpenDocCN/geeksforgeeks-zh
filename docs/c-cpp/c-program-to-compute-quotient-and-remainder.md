# 计算商和余数的 C 程序

> 原文:[https://www . geesforgeks . org/c-程序到计算商和余数/](https://www.geeksforgeeks.org/c-program-to-compute-quotient-and-remainder/)

给定两个数 A 和 b，任务是写一个程序，求 A 除以 b 时这两个数的商和余数。

![quotient_remainder](img/48307f093027833b1699d7ab70c03dbf.png)

**示例**:

```cpp
Input: A = 2, B = 6
Output: Quotient = 0, Remainder = 2

Input: A = 17, B = 5
Output: Quotient = 3, Remainder = 2

```

在下面的程序中，为了找到这两个数字的商和余数，首先要求用户输入两个数字。使用 [scanf()](https://www.geeksforgeeks.org/scanf-fscanf-sscanf-scanf_s-fscanf_s-sscanf_s/) 功能扫描输入，并存储在变量![A](img/cc10d3b72431cdd6ba563d3cc2a57d7f.png "Rendered by QuickLaTeX.com")和![B](img/76d8ee369d9167cdfb7489cf2a197486.png "Rendered by QuickLaTeX.com")中。然后，使用算术运算符![/](img/5e0a3a2aebbafd9e20666ad6a118f4c1.png "Rendered by QuickLaTeX.com")对变量![A](img/cc10d3b72431cdd6ba563d3cc2a57d7f.png "Rendered by QuickLaTeX.com")和![B](img/76d8ee369d9167cdfb7489cf2a197486.png "Rendered by QuickLaTeX.com")进行除法，以获得作为结果存储在变量**商**中的商；并使用算术运算符 **%** 将余数作为结果存储在变量**余数**中。

下面是求两个数的商和余数的程序:

## C

```cpp
// C program to find quotient
// and remainder of two numbers

#include <stdio.h>

int main()
{
    int A, B, quotient = 0, remainder = 0;

    // Ask user to enter the two numbers
    printf("Enter two numbers A and B : \n");

    // Read two numbers from the user || A = 17, B = 5
    scanf("%d%d", &A, &B);

    // Calclulate the quotient of A and B using '/' operator
    quotient = A / B;

    // Calclulate the remainder of A and B using '%' operator
    remainder = A % B;

    // Print the result
    printf("Quotient when A/B is: %d\n", quotient);
    printf("Remainder when A/B is: %d", remainder);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// java program to find quotient
// and remainder of two numbers

import java.io.*;
import java.util.Scanner;

class GFG {

    public static void main (String[] args) {
         Scanner input = new Scanner(System.in);
    int A = input.nextInt();
    int B= input.nextInt();
    int 
    quotient = 0, remainder = 0;

    // Ask user to enter the two numbers
    System.out.println("Enter two numbers A and B : "+" "+ A+" "+ B);

    // Read two numbers from the user || A = 17, B = 5

    // Calclulate the quotient of A and B using '/' operator
    quotient = A / B;

    // Calclulate the remainder of A and B using '%' operator
    remainder = A % B;

    // Print the result
    System.out.println("Quotient when A/B is: "+ quotient);
    System.out.println("Remainder when A/B is: "+ remainder);
    }
}
//this code is contributed by anuj_67..
```

## 蟒蛇 3

```cpp
# Python3 program to find quotient 
# and remainder of two numbers

if __name__=='__main__':

    quotient = 0
    remainder = 0

#Read two numbers from the user || A = 17, B = 5
    A, B = [int(x) for x in input().split()]

#Calclulate the quotient of A and B using '/' operator
    quotient = int(A / B)

#Calclulate the remainder of A and B using '%' operator
    remainder = A % B

#Print the result
    print("Quotient when A/B is:", quotient)
    print("Remainder when A/B is:", remainder)

#this code is contributed by Shashank_Sharma
```

**Output**:

```cpp
Enter two numbers A and B : 17 5
Quotient when A/B is: 3
Remainder when A/B is: 2

```