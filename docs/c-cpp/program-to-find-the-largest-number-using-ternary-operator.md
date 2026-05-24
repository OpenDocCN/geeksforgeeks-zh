# 用三进制运算符求最大数的程序

> 原文:[https://www . geesforgeks . org/program-to-find-最大数-使用-三元运算符/](https://www.geeksforgeeks.org/program-to-find-the-largest-number-using-ternary-operator/)

任务是编写一个程序，使用[三进制运算符](https://www.geeksforgeeks.org/cc-ternary-operator-some-interesting-observations/)在:

*   Two numbers.
*   Three numbers
*   Four numbers

中找出最大的数字

**示例** :

```cpp
Input : 10, 20 
Output : 
Largest number between two numbers (10, 20) is: 20

Input : 25 75 55 15
Output : 
Largest number among four numbers (25, 75, 55, 15) is: 75
```

一个**三元运算符**有以下形式，

```cpp
exp1 ? exp2 : exp3
```

表达式 ***exp1*** 将始终被求值。 ***exp2*** 和 ***exp3*** 的执行取决于 ***exp1*** 的结果。如果 *exp1* 的结果为非零，则 *exp2* 将被评估，否则 *exp3* 将被评估。

*   使用[三进制运算符](https://www.geeksforgeeks.org/cc-ternary-operator-some-interesting-observations/)在**两个数字**中寻找最大数字的程序。

## C++

```cpp
// C++ program to find largest among
// two numbers using ternary operator
#include <iostream>
using namespace std;

int main()
{

    // Variable declaration
    int n1 = 5, n2 = 10, max;

    // Largest among n1 and n2
    max = (n1 > n2) ? n1 : n2;

    // Print the largest number
    cout << "Largest number between "
         << n1 << " and " << n2
         << " is " << max << ".";

    return 0;
}

// This code is contributed by khushboogoyal499
```

## C

```cpp
// C program to find largest among two
// numbers using ternary operator

#include <stdio.h>

int main()
{
    // variable declaration
    int n1 = 5, n2 = 10, max;

    // Largest among n1 and n2
    max = (n1 > n2) ? n1 : n2;

    // Print the largest number
    printf("Largest number between %d and %d is %d. ",
                                         n1, n2, max);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find largest
// among two numbers using
// ternary operator
class GFG
{
public static void main(String args[])
{
    // variable declaration
    int n1 = 5, n2 = 10, max;

    // Largest among n1 and n2
    max = (n1 > n2) ? n1 : n2;

    // Print the largest number
    System.out.println("Largest number between " + n1 +
                  " and " + n2 + " is " + max + ". " );
}
}

// This code is contributed by Arnab Kundu
```

## 蟒蛇 3

```cpp
# Python3 program to find largest
# between two numbers using
# Ternary Operator.

# As python doesn't have ternary operator,
# we use conditional expression,
# form of conditional expression:
# exp1 if condition else exp2
# if condition is true then exp1
# is evaluated otherwise exp2
# max is library function to find
# the maximum number, so can't use
# max as variable
n1 = 5
n2 = 10

mx = n1 if n1 > n2 else n2

# we also can use
# mx=(n1>n2) and n1 or n2

# str() function is used to
# convert integer to string,
# it is required as we are
# concatenating integers with string
print("Largest number between " + str(n1) +
                        " and " + str(n2) +
                        " is " + str(mx))

# This code is contributed by Santanu
```

## C#

```cpp
// C# program to find largest
// among two numbers using
// ternary operator using System;
using System;

class GFG
{
public static void Main()
{
    // variable declaration
    int n1 = 5, n2 = 10, max;

    // Largest among n1 and n2
    max = (n1 > n2) ? n1 : n2;

    // Print the largest number
    Console.WriteLine("Largest number between " +
                     n1 + " and " + n2 + " is " +
                                    max + ". " );
}
}

// This code is contributed
// by Subhadeep
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to find largest
// among two numbers using
// ternary operator

// variable declaration
$n1 = 5; $n2 = 10;

// Largest among n1 and n2
$max = ($n1 > $n2) ? $n1 : $n2;

// Print the largest number
echo "Largest number between " .
     $n1\. " and " .$n2 ." is " . $max;

// This code is contributed
// by Akanksha Rai(Abby_akku)
```

## java 描述语言

```cpp
<script>

// Javascript program to find largest among
// two numbers using ternary operator

// Variable declaration
var n1 = 5, n2 = 10, max;

// Largest among n1 and n2
max = (n1 > n2) ? n1 : n2;

// Print the largest number
document.write("Largest number between "
    + n1 + " and " + n2
    + " is " + max + ".");

</script>
```

**Output:** 

```cpp
Largest number between 5 and 10 is 10.
```

*   使用[三进制运算符](https://www.geeksforgeeks.org/cc-ternary-operator-some-interesting-observations/)在**三个数字**中寻找最大数字的程序。

## C++

```cpp
// C++ program to find largest among three
// numbers using ternary operator
#include <iostream>
using namespace std;

int main()
{

    // Variable declaration
    int n1 = 5, n2 = 10, n3 = 15, max;

    // Largest among n1, n2 and n3
    max = (n1 > n2) ?
          (n1 > n3 ? n1 : n3) :
          (n2 > n3 ? n2 : n3);

    // Print the largest number
    cout << "Largest number among "
         << n1 << ", " << n2 << " and "
         << n3 << " is " << max << "." ;

    return 0;
}

// This code is contributed by khushboogoyal499
```

## C

```cpp
// C program to find largest among three
// numbers using ternary operator

#include <stdio.h>

int main()
{
    // variable declaration
    int n1 = 5, n2 = 10, n3 = 15, max;

    // Largest among n1, n2 and n3
    max = (n1 > n2) ? (n1 > n3 ? n1 : n3) : (n2 > n3 ? n2 : n3);

    // Print the largest number
    printf("Largest number among %d, %d and %d is %d.",
                                         n1, n2, n3, max);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find largest
// among three numbers using
// ternary operator
class GFG
{
public static void main(String args[])
{
    // variable declaration
    int n1 = 5, n2 = 10, n3 = 15, max;

    // Largest among n1, n2 and n3
    max = (n1 > n2) ?
          (n1 > n3 ? n1 : n3) :
          (n2 > n3 ? n2 : n3);

    // Print the largest number
    System.out.println("Largest number among " + n1 +
                             ", " + n2 + " and " + n3 +
                                 " is " + max + ". " );
}
}

// This code is contributed
// by Arnab Kundu
```

## 蟒蛇 3

```cpp
# Python3 program to find largest
# among three numbers using
# ternary operator

# As python doesn't have ternary
# operator, we use conditional
# expression, in form of
# conditional expression:
# Here, mx is a variable
n1 = 5
n2 = 10
n3 = 15

mx = (n1 if (n1 > n2 and n1 > n3) else
     (n2 if (n2 > n1 and n2 > n3) else n3))

# We also can use
# mx=(n1>n2) and n1 or n2

# str() function is used to
# convert integer to string,
# it is required as we are
# concatenating integers with string
print("Largest number among " + str(n1) +
                        " , " + str(n2) +
                      " and " + str(n3) +
                       " is " + str(mx))

# This code is contributed by Santanu
```

## C#

```cpp
// C# program to find largest
// number among three numbers
// using ternary operator
using System;

class GFG
{
public static void Main()
{
    // variable declaration
    int n1 = 5, n2 = 10, n3 = 15, max;

    // Largest among n1 and n2
    max = (n1 > n2 && n1 > n2) ?
                n1 : (n2 > n3) ? n2 : n3;

    // Print the largest number
    Console.WriteLine("Largest number among " +
                     n1 + ", " + n2 + " and " +
                            n3 + " is " + max);
}
}

// This code is contributed by Santanu
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to find largest among three
// numbers using ternary operator

// variable declaration
$n1 = 5; $n2 = 10; $n3 = 15;

// Largest among n1, n2 and n3
$max = ($n1 > $n2) ? ($n1 > $n3 ? $n1 : $n3) :
                     ($n2 > $n3 ? $n2 : $n3);

// Print the largest number
echo "Largest number among ". $n1 . ", ". $n2 .
                   " and " . $n3\. " is " .$max;
?>
```

## java 描述语言

```cpp
<script>

// Javascript program to find largest among three
// numbers using ternary operator

// Variable declaration
var n1 = 5, n2 = 10, n3 = 15, max;

// Largest among n1, n2 and n3
max = (n1 > n2) ?
      (n1 > n3 ? n1 : n3) :
      (n2 > n3 ? n2 : n3);

// Print the largest number
document.write( "Largest number among "
     + n1 + ", " + n2 + " and "
     + n3 + " is " + max + "." );

</script>
```

**Output:** 

```cpp
Largest number among 5, 10 and 15 is 15.
```

*   使用[三进制运算符](https://www.geeksforgeeks.org/cc-ternary-operator-some-interesting-observations/)在**四个数字**中寻找最大数字的程序。

## C++

```cpp
// C++ program to find largest
// number among four numbers
// using ternary operator
#include <iostream>
using namespace std;

int main()
{

    // Variable declaration
    int n1 = 5, n2 = 10, n3 = 15, n4 = 20, max;

    // Largest among n1, n2, n3 and n4
    max = (n1 > n2 && n1 > n3 && n1 > n4) ?
               n1 : ((n2 > n3 && n2 > n4) ?
               n2 : (n3 > n4 ? n3 : n4));

    // Print the largest number
    cout << "Largest number among "
         << n1 << ", " << n2 << ", "
         << n3 << " and " << n4
         << " is " << max << "." ;

    return 0;
}

// This code is contributed by khushboogoyal499
```

## C

```cpp
// C program to find largest among four
// numbers using ternary operator

#include <stdio.h>

int main()
{
    // variable declaration
    int n1 = 5, n2 = 10, n3 = 15, n4 = 20, max;

    // Largest among n1, n2, n3 and n4
    max = (n1 > n2 && n1 > n3 && n1 > n4) ?
                                   n1 :
                                     ((n2 > n3 && n2 > n4) ?
                                                         n2 :
                                                          (n3 > n4 ? n3 : n4));

    // Print the largest number
    printf("Largest number among %d, %d, %d and %d is %d.",
                                         n1, n2, n3, n4, max);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find largest
// among four numbers using
// ternary operator
class GFG
{

public static void main(String args[])
{
    // variable declaration
    int n1 = 5, n2 = 10,
        n3 = 15, n4 = 20, max;

    // Largest among n1, n2, n3 and n4
    max = (n1 > n2 && n1 > n3 && n1 > n4) ?
               n1 : ((n2 > n3 && n2 > n4) ?
               n2 : (n3 > n4 ? n3 : n4));

    // Print the largest number
    System.out.println("Largest number among " +
                      n1 + ", " + n2 + ", "+ n3 +
             " and " + n4 + " is " + max + ". " );
}
}

// This code is contributed
// by Arnab Kundu
```

## 蟒蛇 3

```cpp
# Python3 program to find largest
# among four numbers using
# Ternary Operator.

# As python doesn't have ternary operator,
# we use conditional expression,
# form of conditional expression:
# exp1 if condition else exp2
# if condition is true then exp1
# is evaluated otherwise exp2
# max is library function to find
# the maximum number, so can't use
# max as variable
n1 = 5
n2 = 10
n3 = 15
n4 = 20

mx = (n1 if (n1 > n2 and n1 > n2 and n1 > n4)
         else (n2 if (n2 > n3 and n3 > n4)
         else (n3 if n3 > n4 else n4)))

# str() function is used to convert
# integer to string, it is required
# as we are concatenating integers
# with string
print("Largest number among " + str(n1) + ", " +
            str(n2) + ", " + str(n3) + " and " +
            str(n4) + " is " + str(mx))

# This code is contributed by Santanu
```

## C#

```cpp
// C# program to find largest
// number among four numbers
// using ternary operator
using System;

class GFG
{
public static void Main()
{
    // variable declaration
    int n1 = 5, n2 = 10,
        n3 = 15, n4 = 20, max;

    // Largest among n1 and n2
    max = (n1 > n2 && n1 > n2 && n1 > n2) ?
                n1 : (n2 > n3 && n2 > n4) ?
                           n2 : (n3 > n4) ? n3 : n4;

    // Print the largest number
    Console.WriteLine("Largest number among " +
                        n1 + ", " + n2 + ", " +
                            n3 + " and " + n4 +
                                 " is " + max);
}
}

// This code is contributed by Santanu
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to find largest among four
// numbers using ternary operator

// variable declaration
$n1 = 5; $n2 = 10; $n3 = 15; $n4 = 20;

// Largest among n1, n2, n3 and n4
$max = ($n1 > $n2 && $n1 > $n3 && $n1 > $n4) ?
             $n1 : (($n2 > $n3 && $n2 > $n4) ?
             $n2 : ($n3 > $n4 ? $n3 : $n4));

// Print the largest number
echo "Largest number among ". $n1\. ", ". $n2\. ", ".
                  $n3.  " and ". $n4\. " is " .$max;
?>
```

## java 描述语言

```cpp
<script>
// javascript program to find largest
// among four numbers using
// ternary operator    
        // variable declaration
        var n1 = 5, n2 = 10, n3 = 15, n4 = 20, max;

        // Largest among n1, n2, n3 and n4
        max = (n1 > n2 && n1 > n3 && n1 > n4)
        ? n1 : ((n2 > n3 && n2 > n4)
        ? n2 : (n3 > n4 ? n3 : n4));

        // Print the largest number
        document.write("Largest number among " + n1
        + ", " + n2 + ", " + n3 + " and "
        + n4 + " is " + max + ". ");

// This code is contributed by todaysgaurav
</script>
```

**Output:** 

```cpp
Largest number among 5, 10, 15 and 20 is 20.
```