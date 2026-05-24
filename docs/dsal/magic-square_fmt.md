# 幻方

> 原文： [https://www.geeksforgeeks.org/magic-square/](https://www.geeksforgeeks.org/magic-square/)

## 幻方定义

阶数为`n`的[幻方](http://en.wikipedia.org/wiki/Magic_square)是正方形中`n ^ 2`个数字（通常是不同整数）的排列，以使所有行，所有列以及两个对角线中的`n`个数字总和为相同的常数。 幻方包含从 1 到`n ^ 2`的整数。

每行，每一列和对角线中的常数之和称为[魔术常数或魔术之和](http://en.wikipedia.org/wiki/Magic_constant)。正常魔术方阵的魔术常数仅取决于`n`，并且具有以下值：`M = n (n ^ 2 + 1) / 2`。

```
For normal magic squares of order n = 3, 4, 5, ...,
 the magic constants are: 15, 34, 65, 111, 175, 260, ... 
```

在本文中，我们将讨论如何以编程方式生成大小为`n`的幻方。 在继续之前，请考虑以下示例：

```
Magic Square of size 3

  2   7   6
  9   5   1
  4   3   8
Sum in each row & each column = 3*(3^2+1)/2 = 15

Magic Square of size 5

  9   3  22  16  15
  2  21  20  14   8
 25  19  13   7   1
 18  12   6   5  24
 11  10   4  23  17
Sum in each row & each column = 5*(5^2+1)/2 = 65

Magic Square of size 7

 20  12   4  45  37  29  28
 11   3  44  36  35  27  19
  2  43  42  34  26  18  10
 49  41  33  25  17   9   1
 40  32  24  16   8   7  48
 31  23  15  14   6  47  39
 22  21  13   5  46  38  30
Sum in each row & each column = 7*(7^2+1)/2 = 175

```

您是否找到了存储数字的任何模式？

在任何幻方中，第一个数字（即 1）存储在位置`(n / 2, n - 1)`。 将此位置设为`(i, j)`。 下一个数字存储在位置`(i - 1, j + 1)`，在这里我们可以将每行和列视为圆形数组，即它们环绕。

## 生成算法

### 放置规则

**三个条件成立**：

1.  下一个数字的位置是通过将前一个数字的行号减 1，再将前一个数字的列号增 1 来计算的。在任何时候，如果计算出的行位置变为 -1，它将绕回`n - 1`。 同样，如果计算出的列位置变为`n`，则它将环绕为 0。
2.  如果魔方在计算位置处已经包含数字，则计算列位置将减少 2，计算行位置将增加 1。
3.  如果计算的行位置是 -1，计算的列位置是`n`，则新位置将是：`(0, n-2)`。

```
Example:
Magic Square of size 3

 2  7  6
 9  5  1
 4  3  8 

Steps:
1\. position of number 1 = (3/2, 3-1) = (1, 2)
2\. position of number 2 = (1-1, 2+1) = (0, 0)
3\. position of number 3 = (0-1, 0+1) = (3-1, 1) = (2, 1)
4\. position of number 4 = (2-1, 1+1) = (1, 2)
   Since, at this position, 1 is there. So, apply condition 2.
   new position=(1+1,2-2)=(2,0)
5\. position of number 5=(2-1,0+1)=(1,1)
6\. position of number 6=(1-1,1+1)=(0,2)
7\. position of number 7 = (0-1, 2+1) = (-1,3) // this is tricky, see condition 3 
   new position = (0, 3-2) = (0,1)
8\. position of number 8=(0-1,1+1)=(-1,2)=(2,2) //wrap around
9\. position of number 9=(2-1,2+1)=(1,3)=(1,0) //wrap around

```

基于上述方法，下面是工作代码：

## 代码实现

### C++

```cpp
// C++ program to generate odd sized magic squares
#include <bits/stdc++.h>
using namespace std;
 
// A function to generate odd sized magic squares
void generateSquare(int n)
{
    int magicSquare[n][n];
 
    // set all slots as 0
    memset(magicSquare, 0, sizeof(magicSquare));
 
    // Initialize position for 1
    int i = n / 2;
    int j = n - 1;
 
    // One by one put all values in magic square
    for (int num = 1; num <= n * n;) {
        if (i == -1 && j == n) // 3rd condition
        {
            j = n - 2;
            i = 0;
        }
        else {
            // 1st condition helper if next number
            // goes to out of square's right side
            if (j == n)
                j = 0;
 
            // 1st condition helper if next number
            // is goes to out of square's upper side
            if (i < 0)
                i = n - 1;
        }
        if (magicSquare[i][j]) // 2nd condition
        {
            j -= 2;
            i++;
            continue;
        }
        else
            magicSquare[i][j] = num++; // set number
 
        j++;
        i--; // 1st condition
    }
 
    // Print magic square
    cout << "The Magic Square for n=" << n
         << ":\nSum of "
            "each row or column "
         << n * (n * n + 1) / 2 << ":\n\n";
    for (i = 0; i < n; i++) {
        for (j = 0; j < n; j++)
 
            // setw(7) is used so that the matrix gets
            // printed in a proper square fashion.
            cout << setw(4) << magicSquare[i][j] << " ";
        cout << endl;
    }
}
 
// Driver code
int main()
{
 
    // Works only when n is odd
    int n = 7;
    generateSquare(n);
    return 0;
}
 
// This code is contributed by rathbhupendra
```

### C

```c
// C program to generate odd sized magic squares
#include <stdio.h>
#include <string.h>
 
// A function to generate odd sized magic squares
void generateSquare(int n)
{
    int magicSquare[n][n];
 
    // set all slots as 0
    memset(magicSquare, 0, sizeof(magicSquare));
 
    // Initialize position for 1
    int i = n / 2;
    int j = n - 1;
 
    // One by one put all values in magic square
    for (int num = 1; num <= n * n;) {
        if (i == -1 && j == n) // 3rd condition
        {
            j = n - 2;
            i = 0;
        }
        else {
            // 1st condition helper if next number
            // goes to out of square's right side
            if (j == n)
                j = 0;
 
            // 1st condition helper if next number
            // is goes to out of square's upper side
            if (i < 0)
                i = n - 1;
        }
        if (magicSquare[i][j]) // 2nd condition
        {
            j -= 2;
            i++;
            continue;
        }
        else
            magicSquare[i][j] = num++; // set number
 
        j++;
        i--; // 1st condition
    }
 
    // Print magic square
    printf("The Magic Square for n=%d:\nSum of "
           "each row or column %d:\n\n",
           n, n * (n * n + 1) / 2);
    for (i = 0; i < n; i++) {
        for (j = 0; j < n; j++)
            printf("%3d ", magicSquare[i][j]);
        printf("\n");
    }
}
 
// Driver program to test above function
int main()
{
    int n = 7; // Works only when n is odd
    generateSquare(n);
    return 0;
}
```

### Java

```java
// Java program to generate odd sized magic squares
import java.io.*;
 
class GFG {
    // Function to generate odd sized magic squares
    static void generateSquare(int n)
    {
        int[][] magicSquare = new int[n][n];
 
        // Initialize position for 1
        int i = n / 2;
        int j = n - 1;
 
        // One by one put all values in magic square
        for (int num = 1; num <= n * n;) {
            if (i == -1 && j == n) // 3rd condition
            {
                j = n - 2;
                i = 0;
            }
            else {
                // 1st condition helper if next number
                // goes to out of square's right side
                if (j == n)
                    j = 0;
 
                // 1st condition helper if next number is
                // goes to out of square's upper side
                if (i < 0)
                    i = n - 1;
            }
 
            // 2nd condition
            if (magicSquare[i][j] != 0) {
                j -= 2;
                i++;
                continue;
            }
            else
                // set number
                magicSquare[i][j] = num++;
 
            // 1st condition
            j++;
            i--;
        }
 
        // print magic square
        System.out.println("The Magic Square for " + n
                           + ":");
        System.out.println("Sum of each row or column "
                           + n * (n * n + 1) / 2 + ":");
        for (i = 0; i < n; i++) {
            for (j = 0; j < n; j++)
                System.out.print(magicSquare[i][j] + " ");
            System.out.println();
        }
    }
 
    // driver program
    public static void main(String[] args)
    {
        // Works only when n is odd
        int n = 7;
        generateSquare(n);
    }
}
 
// Contributed by Pramod Kumar
```

## Python

```py
# Python program to generate
# odd sized magic squares
# A function to generate odd
# sized magic squares

def generateSquare(n):
    # 2-D array with all
    # slots set to 0
    magicSquare = [[0 for x in range(n)]
                   for y in range(n)]

    # initialize position of 1
    i = n / 2
    j = n - 1

    # Fill the magic square
    # by placing values
    num = 1
    while num <= (n * n):
        if i == -1 and j == n:  # 3rd condition
            j = n - 2
            i = 0
        else:
            # next number goes out of
            # right side of square
            if j == n:
                j = 0

            # next number goes
            # out of upper side
            if i < 0:
                i = n - 1

        if magicSquare[int(i)][int(j)]:  # 2nd condition
            j = j - 2
            i = i + 1
            continue
        else:
            magicSquare[int(i)][int(j)] = num
            num = num + 1

        j = j + 1
        i = i - 1  # 1st condition

    # Printing magic square
    print("Magic Squre for n =", n)
    print("Sum of each row or column",
          n * (n * n + 1) / 2, "\n")

    for i in range(0, n):
        for j in range(0, n):
            print('%2d ' % (magicSquare[i][j]),
                  end='')

            # To display output
            # in matrix form
            if j == n - 1:
                print()

# Driver Code

# Works only when n is odd
n = 7
generateSquare(n)

# This code is contributed
# by Harshit Agrawal
```

## C#

```cs
// C# program to generate odd sized magic squares
using System;

class GFG {
    // Function to generate odd sized magic squares
    static void generateSquare(int n)
    {
        int[, ] magicSquare = new int[n, n];

        // Initialize position for 1
        int i = n / 2;
        int j = n - 1;

        // One by one put all values in magic square
        for (int num = 1; num <= n * n;) {
            if (i == -1 && j == n) // 3rd condition
            {
                j = n - 2;
                i = 0;
            }
            else {
                // 1st condition helper if next number
                // goes to out of square's right side
                if (j == n)
                    j = 0;

                // 1st condition helper if next number is
                // goes to out of square's upper side
                if (i < 0)
                    i = n - 1;
            }

            // 2nd condition
            if (magicSquare[i, j] != 0) {
                j -= 2;
                i++;
                continue;
            }
            else
                // set number
                magicSquare[i, j] = num++;

            // 1st condition
            j++;
            i--;
        }

        // print magic square
        Console.WriteLine("The Magic Square for " + n
                          + ":");
        Console.WriteLine("Sum of each row or column "
                          + n * (n * n + 1) / 2 + ":");

        for (i = 0; i < n; i++) {
            for (j = 0; j < n; j++)
                Console.Write(magicSquare[i, j] + " ");
            Console.WriteLine();
        }
    }

    // driver program
    public static void Main()
    {
        // Works only when n is odd
        int n = 7;

        generateSquare(n);
    }
}

// This code is contributed by Sam007.
```

## PHP

```php
<?php
// php program to generate odd sized
// magic squares

// A function to generate odd sized 
// magic squares
function generateSquare($n)
{
    // set all slots as 0
    $magicSquare;
    for ($i = 0; $i < $n; $i++)
        for ($j = 0; $j < $n; $j++)
            $magicSquare[$i][$j] = 0;

    // Initialize position for 1
    $i = (int)$n / 2;
    $j = $n - 1;

    // One by one put all values in
    // magic square
    for ($num = 1; $num <= $n * $n; )
    {
        // 3rd condition
        if ($i == -1 && $j == $n) 
        {
            $j = $n-2;
            $i = 0;
        }
        else
        {
            // 1st condition helper if 
            // next number goes to out 
            // of square's right side
            if ($j == $n)
                $j = 0;

            // 1st condition helper if
            // next number is goes to 
            // out of square's upper 
            // side
            if ($i < 0)
                $i = $n-1;
        }
        
        // 2nd condition
        if ($magicSquare[$i][$j]) 
        {
            $j -= 2;
            $i++;
            continue;
        }
        else
            // set number
            $magicSquare[$i][$j] = $num++; 

        // 1st condition
        $j++; $i--; 
    }

    // Print magic square
    echo "The Magic Square for n = " . $n
        . ":\nSum of each row or column "
        . $n * ($n * $n + 1) / 2;
        
    echo "\n\n";
    for ($i = 0; $i < $n; $i++)
    {
        for ($j = 0; $j < $n; $j++)
            echo $magicSquare[$i][$j] . " ";
        echo "\n";
    }
}

// Driver program to test above function

// Works only when n is odd
$n = 7; 
generateSquare ($n);
    
// This code is contributed by mits.
?>
```

输出：

```
The Magic Square for n=7:
Sum of each row or column 175:

  20   12    4   45   37   29   28 
  11    3   44   36   35   27   19 
   2   43   42   34   26   18   10 
  49   41   33   25   17    9    1 
  40   32   24   16    8    7   48 
  31   23   15   14    6   47   39 
  22   21   13    5   46   38   30 
```

注意：此方法仅适用于`n`的奇数值。

参考：

<http://en.wikipedia.org/wiki/Magic_square>