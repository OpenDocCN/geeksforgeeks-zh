# 打印数字图案的程序

> 原文:[https://www . geesforgeks . org/c-程序转打印数字模式/](https://www.geeksforgeeks.org/c-program-to-print-a-pattern-of-numbers/)

基于模式的程序的思想是理解 for 循环的嵌套概念，以及如何和在哪里放置字母/数字/星星以形成所需的模式。
写入程序，以下列方式打印数字模式，用于循环

```cpp
    1
   232
  34543
 4567654
567898765
```

在几乎所有类型的模式程序中，您必须注意两件事:

1.  行数
2.  模式是每行增加还是减少？

**实施**T2】

## C++

```cpp
// C++ program to illustrate the above
// given pattern of numbers.
#include<bits/stdc++.h>
using namespace std;

int main()
{
    int n = 5, i, j, num = 1, gap;
    gap = n - 1;

    for ( j = 1 ; j <= n ; j++ )
    {
        num = j;
        for ( i = 1 ; i <= gap ; i++ )
            cout << " ";

        gap --;
        for ( i = 1 ; i <= j ; i++ )
        {
            cout << num;
            num++ ;
        }
        num--;
        num--;
        for ( i = 1 ; i < j ; i++)
        {
            cout << num;
            num--;
        }
        cout << "\n";
    }
    return 0;
}

//This code is contributed by Shivi_Aggarwal
```

## C

```cpp
// C program to illustrate the above
// given pattern of numbers.
#include<stdio.h>

int main()
{
      int n = 5, i, j, num = 1, gap;

      gap = n - 1;

      for ( j = 1 ; j <= n ; j++ )
      {
          num = j;

          for ( i = 1 ; i <= gap ; i++ )
              printf(" ");

          gap --;

          for ( i = 1 ; i <= j ; i++ )
          {
              printf("%d", num);
              num++ ;
          }
          num--;
          num--;
          for ( i = 1 ; i < j ; i++)
          {
              printf("%d", num);
              num--;
          }
          printf("\n");

      }

      return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java Program to illustrate the
// above given pattern of numbers
import java.io.*;

class GFG {

    public static void main(String args[])
    {

        int n = 5, i, j, num = 1, gap;

        gap = n - 1;

        for ( j = 1 ; j <= n ; j++ )
        {
        num = j;

        for ( i = 1 ; i <= gap ; i++ )
            System.out.print(" ");

        gap --;

        for ( i = 1 ; i <= j ; i++ )
        {
            System.out.print(num);
            num++ ;
        }
        num--;
        num--;
        for ( i = 1 ; i < j ; i++)
        {
            System.out.print(num);
            num--;
        }
        System.out.println();
        }
    }
}

// This code is contributed
// by Nikita tiwari.
```

## 蟒蛇 3

```cpp
# Python Program to illustrate the
# above given pattern of numbers.

n = 5
num = 1
gap = n - 1
for j in range(1, n + 1) :
    num = j
    for i in range(1, gap + 1) :
        print(" ", end="")
    gap = gap - 1

    for i in range(1, j + 1) :
        print(num, end="")
        num = num + 1

    num = num - 2
    for i in range(1, j) :
        print(num, end="")
        num = num - 1

    print()

# This code is contributed
# by Nikita tiwari.
```

## C#

```cpp
// C# Program to illustrate the
// above given pattern of numbers
using System;

class GFG {

    public static void Main()
    {

        int n = 5, i, j, num = 1, gap;

        gap = n - 1;

        for (j = 1; j <= n; j++) {
            num = j;

            for (i = 1; i <= gap; i++)
                Console.Write(" ");

            gap--;

            for (i = 1; i <= j; i++) {
                Console.Write(num);
                num++ ;
            }
            num--;
            num--;
            for (i = 1; i < j; i++) {
                Console.Write(num);
                num--;
            }
            Console.WriteLine();
        }
    }
}

// This code is contributed
// by vt_m.
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
//php program to illustrate the above
// given pattern of numbers.

$n = 5;
$num = 1;
$gap = $n - 1;

for ($j = 1; $j <= $n; $j++)
{
    $num = $j;

    for ($i = 1; $i <= $gap; $i++)
        printf(" ");

    $gap --;

    for ($i = 1; $i <= $j; $i++)
    {
        printf($num);
        $num++ ;
    }
    $num--;
    $num--;
    for ($i = 1; $i < $j; $i++)
    {
        printf($num);
        $num--;
    }
    printf("\n");

}

// This code is contributed by mits
?>
```

## java 描述语言

```cpp
<script>
      // JavaScript program to illustrate the above
      // given pattern of numbers.
      var n = 5,
        i,
        j,
        num = 1,
        gap;
      gap = n - 1;

      for (j = 1; j <= n; j++) {
        num = j;
        for (i = 1; i <= gap; i++) document.write("  ");

        gap--;
        for (i = 1; i <= j; i++) {
          document.write(num);
          num++ ;
        }
        num--;
        num--;
        for (i = 1; i < j; i++) {
          document.write(num);
          num--;
        }
        document.write("<br>");
      }

      // This code is contributed by rdtank.
    </script>
```

**输出:**

```cpp
    1
   232
  34543
 4567654
567898765
```

[金字塔模式的程序](https://www.geeksforgeeks.org/program-to-print-pyramid-pattern/)
如果你发现任何不正确的地方，请写评论，或者你想分享更多关于上面讨论的话题的信息