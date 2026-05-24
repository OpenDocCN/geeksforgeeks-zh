# 程序打印空心矩形或方形星形图案

> 原文:[https://www . geesforgeks . org/program-to-print-空心-矩形-或方形-星形-图案/](https://www.geeksforgeeks.org/program-to-print-hollow-rectangle-or-square-star-patterns/)

#### 空心矩形星形图案:

任务打印在给定尺寸的空心图案下面。

```cpp
********************
*                  *
*                  *
*                  *
*                  *
********************
```

**说明:**

*   输入行数和列数。
*   对于矩形行，运行从 1 到行的外部循环。

```cpp
for (i = 1; i < = rows; i++)
```

*   对于矩形列，运行从 1 到列的内部循环。

```cpp
for (j = 1; j < = columns; j++)
```

*   打印第一行或最后一行或第一列或最后一列的星号，否则打印空格。
*   打印一行的所有列后，在内部循环后打印新行。

## C++

```cpp
// C++ code for hollow rectangle
#include <bits/stdc++.h>
using namespace std;

// Function to print hollow rectangle
void print_rectangle(int n, int m)
{
    int i, j;
    for (i = 1; i <= n; i++)
    {
        for (j = 1; j <= m; j++)
        {
            if (i == 1 || i == n ||
                j == 1 || j == m)        
                cout << "*";            
            else
                cout << " ";
        }
        cout << endl;
    }

}

// Driver Code
int main()
{
    int rows = 6, columns = 20;
    print_rectangle(rows, columns);
    return 0;
}

// This code is contributed
// by rathbhupendra
```

## C

```cpp
// C code for hollow rectangle
#include <stdio.h>

// Function to print hollow rectangle
void print_rectangle(int n, int m)
{
    int i, j;
    for (i = 1; i <= n; i++)
    {
        for (j = 1; j <= m; j++)
        {
            if (i==1 || i==n || j==1 || j==m)           
                printf("*");           
            else
                printf(" ");           
        }
        printf("\n");
    }

}

// Driver program for above function
int main()
{
    int rows = 6, columns = 20;
    print_rectangle(rows, columns);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// JAVA code for hollow rectangle
import java.io.*;

class GFG {

    // Function to print hollow rectangle
    static void print_rectangle(int n, int m)
    {
        int i, j;
        for (i = 1; i <= n; i++)
        {
            for (j = 1; j <= m; j++)
            {
                if (i == 1 || i == n ||
                    j == 1 || j == m)           
                    System.out.print("*");           
                else
                    System.out.print(" ");           
            }
            System.out.println();
        }

    }

    // Driver program for above function
    public static void main(String args[])
    {
        int rows = 6, columns = 20;
        print_rectangle(rows, columns);
    }
}

/*This code is contributed by Nikita Tiwari.*/
```

## 蟒蛇 3

```cpp
# Python 3 code for hollow rectangle

# Function to print hollow rectangle
def print_rectangle(n, m) :

    for i in range(1, n+1) :
        for j in range(1, m+1) :
            if (i == 1 or i == n or
                j == 1 or j == m) :
                print("*", end="")           
            else :
                print(" ", end="")           

        print()

# Driver program for above function
rows = 6
columns = 20
print_rectangle(rows, columns)

# This code is contributed by Nikita Tiwari.
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP code for hollow rectangle

// Function to print hollow rectangle
function print_rectangle($n, $m)
{
    $i;
    $j;
    for ($i = 1; $i <= $n; $i++)
    {
        for ($j = 1; $j <= $m; $j++)
        {
            if ($i == 1 || $i == $n ||
                $j == 1 || $j == $m)        
                echo("*");        
            else
                echo(" ");        
        }
        echo("\n");
    }

}

    // Driver Code
    $rows = 6;
    $columns = 20;
    print_rectangle($rows, $columns);

// This code is contributed by nitin mittal
?>
```

## java 描述语言

```cpp
<script>
      // JavaScript code for hollow rectangle
      // Function to print hollow rectangle
      function print_rectangle(n, m)
      {
        var i, j;
        for (i = 1; i <= n; i++)
        {
          for (j = 1; j <= m; j++)
          {
            if (i == 1 || i == n || j == 1 || j == m)
                 document.write("*");
            else
                document.write("  ");
          }
          document.write("<br>");
        }
      }

      // Driver Code
      var rows = 6,
        columns = 20;
      print_rectangle(rows, columns);

      // This code is contributed by rdtank.
    </script>
```

输出:

```cpp
********************
*                  *
*                  *
*                  *
*                  *
********************
```

#### 空心方形星形图案:

```cpp
********
*      *
*      *
*      *
*      *
*      *
*      *
********
```

**说明:**

*   输入行数。
*   对于行，从 1 到 n 的外部循环
*   对于列，从 1 到 N 的内部循环
*   内部循环打印第一行和最后一行或第一列和最后一列的星号。哪个是印星

```cpp
 if i == 1 or i == N or j == 1 or j == N
```

*   否则打印空间。
*   打印完一行的所有列后，在内部循环后打印一个空行。

## C++

```cpp
// C++ code for hollow squares
#include <bits/stdc++.h>
using namespace std;

// Function to print hollow square
void print_square(int n)
{
    int i, j;

    for (i = 1; i <= n; i++)
    {
        for (j = 1; j <= n; j++)
        {
            if (i==1 || i==n || j==1 || j==n)    
                cout << "*";        
            else   
                cout << " ";        
        }
        cout << "\n";
    }

}

// Driver code for above function
int main()
{
    int rows = 8;
    print_square(rows);
    return 0;
}

// This code is contributed by Code_Mech
```

## C

```cpp
// C code for hollow squares
#include <stdio.h>

// Function to print hollow square
void print_square(int n)
{
    int i, j;

    for (i = 1; i <= n; i++)
    {
        for (j = 1; j <= n; j++)
        {
            if (i==1 || i==n || j==1 || j==n)           
                printf("*");           
            else           
                printf(" ");           
        }
        printf("\n");
    }

}

// Driver code for above function
int main()
{
    int rows = 8;
    print_square(rows);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// JAVA code for hollow squares
import java.io.*;

class GFG {

    // Function to print hollow square
    static void print_square(int n)
    {
        int i, j;

        for (i = 1; i <= n; i++)
        {
            for (j = 1; j <= n; j++)
            {
                if (i == 1 || i == n ||
                    j == 1 || j == n)           
                    System.out.print("*");           
                else          
                    System.out.print(" ");           
            }
            System.out.println();
        }

    }

    // Driver code for above function
    public static void main(String args[])
    {
        int rows = 8;
        print_square(rows);
    }
}

/*This code is contributed by Nikita Tiwari.*/
```

## 蟒蛇 3

```cpp
# Python 3 code for hollow squares

# Function to print hollow square
def print_square(n) :

    for i in range(1, n+1) :
        for j in range(1, n+1) :
            if (i == 1 or i == n or
                j == 1 or j == n) :           
                print("*", end = "")           
            else :
                print(" ", end = "")           

        print()

# Driver code for above function
rows = 8
print_square(rows)

# This code is contributed by Nikita Tiwari.
```

<gfg-tab role="tab" slot="tab" id="gfg-tab-4">c#】</gfg-tab>T3

```cpp
 <?php
// PHP code for hollow squares

// Function to prhollow square
function print_square($n)
{
    $i;
    $j;
    for ($i = 1; $i <= $n; $i++)
    {
        for ($j = 1; $j <= $n; $j++)
        {
            if ($i == 1 || $i == $n || 
                $j == 1 || $j == $n)     
                print ("*");         
            else    
                print (" ");         
        }
        echo "\n";
    }

}

    // Driver Code
    $rows = 8;
    print_square($rows);

// This code is contributed by Anuj_67
?> 
```

T4

## C++

```cpp
// C++ program to print hollow square star
// pattern with diagonal
#include <bits/stdc++.h>
using namespace std;

// Function to print hollow square with
// primary and secondary diagonal
void print_squaredi(int n)
{
    int i, j;
    for (i = 1; i <= n; i++)
    {
        for (j = 1; j <= n; j++)
        {
            if (i == 1 || i == n || j == 1 ||
                j == n || i == j || j == (n - i + 1))        
                cout << "*";        
            else       
                cout << " ";        
        }
        cout << "\n";
    }
}

// Driver code
int main()
{
    int rows = 8;
    print_squaredi(rows);
    return 0;
}

// This code is contributed by SHUBHAMSINGH10
```

## C

```cpp
// C program to print hollow square star
// pattern with diagonal
#include <stdio.h>

// Function to print hollow square with
// primary and secondary diagonal
void print_squaredi(int n)
{
    int i, j;
    for (i = 1; i <= n; i++)
    {
        for (j = 1; j <= n; j++)
        {
            if (i==1 || i==n || j==1 ||
                j==n || i==j || j==(n - i + 1))           
                printf("*");           
            else           
                printf(" ");           
        }
        printf("\n");
    }

}
// Driver code for above function
int main()
{
    int rows = 8;
    print_squaredi(rows);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// JAVA program to print hollow square
// star pattern with diagonal
import java.io.*;

class GFG {

    // Function to print hollow square with
    // primary and secondary diagonal
    static void print_squaredi(int n)
    {
        int i, j;
        for (i = 1; i <= n; i++)
        {
            for (j = 1; j <= n; j++)
            {
                if (i == 1 || i == n || j == 1 ||
                j == n || i == j || j == (n - i + 1))           
                    System.out.print("*");           
                else          
                    System.out.print(" ");           
            }
            System.out.println();
        }

    }

    // Driver code for above function
    public static void main(String args[])
    {
        int rows = 8;
        print_squaredi(rows);
    }
}

/*This code is contributed by Nikita Tiwari.*/
```

## 蟒蛇 3

```cpp
# Python 3 program to print hollow
# square star pattern with diagonal

# Function to print hollow square with
# primary and secondary diagonal
def print_squaredi(n) :
    for i in range(1, n+1) :
        for j in range(1, n+1) :
            if (i==1 or i==n or j==1 or j==n
                or i==j or j==(n - i + 1)) :
                print("*", end = "")           
            else :
                print(" ", end = "")           

        print()

# Driver code for above function
rows = 8
print_squaredi(rows)

# This code is contributed by Nikita Tiwari.
```

## C#

```cpp
// C# program to print hollow square
// star pattern with diagonal
using System;

class GFG {

    // Function to print hollow square with
    // primary and secondary diagonal
    static void print_squaredi(int n)
    {
        int i, j;
        for (i = 1; i <= n; i++)
        {
            for (j = 1; j <= n; j++)
            {
                if (i == 1 || i == n ||
                    j == 1 || j == n ||
                    i == j || j == (n - i + 1))        
                    Console.Write("*");        
                else       
                Console.Write(" ");        
            }
            Console.WriteLine();
        }

    }

    // Driver code
    public static void Main()
    {
        int rows = 8;
        print_squaredi(rows);
    }
}

// This code is contributed by Nitin Mittal.
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to print hollow square
// star pattern with diagonal

// Function to print hollow square with
// primary and secondary diagonal
function print_squaredi($n)
{
    $i;
    $j;
    for($i = 1; $i <= $n; $i++)
    {
        for ($j = 1; $j <= $n; $j++)
        {
            if($i == 1 or $i == $n or $j == 1 ||
               $j == $n or $i == $j or $j == ($n -
                                          $i + 1))    
                printf("*");        
            else   
                echo " ";    
        }
        echo "\n";
    }

}

    // Driver Code
    $rows = 8;
    print_squaredi($rows);

// This code is contributed by anuj_67.
?>
```

输出:

```cpp
********
**    **
* *  * *
*  **  *
*  **  *
* *  * *
**    **
********
```