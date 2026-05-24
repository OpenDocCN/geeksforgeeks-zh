# 程序打印窗口图案

> 原文：[https://www.geeksforgeeks.org/program-to-print-window-pattern/](https://www.geeksforgeeks.org/program-to-print-window-pattern/)

打印其中有一个空心方块和加号的图案。模式将根据 `n`，即示例中给出的行数。

**示例：**

```py
Input : 6
Output : * * * * * *
         *   * *   * 
         * * * * * * 
         * * * * * * 
         *   * *   * 
         * * * * * *

Input : 7
Output : * * * * * * * 
         *     *     * 
         *     *     * 
         * * * * * * * 
         *     *     * 
         *     *     * 
         * * * * * * *
```

## 方法

*   我们将启动一个直到 `n` 的 `for` 循环，并且在这个循环内部还会有一个直到 `n` 的 `for` 循环。
*   在这个简单的例子中，我们必须检查行是否是第一行或最后一行，或者列是否是第一列或最后一列，然后打印 `"*"`。
*   现在我们要检查中间的行和列。
*   所以当 `n` 是奇数时，我们将有一个中间行和中间列。如果行或列在中间，我们将打印 `"*"`。
*   如果 `n` 是偶数，那么如果行或列等于 `n/2` 和 `(n/2)+1` 这些值，我们将打印 `"*"`。
*   其他所有地方我们都必须打印 `""`（空格）。

下面是实现。

## C++ 14

```cpp
// C++ program to print the pattern 
// hollow square with plus inside it
// window pattern
#include <bits/stdc++.h>
using namespace std;

// Function to print pattern n means 
// number of rows which we want
void window_pattern (int n)
{
    int c, d;

    // If n is odd then we will have
    // only one middle element
    if (n % 2 != 0)
    {
        c = (n / 2) + 1;
        d = 0;
    }

    // If n is even then we will have two
    // values
    else
    {
        c = (n / 2) + 1;
        d = n / 2 ;
    }

    for(int i = 1; i <= n; i++)
    {
        for(int j = 1; j <= n; j++)
        {

            // If i,j equals to corner row or
            // column then "*"
            if (i == 1 || j == 1 ||
                i == n || j == n)
                cout << "* ";

            else
            {

                // If i,j equals to the middle 
                // row or column then  "*"
                if (i == c || j == c)
                    cout << "* ";

                else if (i == d || j == d)
                    cout << "* ";

                else
                    cout << "  ";
            }
        }
        cout << '\n';
    }
}

// Driver Code
int main()
{
    int n = 7;

    window_pattern(n);
    return 0;   
}

// This code is contributed by himanshu77
```

## Java

```java
// Java program to print the pattern 
// hollow square with plus inside it
// window pattern
class GFG
{

  // Function to print pattern n means 
  // number of rows which we want
  static void window_pattern (int n)
  {
    int c, d;

    // If n is odd then we will have
    // only one middle element
    if (n % 2 != 0)
    {
      c = (n / 2) + 1;
      d = 0;
    }

    // If n is even then we will have
    // two values
    else
    {
      c = (n / 2) + 1;
      d = n / 2 ;
    } 
    for(int i = 1; i <= n; i++)
    {
      for(int j = 1; j <= n; j++)
      {

        // If i,j equals to corner row
        // or column then "*"
        if (i == 1 || j == 1 ||
            i == n || j == n)
          System.out.print("* ");          
        else
        {

          // If i,j equals to the middle 
          // row or column then  "*"
          if (i == c || j == c)
            System.out.print("* ");
          else if (i == d || j == d)
            System.out.print("* ");
          else
            System.out.print("  ");
        }
      }
      System.out.println();
    }
  }

  // Driver code
  public static void main(String[] args)
  {
    int n = 7;
    window_pattern(n);
  }
}

// This code is contributed by divyeshrabadiya07
```

## Python 3

```python
# Python3 program to print the pattern
# hollow square with plus inside it
# window pattern

# function to print pattern n means
# number of rows which we want
def window_pattern(n):

    # if n is odd then we will have
    # only one middle element
    if n % 2 != 0:
        c = ( n // 2 ) + 1
        d = 0

    # if n is even then we will have two
    # values
    else:
        c = ( n // 2 ) + 1
        d = ( n // 2 )

    for i in range( 1 , n + 1 ):
        for j in range( 1 , n + 1 ):

            # if i,j equals to corner row or
            # column then "*"
            if i == 1 or j == 1 or i == n or j == n:
                print("*",end=" ")

            else:

                # if i,j equals to the middle row
                # or column then  "*"
                if i == c or j == c:
                    print("*",end=" ")

                elif i == d or j == d:
                    print("*",end=" ")

                else:
                    print(" ",end=" ")

        print()

# Driver Code
if __name__ == "__main__":
    n = 7
    window_pattern(n)
```

## C#

```csharp
// C# program to print the pattern 
// hollow square with plus inside it
// window pattern
using System;

class GFG{

// Function to print pattern n means 
// number of rows which we want
static void window_pattern (int n)
{
    int c, d;

    // If n is odd then we will have
    // only one middle element
    if (n % 2 != 0)
    {
        c = (n / 2) + 1;
        d = 0;
    }

    // If n is even then we will have
    // two values
    else
    {
        c = (n / 2) + 1;
        d = n / 2 ;
    }

    for(int i = 1; i <= n; i++)
    {
        for(int j = 1; j <= n; j++)
        {

            // If i,j equals to corner row
            // or column then "*"
            if (i == 1 || j == 1 ||
                i == n || j == n)
                Console.Write("* ");

            else
            {

                // If i,j equals to the middle 
                // row or column then  "*"
                if (i == c || j == c)
                    Console.Write("* ");

                else if (i == d || j == d)
                    Console.Write("* ");

                else
                    Console.Write("  ");
            }
        }
        Console.WriteLine();
    }
}

// Driver code
static void Main()
{
    int n = 7;

    window_pattern(n);
}
}

// This code is contributed by divyesh072019
```

## JavaScript

```javascript
// JavaScript program to
// print the pattern
// hollow square with
// plus inside it
// window pattern

// Function to print pattern n means
// number of rows which we want
function window_pattern(n)
{
  var c, d;

  // If n is odd then we will have
  // only one middle element
  if (n % 2 != 0) {
    c = parseInt(n / 2 + 1);
    d = 0;
  }

  // If n is even then we will have two
  // values
  else {
    c = parseInt(n / 2 + 1);
    d = parseInt(n / 2);
  }

  for (var i = 1; i <= n; i++) {
    for (var j = 1; j <= n; j++) {
      // If i,j equals to corner row or
      // column then "*"
      if (i == 1 || j == 1 || i == n || j == n)
        document.write("* ");
      else {
        // If i,j equals to the middle
        // row or column then "*"
        if (i == c || j == c)
          document.write("* ");
        else if (i == d || j == d)
          document.write("* ");
        else
          document.write("   ");
      }
    }
    document.write("<br>");
  }
}

// Driver Code
var n = 7;

window_pattern(n);
```

**输出：**

```py
* * * * * * * 
*     *     * 
*     *     * 
* * * * * * * 
*     *     * 
*     *     * 
* * * * * * *
```

**时间复杂度：** O(n²)