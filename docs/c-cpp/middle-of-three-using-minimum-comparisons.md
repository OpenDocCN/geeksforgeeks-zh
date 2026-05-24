# 使用最小比较的三个中间值

> 原文:[https://www . geeksforgeeks . org/三个中间使用最小比较/](https://www.geeksforgeeks.org/middle-of-three-using-minimum-comparisons/)

给定三个不同的数字 a、b 和 c，找出中间有一个值的数字。
示例:

```cpp
Input : a = 20, b = 30, c = 40
Output : 30

Input : a = 12, n = 32, c = 11
Output : 12
```

**简单方法:**

## C++

```cpp
// CPP program to find  middle of three distinct
// numbers
#include <bits/stdc++.h>
using namespace std;

int middleOfThree(int a, int b, int c)
{
    // Checking for b
    if ((a < b && b < c) || (c < b && b < a))
       return b;

    // Checking for a
    else if ((b < a && a < c) || (c < a && a < b))
       return a;

    else
       return c;
}

// Driver Code
int main()
{
    int a = 20, b = 30, c = 40;
    cout << middleOfThree(a, b, c);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find middle of
// three distinct numbers
import java.util.*;

class Middle
{  
    // Function to find the middle of three number
    public static int middleOfThree(int a, int b,
                                          int c)
    {
        // Checking for b
        if ((a < b && b < c) || (c < b && b < a))
            return b;

        // Checking for a
        else if ((b < a && a < c) || (c < a && a < b))
        return a;

        else
        return c;
    }

    // driver code
    public static void main(String[] args)
    {
        int a = 20, b = 30, c = 40;
        System.out.println( middleOfThree(a, b, c) );
    }
}

// This code is contributed by rishabh_jain
```

## 蟒蛇 3

```cpp
# Python3 program to find middle
# of three distinct numbers

def middleOfThree(a, b, c):

    # Checking for b
    if ((a < b and b < c) or (c < b and b < a)) :
        return b;

    # Checking for a
    if ((b < a and a < c) or (c < a and a < b)) :
        return a;

    else :
        return c

# Driver Code
a = 20
b = 30
c = 40
print(middleOfThree(a, b, c))

# This code is contributed by rishabh_jain
```

## C#

```cpp
// C# program to find middle of
// three distinct numbers
using System;

class Middle
{
    // Function to find the middle of three number
    public static int middleOfThree(int a, int b,
                                        int c)
    {
        // Checking for b
        if ((a < b && b < c) || (c < b && b < a))
            return b;

        // Checking for a
        else if ((b < a && a < c) || (c < a && a < b))
        return a;

        else
        return c;
    }

    // Driver code
    public static void Main()
    {
        int a = 20, b = 30, c = 40;
        Console.WriteLine( middleOfThree(a, b, c) );
    }
}

// This code is contributed by vt_m
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to find middle
// of three distinct numbers

function middleOfThree($a, $b, $c)
{

    // Checking for b
    if (($a < $b && $b < $c) or
        ($c < $b && $b < $a))
    return $b;

    // Checking for a
    else if (($b < $a and $a < $c) or
             ($c < $a and $a < $b))
    return $a;

    else
    return $c;
}

    // Driver Code
    $a = 20;
    $b = 30;
    $c = 40;
    echo middleOfThree($a, $b, $c);

// This code is contributed by anuj_67.
?>
```

## java 描述语言

```cpp
<script>

// Javascript program to find  middle of three distinct
// numbers

function middleOfThree( a,  b, c)
{
    // Checking for b
    if ((a < b && b < c) || (c < b && b < a))
       return b;

    // Checking for a
    else if ((b < a && a < c) || (c < a && a < b))
       return a;

    else
       return c;
}

    // driver code

    let a = 20, b = 30, c = 40;
    document.write(middleOfThree(a, b, c));

</script>
```

**输出:**

```cpp
30
```

但是上面使用的方法效率不高，因为额外的比较很容易被最小化。如果第一部分为假，它将执行剩余的一半来检查条件。如果我们也检查 **a** ，这个问题仍然存在。
**更好的方法(需要更少的比较):**

## C++

```cpp
// CPP program to find middle of three distinct
// numbers
#include <bits/stdc++.h>
using namespace std;

// Function to find the middle of three numbers
int middleOfThree(int a, int b, int c)
{
    // Compare each three number to find middle
    // number. Enter only if a > b
    if (a > b)
    {
        if (b > c)
            return b;
        else if (a > c)
            return c;
        else
            return a;
    }
    else
    {
        // Decided a is not greater than b.
        if (a > c)
            return a;
        else if (b > c)
            return c;
        else
            return b;
    }
}

// Driver Code
int main()
{
    int a = 20, b = 30, c = 40;
    cout << middleOfThree(a, b, c);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find middle of
// three distinct numbers
import java.util.*;

class Middle
{  
    // Function to find the middle of three number
    public static int middleOfThree(int a, int b,
                                          int c)
    {
        // Compare each three number to find
        // middle number. Enter only if a > b
        if (a > b)
        {
            if (b > c)
                return b;
            else if (a > c)
                return c;
            else
                return a;
        }
        else
        {
            // Decided a is not greater than b.
            if (a > c)
                return a;
            else if (b > c)
                return c;
            else
                return b;
        }
    }

    // driver code
    public static void main(String[] args)
    {
        int a = 20, b = 30, c = 40;
        System.out.println(middleOfThree(a, b, c));
    }
}

// This code is contributed by rishabh_jain
```

## 蟒蛇 3

```cpp
# Python3 program to find middle
# of three distinct numbers

# Function to find the middle of three numbers
def middleOfThree(a, b, c) :

    # Compare each three number to find
    # middle number. Enter only if a > b
    if a > b :
        if (b > c):
            return b
        elif (a > c) :
            return c
        else :
            return a
    else:
        # Decided a is not greater than b.
        if (a > c) :
            return a
        elif (b > c) :
            return c
        else :
            return b

# Driver Code
a = 20
b = 30
c = 40
print( middleOfThree(a, b, c) )

# This code is contributed by rishabh_jain
```

## C#

```cpp
// C# program to find middle of
// three distinct numbers
using System;

class Middle
{
    // Function to find the middle of three number
    public static int middleOfThree(int a, int b,
                                            int c)
    {
        // Compare each three number to find
        // middle number. Enter only if a > b
        if (a > b)
        {
            if (b > c)
                return b;
            else if (a > c)
                return c;
            else
                return a;
        }
        else
        {
            // Decided a is not greater than b.
            if (a > c)
                return a;
            else if (b > c)
                return c;
            else
                return b;
        }
    }

    // Driver code
    public static void Main()
    {
        int a = 20, b = 30, c = 40;
        Console.WriteLine(middleOfThree(a, b, c));
    }
}

// This code is contributed by vt_m
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to find middle
// of three distinct numbers

// Function to find the middle
// of three numbers
function middleOfThree( $a, $b, $c)
{

    // Compare each three number
    // to find middle number.
    // Enter only if a > b
    if ($a > $b)
    {
        if ($b > $c)
            return $b;
        else if ($a > $c)
            return $c;
        else
            return $a;
    }
    else
    {

        // Decided a is not
        // greater than b.
        if ($a > $c)
            return $a;
        else if ($b > $c)
            return $c;
        else
            return $b;
    }
}

    // Driver Code
    $a = 20; $b = 30;
    $c = 40;
    echo middleOfThree($a, $b, $c);

// This code is contributed by anuj_67.
?>
```

## java 描述语言

```cpp
<script>
    // Javascript program to find middle of three distinct numbers

    // Function to find the middle of three number
    function middleOfThree(a, b, c)
    {
        // Compare each three number to find
        // middle number. Enter only if a > b
        if (a > b)
        {
            if (b > c)
                return b;
            else if (a > c)
                return c;
            else
                return a;
        }
        else
        {
            // Decided a is not greater than b.
            if (a > c)
                return a;
            else if (b > c)
                return c;
            else
                return b;
        }
    }

    let a = 20, b = 30, c = 40;
    document.write(middleOfThree(a, b, c));

    // This code is contributed by divyesh072019.
</script>
```

输出:

```cpp
30
```

这种方法效率高，比较次数少。只有在 a > b 的情况下才会执行外部 IF 循环，否则将执行外部 ELSE。
**其他有效方法:**

## C++

```cpp
// CPP program to find middle of three distinct
// numbers
#include <bits/stdc++.h>
using namespace std;

// Function to find the middle of three number
int middleOfThree(int a, int b, int c)
{
    // x is positive if a is greater than b.
    // x is negative if b is greater than a.
    int x = a - b;

    int y = b - c;  // Similar to x
    int z = a - c;  // Similar to x and y.

    // Checking if b is middle (x and y both
    // are positive)
    if (x * y > 0)
        return b;

    // Checking if c is middle (x and z both
    // are positive)
    else if (x * z > 0)
        return c;
    else
        return a;
}

// Driver Code
int main()
{
    int a = 20, b = 30, c = 40;
    cout << middleOfThree(a, b, c);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
//java program to find middle of three distinct
// numbers
import java.util.*;

class Middle
{  
    // Function to find the middle of three number
    public static int middleOfThree(int a, int b,
                                          int c)
    {
        // x is positive if a is greater than b.
        // x is negative if b is greater than a.
        int x = a - b;

        int y = b - c; // Similar to x
        int z = a - c; // Similar to x and y.

        // Checking if b is middle (x and y
        // both are positive)
        if (x * y > 0)
            return b;

        // Checking if c is middle (x and z
        // both are positive)
        else if (x * z > 0)
            return c;
        else
            return a;
    }

    // driver code
    public static void main(String[] args)
    {
        int a = 20, b = 30, c = 40;
        System.out.println( middleOfThree(a, b, c) );
    }
}

// This code is contributed by rishabh_jain
```

## 蟒蛇 3

```cpp
# Python3 program to find middle
# of three distinct numbers

# Function to find the middle of three number
def middleOfThree(a, b, c) :

    # x is positive if a is greater than b.
    # x is negative if b is greater than a.
    x = a - b

    # Similar to x
    y = b - c

    # Similar to x and y.
    z = a - c

    # Checking if b is middle (x and y
    # both are positive)
    if x * y > 0:
        return b

    # Checking if c is middle (x and z
    # both are positive)
    elif (x * z > 0) :
        return
    else :
        return a

# Driver Code
a = 20
b = 30
c = 40
print(middleOfThree(a, b, c))

# This code is contributed by rishabh_jain
```

## C#

```cpp
//C# program to find middle of three distinct
// numbers
using System;

class Middle
{
    // Function to find the middle of three number
    public static int middleOfThree(int a, int b,
                                        int c)
    {
        // x is positive if a is greater than b.
        // x is negative if b is greater than a.
        int x = a - b;

        // Similar to x
        int y = b - c;

         // Similar to x and y.
        int z = a - c;

        // Checking if b is middle (x and y
        // both are positive)
        if (x * y > 0)
            return b;

        // Checking if c is middle (x and z
        // both are positive)
        else if (x * z > 0)
            return c;
        else
            return a;
    }

    // Driver code
    public static void Main()
    {
        int a = 20, b = 30, c = 40;
        Console.WriteLine( middleOfThree(a, b, c) );
    }
}

// This code is contributed by vt_m
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to find middle
// of three distinct numbers

// Function to find the
// middle of three number
function middleOfThree($a, $b, $c)
{

    // x is positive if a
    // is greater than b.
    // x is negative if b
    // is greater than a.
    $x = $a - $b;

    // Similar to x
    $y = $b - $c;

    // Similar to x and y.
    $z = $a - $c;

    // Checking if b is
    // middle (x and y both
    // are positive)
    if ($x * $y > 0)
        return $b;

    // Checking if c is
    // middle (x and z both
    // are positive)
    else if ($x * $z > 0)
        return $c;
    else
        return $a;
}

    // Driver Code
    $a = 20;
    $b = 30;
    $c = 40;
    echo middleOfThree($a, $b, $c);

// This code is contributed by anuj_67.
?>
```

## java 描述语言

```cpp
<script>

// javascript program to find middle of
//  three distinct numbers

    // Function to find the middle of three number
    function middleOfThree(a, b, c)
    {
        // x is positive if a is greater than b.
        // x is negative if b is greater than a.
        let x = a - b;

        let y = b - c; // Similar to x
        let z = a - c; // Similar to x and y.

        // Checking if b is middle (x and y
        // both are positive)
        if (x * y > 0)
            return b;

        // Checking if c is middle (x and z
        // both are positive)
        else if (x * z > 0)
            return c;
        else
            return a;
    }

// Driver code

        let a = 20, b = 30, c = 40;
        document.write( middleOfThree(a, b, c) );

</script>
```

**输出:**

```cpp
30
```