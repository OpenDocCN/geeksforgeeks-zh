# 打印镜像空心平行四边形的程序

> 原文:[https://www . geesforgeks . org/program-to-print-mirrored-空心-平行四边形/](https://www.geeksforgeeks.org/program-to-print-mirrored-hollow-parallelogram/)

给定行的长度和列的宽度，任务是打印镜像中空平行四边形。
**例:**

```cpp
Input: rows = 5, cols = 8
Output:
********
 *      *
  *      *
   *      *
    ********
```

## C++

```cpp
// CPP program to print hollow mirrored
// parallelogram star pattern series

#include <iostream>
using namespace std;

// function for creating pattern
void Pattern(int rows, int cols)
{
    int i, j;

    for (i = 1; i <= rows; i++) {

        // Printing spaces
        for (j = 1; j < i; j++) {
            cout << " ";
        }

        // Printing hollow parallelogram
        for (j = 1; j <= cols; j++) {

            if (i == 1 || i == rows
                || j == 1 || j == cols) {
                cout << "*";
            }
            else {
                cout << " ";
            }
        }

        cout << "\n";
    }
}

// driver code
int main()
{
    // Get number of rows and columns
    int rows = 5, cols = 8;

    // Print the Pattern
    Pattern(rows, cols);

    return 0;
}
```

## C

```cpp
// C program to print hollow mirrored
// parallelogram star pattern series

#include <stdio.h>

// function for creating pattern
void Pattern(int rows, int cols)
{
    int i, j;

    for (i = 1; i <= rows; i++) {

        // Printing spaces
        for (j = 1; j < i; j++) {
            printf(" ");
        }

        // Printing hollow parallelogram
        for (j = 1; j <= cols; j++) {

            if (i == 1 || i == rows
                || j == 1 || j == cols) {
                printf("*");
            }
            else {
                printf(" ");
            }
        }

        printf("\n");
    }
}

// driver code
int main()
{
    // Get number of rows and columns
    int rows = 5, cols = 8;

    // Print the Pattern
    Pattern(rows, cols);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to print hollow mirrored
// parallelogram star pattern series
import java.util.*;

class solution
{

// function for creating pattern
static void Pattern(int rows, int cols)
{
    int i, j;

    for (i = 1; i <= rows; i++) {

        // Printing spaces
        for (j = 1; j < i; j++) {
            System.out.print(" ");
        }

        // Printing hollow parallelogram
        for (j = 1; j <= cols; j++) {

            if (i == 1 || i == rows
                || j == 1 || j == cols) {
                 System.out.print("*");
            }
            else {
             System.out.print(" ");
            }
        }

         System.out.print("\n");
    }
}

// driver code
public static void main(String args[])
{
    // Get number of rows and columns
    int rows = 5, cols = 8;

    // Print the Pattern
    Pattern(rows, cols);

}

}
```

## 蟒蛇 3

```cpp
# Python3 program to prhollow mirrored
# parallelogram star pattern series
import math as mt

# function for creating pattern
def Pattern(rows, cols):

    for i in range(1, rows + 1):

        # Printing spaces
        for j in range(1, i):
            print(end = " ")

        # Printing hollow parallelogram
        for j in range(1, cols + 1):

            if (i == 1 or i == rows or
                j == 1 or j == cols):
                print("*", end = "")
            else:
                print(end = " ")

        print()

# Driver code

# Get number of rows and columns
rows, cols = 5, 8

# Print the Pattern
Pattern(rows, cols)

# This code is contributed by
# mohit kumar 29
```

## C#

```cpp
// C# program to print hollow mirrored
// parallelogram star pattern series
using System;

class GFG
{

// function for creating pattern
static void Pattern(int rows, int cols)
{
    int i, j;

    for (i = 1; i <= rows; i++)
    {

        // Printing spaces
        for (j = 1; j < i; j++)
        {
            Console.Write(" ");
        }

        // Printing hollow parallelogram
        for (j = 1; j <= cols; j++)
        {

            if (i == 1 || i == rows
                || j == 1 || j == cols)
            {
                Console.Write("*");
            }
            else
            {
                Console.Write(" ");
            }
        }

        Console.Write("\n");
    }
}

// Driver code
public static void Main()
{
    // Get number of rows and columns
    int rows = 5, cols = 8;

    // Print the Pattern
    Pattern(rows, cols);
}
}

// This code is contributed by RAJPUT-JI
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to print hollow mirrored
// parallelogram star pattern series

// function for creating pattern
function Pattern($rows, $cols)
{
    for ($i = 1; $i <= $rows; $i++)
    {

        // Printing spaces
        for ($j = 1; $j < $i; $j++)
        {
            echo " ";
        }

        // Printing hollow parallelogram
        for ($j = 1; $j <= $cols; $j++)
        {

            if ($i == 1 || $i == $rows||
                $j == 1 || $j == $cols)
            {
                echo "*";
            }
            else
            {
                echo " ";
            }
        }

        echo "\n";
    }
}

// Driver Code

// Get number of rows and columns
$rows = 5; $cols = 8;

// Print the Pattern
Pattern($rows, $cols);

// This code is contributed by
// Akanksha Rai
?>
```

## java 描述语言

```cpp
<script>

      // JavaScript program to print hollow mirrored
      // parallelogram star pattern series

      // function for creating pattern
      function Pattern(rows, cols) {
        var i, j;

        for (i = 1; i <= rows; i++) {
          // Printing spaces
          for (j = 1; j < i; j++) {
            document.write("  ");
          }

          // Printing hollow parallelogram
          for (j = 1; j <= cols; j++) {
            if (i == 1 || i == rows || j == 1 || j == cols) {
              document.write("*");
            } else {
              document.write("  ");
            }
          }

          document.write("<br>");
        }
      }

      // driver code
      // Get number of rows and columns
      var rows = 5,
        cols = 8;

      // Print the Pattern
      Pattern(rows, cols);

</script>
```

**Output:** 

```cpp
********
 *      *
  *      *
   *      *
    ********
```