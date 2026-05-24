# 程序打印空心金字塔和菱形图案

> 原文:[https://www . geesforgeks . org/program-print-hollow-金字塔-diamond-pattern/](https://www.geeksforgeeks.org/program-print-hollow-pyramid-diamond-pattern/)

**先决条件:** [循环](https://www.geeksforgeeks.org/c-language-2-gq/loops-control-structure-gq/)[If Else 语句](https://www.geeksforgeeks.org/decision-making-c-c-else-nested-else/)
**1。空心金字塔/三角形图案**
图案与金字塔图案相似。唯一的区别是，我们将用空格字符替换所有内部的' # '字符，并且我们将在最后一行中使用 2*N-1 (N =模式中的行数)' # '字符。
**举例:**

```cpp
Input rows: 6
Output:
     #
    # #
   #   #
  #     #
 #       #
#         #
###########    
```

## C++

```cpp
// CPP program to print a hollow pyramid pattern
#include <iostream>
using namespace std;
void printPattern(int);
int main()
{
    int n = 6;

    printPattern(n);
}
void printPattern(int n)
{
    int i, j, k = 0;
    for (i = 1; i <= n; i++) // row=6
    {
        // Print spaces
        for (j = i; j < n; j++) {
            cout << " ";
        }
        // Print #
        while (k != (2 * i - 1)) {
            if (k == 0 || k == 2 * i - 2)
                cout << "#";
            else
                cout << " ";
            k++ ;
            ;
        }
        k = 0;
        cout << endl; // print next row
    }
    // print last row
    for (i = 0; i < 2 * n - 1; i++) {
        cout << "#";
    }
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// JAVA program to print a hollow
// pyramid pattern
class GFG{

    public static void main(String args[])
    {
        int n = 6;

        printPattern(n);
    }

    static void printPattern(int n)
    {
        int i, j, k = 0;
        for (i = 1; i <= n; i++) // row=6
        {
            // Print spaces
            for (j = i; j < n; j++) {
                System.out.print(" ");
            }
            // Print #
            while (k != (2 * i - 1)) {
                if (k == 0 || k == 2 * i - 2)
                    System.out.print("#");
                else
                    System.out.print(" ");
                k++ ;
                ;
            }
            k = 0;

            // print next row
            System.out.println();
        }
        // print last row
        for (i = 0; i < 2 * n - 1; i++) {
            System.out.print("#");
        }
    }
}

/*This code is contributed by Nikita Tiwari.*/
```

## 计算机编程语言

```cpp
# Python program to print a hollow
# pyramid pattern

def printPattern( n) :
    k = 0
    for i in range(1,n+1) : #row 6

        # Print spaces
        for j in range(i,n) :
            print(' ', end='')

        # Print #
        while (k != (2 * i - 1)) :
            if (k == 0 or k == 2 * i - 2) :
                print('#', end='')
            else :
                print(' ', end ='')
            k = k + 1
        k = 0;
        print ("") # print next row

    # print last row
    for i in range(0, 2 * n -1) :
        print ('#', end = '')

# Driver code
n = 6
printPattern(n)

# This code is contributed by Nikita Tiwari.
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// php program to print a
// hollow pyramid pattern

function printPattern($n)
{
    $k = 0;

    // row=6
    for ($i = 1; $i <= $n; $i++)
    {

        // Print spaces
        for ($j = $i; $j < $n; $j++)
        {
            echo " ";
        }

        // Print #
        while ($k != (2 * $i - 1))
        {
            if ($k == 0 || $k == 2 *
                             $i - 2)
                echo "#";
            else
                echo " ";
            $k++ ;
        }
        $k = 0;

        // print next row
        echo "\n";
    }

    // print last row
    for ($i = 0; $i < 2 * $n - 1; $i++)
    {
        echo "#";
    }
}

//Driver Code
$n = 6;
printPattern($n);

// This code is contributed by mits
?>
```

## java 描述语言

```cpp
<script>
      // JavaScript program to print a hollow pyramid pattern
      var n = 6;
      printPattern(n);
      function printPattern(n)
      {
        var i, j, k = 0;
        for (i = 1; i <= n; i++)// row=6
        {
          // Print spaces
          for (j = i; j < n; j++)
          {
            document.write("  ");
          }

          // Print #
          while (k != 2 * i - 1)
          {
            if (k == 0 || k == 2 * i - 2)
                document.write("#");
            else
                document.write("  ");
            k++ ;
          }
          k = 0;
          document.write("<br>"); // print next row
        }

        // print last row
        for (i = 0; i < 2 * n - 1; i++)
        {
          document.write("#");
        }
      }

      // This code is contributed by rdtank.
    </script>
```

输出:

```cpp

     #
    # #
   #   #
  #     #
 #       #
#         #
 #         #
  #       #
   #     #
    #   #
     # #
      #
```

本文由[**Shivani ghshityal**](https://auth.geeksforgeeks.org/profile.php?user=Shivani Ghughtyal)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。