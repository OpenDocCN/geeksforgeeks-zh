# C 程序打印弗洛伊德三角形

> 原文:[https://www . geesforgeks . org/c-program-print-floyds-triangle/](https://www.geeksforgeeks.org/c-program-print-floyds-triangle/)

[弗洛伊德三角形](http://en.wikipedia.org/wiki/Floyd%27s_triangle)是第一自然数的三角形。

```cpp
1
2     3
4     5     6
7     8     9     10
11     12     13     14     15
```

下面的程序用 n 条线打印弗洛伊德的三角形。

## C++

```cpp
#include <bits/stdc++.h>
using namespace std;

void printFloydTriangle(int n)
{
    int i, j, val = 1;
    for (i = 1; i <= n; i++)
    {
        for (j = 1; j <= i; j++)
            cout << val++ << " ";
        cout << endl;
    }
}

// Driver Code
int main()
{
    printFloydTriangle(6);
    return 0;
}

// This is code is contributed
// by rathbhupendra
```

## C

```cpp
// Without using a temporary variable and with only one loop
#include<stdio.h>
void floyd(n){
    int i,j=1;
    for (i=1;i<=(n*(n+1))/2;i++){
        printf("%d ",i);
        if(i==(j*(j+1))/2){
            printf("\n");
            j++ ;
        }
    }
}

int main(){
    floyd(6);
}

//This code is contributed by Vishal B
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to print
// Floyd's triangle
class GFG
{
    static void printFloydTriangle(int n)
    {
        int i, j, val = 1;
        for (i = 1; i <= n; i++)
        {
            for (j = 1; j <= i; j++)
            {
                System.out.print(val + " ");
                val++ ;
            }
            System.out.println();

        }
    }

    // Driver Code
    public static void main(String[] args)
    {
        printFloydTriangle(6);
    }
}
```

## 蟒蛇 3

```cpp
# Python3 program to print
# Floyd's triangle
def loydTriangle(n):

    val = 1
    for i in range(1, n + 1):

        for j in range(1, i + 1):
            print(val, end = " ")
            val += 1

        print("")

loydTriangle(6)

# This code is contributed by
# Smitha Dinesh Semwal
```

## C#

```cpp
// C# program to print
// Floyd's triangle
using System;

class GFG
{
    static void printFloydTriangle(int n)
    {
        int i, j, val = 1;
        for (i = 1; i <= n; i++)
        {
            for (j = 1; j <= i; j++)
            {
                Console.Write(val + " ");
                val++ ;
            }
            Console.WriteLine();
        }
    }

    // Driver Code
    public static void Main()
    {
        printFloydTriangle(6);
    }
}
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP code to print Floyd's Triangle

// Function to display Floyd's Triangle
function FloydsTriangle($n)
{
    $val = 1;

    // loop for number of lines
    for($i = 1; $i <= $n; $i++)
    {
        // loop for number of elements
        // in each line
        for($j = 1; $j <= $i; $j++)
        {
            print($val." ");
            $val++ ;
        }
        print("\n");
    }
}

// Driver's Code
$n = 6;
FloydsTriangle($n);

// This code is contributed by akash7981
?>
```

## java 描述语言

```cpp
<script>
// Javascript implementation
function printFloydTriangle(n)
{
    var i, j, val = 1;
    for (i = 1; i <= n; i++)
    {
        for (j = 1; j <= i; j++)
            document.write(val++ + " ");
        document.write("<br>");
    }
}

// Driver Code
printFloydTriangle(6);

// This is code is contributed
// by shivani
</script>
```

**输出:**

```cpp
1
2 3
4 5 6
7 8 9 10
11 12 13 14 15
16 17 18 19 20 21
```

***时间复杂度:** O(n <sup>2</sup> )*

***辅助空间:**O(1)*T4】

https://www.youtube.com/watch?v=VOk9

-jsvpnc t0