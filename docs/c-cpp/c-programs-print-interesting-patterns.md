# 打印有趣图案的程序

> 原文:[https://www . geesforgeks . org/c-programs-print-interest-patterns/](https://www.geeksforgeeks.org/c-programs-print-interesting-patterns/)

打印以下图案的程序:

**示例:**

```cpp
Input : 5
Output: 
* * * * *  * * * * *
* * * *      * * * *
* * *          * * *
* *              * *
*                  *
*                  *
* *              * *
* * *          * * *
* * * *      * * * *
* * * * *  * * * * *
```

这个节目分为四个部分。

## C++

```cpp
// C++ program to print
// the given pattern
#include<iostream>
using namespace std;

void pattern(int n)
{
    int i, j;

    // This is upper half of pattern
    for(i = 1; i <= n; i++)
    {
        for(j = 1; j <= (2 * n); j++)
        {

            // Left part of pattern
            if (i > (n - j + 1))
                cout << " ";
            else
                cout << "*";

            // Right part of pattern
            if ((i + n) > j)
                cout << " ";
            else
                cout << "*";
        }
        cout << endl ;
    }

    // This is lower half of pattern
    for(i = 1; i <= n; i++)
    {
        for(j = 1; j <= (2 * n); j++)
        {

            // Right Part of pattern
            if (i < j)
                cout << " ";
            else
                cout << "*";

            // Left Part of pattern
            if (i <= ((2 * n) - j))
                cout << " ";
            else
                cout << "*";
        }
        cout << endl;
    }
}

// Driver Code
int main()
{
    pattern(7);

    return 0;
}

// This code is contributed by bunnyram19
```

## C

```cpp
// C program to print
// the given pattern

#include<stdio.h>
void pattern(int n)
{
    int i,j;

    // This is upper half of pattern
    for (i=1; i<=n; i++)
    {
        for (j=1; j<=(2*n); j++)
        {
            // Left part of pattern
            if (i>(n-j+1))
                printf(" ");
            else
                printf("*");

            // Right part of pattern
            if ((i+n)>j)
                printf(" ");
            else
                printf("*");
        }
        printf("\n");
    }

    // This is lower half of pattern
    for (i=1; i<=n; i++)
    {
        for (j=1; j<=(2*n); j++)
        {
            // Right Part of pattern
            if (i<j)
                printf(" ");
            else
                printf("*");

            // Left Part of pattern
            if (i<=((2*n)-j))
                printf(" ");
            else
                printf("*");
        }
        printf("\n");
    }
}

// Driver Code
int main()
{
    pattern(7);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to print
// the given pattern
import java.io.*;

class GFG {

    static void pattern(int n)
    {
        int i, j;

        // This is upper half of pattern
        for (i = 1; i <= n; i++) {
            for (j = 1; j <= (2 * n); j++) {

                // Left part of pattern
                if (i > (n - j + 1))
                    System.out.print(" ");
                else
                    System.out.print("*");

                // Right part of pattern
                if ((i + n) > j)
                    System.out.print(" ");
                else
                    System.out.print("*");
            }

            System.out.println("");
        }

        // This is lower half of pattern
        for (i = 1; i <= n; i++) {
            for (j = 1; j <= (2 * n); j++) {

                // Right Part of pattern
                if (i < j)
                    System.out.print(" ");
                else
                    System.out.print("*");

                // Left Part of pattern
                if (i <= ((2 * n) - j))
                    System.out.print(" ");
                else
                    System.out.print("*");
            }

            System.out.println("");
        }
    }

    // Driver Code
    public static void main(String[] args)
    {
        pattern(7);
    }
}

// This code is contributed by vt_m
```

## 蟒蛇 3

```cpp
# Python3 program to print
# the given pattern

def pattern(n):

    # This is upper half of pattern
    for i in range (1, n + 1):
        for j in range (1, 2 * n):

            # Left part of pattern
            if i > (n - j + 1):
                print("", end = ' ');
            else:
                print("*", end = '');

            # Right part of pattern
            if i + n - 1 > j:
                print("", end = ' ');
            else:
                print("*", end = '');
        print("");

    # This is lower half of pattern
    for i in range (1, n + 1):
        for j in range (1, 2 * n):
            #Left part of pattern
            if i < j:
                print("", end = ' ');
            else:
                print("*", end = '');

            # Right part of pattern
            if i < 2 * n - j:
                print("", end = ' ');
            else:
                print("*", end = '');
        print("");

# Driver Code
pattern(7);

# This code is contributed by mits
```

## C#

```cpp
// C# program to print
// the given pattern
using System;

class GFG
{
    static void pattern(int n)
    {
        int i, j;

        // This is upper
        // half of pattern
        for (i = 1; i <= n; i++)
        {
            for (j = 1; j <= (2 * n); j++)
            {

                // Left part of pattern
                if (i > (n - j + 1))
                    Console.Write(" ");
                else
                    Console.Write("*");

                // Right part of pattern
                if ((i + n) > j)
                    Console.Write(" ");
                else
                    Console.Write("*");
            }

            Console.WriteLine("");
        }

        // This is lower
        // half of pattern
        for (i = 1; i <= n; i++)
        {
            for (j = 1; j <= (2 * n); j++)
            {

                // Right Part of pattern
                if (i < j)
                    Console.Write(" ");
                else
                    Console.Write("*");

                // Left Part of pattern
                if (i <= ((2 * n) - j))
                    Console.Write(" ");
                else
                    Console.Write("*");
            }

            Console.WriteLine("");
        }
    }

    // Driver Code
    static public void Main ()
    {
        pattern(7);
    }
}

// This code is contributed by ajit
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to print
// the given pattern

function pattern($n)
{
    $i; $j;

    // This is upper half of pattern
    for ($i = 1; $i <= $n; $i++)
    {
        for ($j = 1; $j <= (2 * $n); $j++)
        {
            // Left part of pattern
            if ($i > ($n - $j + 1))
                echo " ";
            else
                echo "*";

            // Right part of pattern
            if (($i + $n) > $j)
                echo " ";
            else
                echo "*";
        }
        printf("\n");
    }

    // This is lower half of pattern
    for ($i = 1; $i <= $n; $i++)
    {
        for ($j = 1; $j <= (2 * $n); $j++)
        {
            // Right Part of pattern
            if ($i < $j)
                echo " ";
            else
                echo "*";

            // Left Part of pattern
            if ($i <= ((2 * $n) - $j))
                echo " ";
            else
                echo "*";
        }
        echo "\n";
    }
}

// Driver Code
pattern(7);

// This code is contributed by m_kit
?>
```

## java 描述语言

```cpp
<script>

      // JavaScript program to print
      // the given pattern

      function pattern(n) {
        var i, j;

        // This is upper half of pattern
        for (i = 1; i <= n; i++) {
          for (j = 1; j <= 2 * n; j++) {
            // Left part of pattern
            if (i > n - j + 1)
            document.write("  ");
            else
            document.write("*");

            // Right part of pattern
            if (i + n > j)
            document.write("  ");
            else
            document.write("*");
          }
          document.write("<br>");
        }

        // This is lower half of pattern
        for (i = 1; i <= n; i++) {
          for (j = 1; j <= 2 * n; j++) {
            // Right Part of pattern
            if (i < j)
            document.write("  ");
            else
            document.write("*");

            // Left Part of pattern
            if (i <= 2 * n - j)
            document.write("  ");
            else
            document.write("*");
          }
          document.write("<br>");
        }
      }

      // Driver Code
      pattern(7);

    </script>
```

**输出:**

```cpp
* * * * * * *  * * * * * * *
* * * * * *      * * * * * *
* * * * *          * * * * *
* * * *              * * * *
* * *                  * * *
* *                      * *
*                          *
*                          *
* *                      * *
* * *                  * * *
* * * *              * * * *
* * * * *          * * * * *
* * * * * *      * * * * * *
* * * * * * *  * * * * * * *
```

打印以下图案的程序:

**示例:**

```cpp
Input : 5
Output: 
*                  *
* *              * *
* * *          * * *
* * * *      * * * *
* * * * *  * * * * *
* * * * *  * * * * *
* * * *      * * * *
* * *          * * *
* *              * *
*                  *
```

这个节目分为四个部分。

## C++

```cpp
// C++ program to print the
// given pattern
#include <bits/stdc++.h>
using namespace std;

void pattern(int n)
{
    int i, j;

    // This is upper half of pattern
    for (i = 1; i <= n; i++)
    {
        for (j = 1; j <= (2 * n); j++)
        {
            // Left part of pattern
            if (i < j)
                cout << " ";
            else
                cout << "*";

            // Right part of pattern
            if (i <= ((2 * n) - j))
                cout << " ";
            else
                cout << "*";
        }
        cout << "\n";
    }

    // This is lower half of pattern
    for (i = 1; i <= n; i++)
    {
        for (j = 1; j <= (2 * n); j++)
        {
            // Left part of pattern
            if (i > (n - j + 1))
                cout <<" ";
            else
                cout <<"*";

            // Right part of pattern
            if ((i + n) > j)
                cout << " ";
            else
                cout << "*";
        }
        cout << "\n";
    }
}

// Driver Code
int main()
{
    pattern(7);
    return 0;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
// C program to print the
// given pattern

#include<stdio.h>
void pattern(int n)
{
    int i,j;

    // This is upper half of pattern
    for (i=1; i<=n; i++)
    {
        for (j=1; j<=(2*n); j++)
        {
            // Left part of pattern
            if (i<j)
                printf(" ");
            else
                printf("*");

            // Right part of pattern
            if (i<=((2*n)-j))
                printf(" ");
            else
                printf("*");
        }
        printf("\n");
    }

    // This is lower half of pattern
    for (i=1; i<=n; i++)
    {
        for (j=1;j<=(2*n);j++)
        {
            // Left part of pattern
            if (i>(n-j+1))
                printf(" ");
            else
                printf("*");

            // Right part of pattern
            if ((i+n)>j)
                printf(" ");
            else
                printf("*");
        }
        printf("\n");
    }
}

// Driver Code
int main()
{
    pattern(7);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to print the
// given pattern

import java.io.*;

class GFG {

    static void pattern(int n)
    {
        int i, j;

        // This is upper half of pattern
        for (i = 1; i <= n; i++) {
            for (j = 1; j <= (2 * n); j++) {

                // Left part of pattern
                if (i < j)
                    System.out.print(" ");
                else
                    System.out.print("*");

                // Right part of pattern
                if (i <= ((2 * n) - j))
                    System.out.print(" ");
                else
                    System.out.print("*");
            }

            System.out.println("");
        }

        // This is lower half of pattern
        for (i = 1; i <= n; i++) {
            for (j = 1; j <= (2 * n); j++) {

                // Left part of pattern
                if (i > (n - j + 1))
                    System.out.print(" ");
                else
                    System.out.print("*");

                // Right part of pattern
                if ((i + n) > j)
                    System.out.print(" ");
                else
                    System.out.print("*");
            }

            System.out.println("");
        }
    }

    // Driver Code
    public static void main(String[] args)
    {
        pattern(7);
    }
}

// This code is contributed by vt_m
```

## 蟒蛇 3

```cpp
# Python3 program to
# print the given pattern

def pattern(n):

    # This is upper
    # half of pattern
    for i in range(1, n + 1):
        for j in range(1, 2 * n + 1):

            # Left part of pattern
            if (i < j):
                print("", end = " ");
            else:
                print("*", end = "");

            # Right part of pattern
            if (i <= ((2 * n) - j)):
                print("", end = " ");
            else:
                print("*", end = "");
        print("");

    # This is lower
    # half of pattern
    for i in range(1, n + 1):
        for j in range(1, 2 * n + 1):

            # Left part of pattern
            if (i > (n - j + 1)):
                print("", end = " ");
            else:
                print("*", end = "");

            # Right part of pattern
            if ((i + n) > j):
                print("", end = " ");
            else:
                print("*", end = "");
        print("");

# Driver Code
pattern(7);

# This code is contributed
# by mits
```

## C#

```cpp
// C# program to print
// the given pattern
using System;

class GFG
{
    static void pattern(int n)
    {
        int i, j;

        // This is upper
        // half of pattern
        for (i = 1; i <= n; i++)
        {
            for (j = 1; j <= (2 * n); j++)
            {

                // Left part of pattern
                if (i < j)
                    Console.Write(" ");
                else
                    Console.Write("*");

                // Right part of pattern
                if (i <= ((2 * n) - j))
                    Console.Write(" ");
                else
                    Console.Write("*");
            }

            Console.WriteLine("");
        }

        // This is lower
        // half of pattern
        for (i = 1; i <= n; i++)
        {
            for (j = 1; j <= (2 * n); j++)
            {

                // Left part of pattern
                if (i > (n - j + 1))
                    Console.Write(" ");
                else
                    Console.Write("*");

                // Right part of pattern
                if ((i + n) > j)
                    Console.Write(" ");
                else
                    Console.Write("*");
            }

            Console.WriteLine("");
        }
    }

    // Driver Code
    static public void Main ()
    {
        pattern(7);
    }
}

// This code is contributed by ajit
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to print
// the given pattern
function pattern($n)
{
    $i; $j;

    // This is upper half
    // of pattern
    for ($i = 1; $i <= $n; $i++)
    {
        for ($j = 1; $j <= (2 * $n); $j++)
        {
            // Left part of pattern
            if ($i < $j)
                echo " ";
            else
                echo "*";

            // Right part of pattern
            if ($i <= ((2 * $n) - $j))
                echo " ";
            else
                echo "*";
        }
        echo "\n";
    }

    // This is lower half of pattern
    for ($i = 1; $i <= $n; $i++)
    {
        for ($j = 1;$j <= (2 * $n); $j++)
        {
            // Left part of pattern
            if ($i > ($n - $j + 1))
                echo " ";
            else
                echo "*";

            // Right part of pattern
            if (($i + $n) > $j)
                echo " ";
            else
                echo "*";
        }
    echo "\n";
    }
}

// Driver Code
pattern(7);

// This code is contributed by aj_36
?>
```

## java 描述语言

```cpp
<script>

// Javascript program to print the
// given pattern  
function pattern(n)
{
    var i, j;

    // This is upper half of pattern
    for(i = 1; i <= n; i++)
    {
        for(j = 1; j <= (2 * n); j++)
        {

            // Left part of pattern
            if (i < j)
                document.write("  ");
            else
                document.write("*");

            // Right part of pattern
            if (i <= ((2 * n) - j))
                document.write("  ");
            else
                document.write("*");
        }
        document.write('<br>');
    }

    // This is lower half of pattern
    for(i = 1; i <= n; i++)
    {
        for(j = 1; j <= (2 * n); j++)
        {

            // Left part of pattern
            if (i > (n - j + 1))
                document.write("  ");
            else
                document.write("*");

            // Right part of pattern
            if ((i + n) > j)
                document.write("  ");
            else
                document.write("*");
        }
        document.write('<br>');
    }
}

// Driver Code
pattern(7);

// This code is contributed by Princi Singh

</script>
```

**输出:**

```cpp
*                          *
* *                      * *
* * *                  * * *
* * * *              * * * *
* * * * *          * * * * *
* * * * * *      * * * * * *
* * * * * * *  * * * * * * *
* * * * * * *  * * * * * * *
* * * * * *      * * * * * *
* * * * *          * * * * *
* * * *              * * * *
* * *                  * * *
* *                      * *
*                          *
```

本文由[阿迪蒂亚·库马尔](https://www.linkedin.com/in/aditya-kumar-837315100/)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。