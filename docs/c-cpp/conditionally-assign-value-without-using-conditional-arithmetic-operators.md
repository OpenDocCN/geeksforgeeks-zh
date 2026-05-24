# 在不使用条件和算术运算符的情况下有条件地赋值

> 原文:[https://www . geesforgeks . org/有条件赋值不使用条件算术运算符/](https://www.geeksforgeeks.org/conditionally-assign-value-without-using-conditional-arithmetic-operators/)

给定 4 个整数 a、b、y 和 x，其中 x 只能取 0 或 1。提出了以下问题:

```cpp
If 'x' is 0, 
   Assign value 'a' to variable 'y' 
Else (If 'x' is 1)
   Assign value 'b' to variable 'y'.
```

注意:–不允许使用任何条件运算符(包括三元运算符)或任何算术运算符(+、-、*、/)。

**示例:**

```cpp
Input :  a = 5 , b = 10, x = 1
Output :  y = 10

Input : a = 5, b = 10 , x = 0
Output :  y = 5
```

问于:谷歌采访

**解决方案 1:**

一个想法是简单地将“a”和“b”分别存储在第 0 和第 1 个索引处的数组中。然后将“x”作为索引，将值存储到“y”中。

下面是上述方法的实现:

## C++

```cpp
// C/C++ program to assign value to y according
// to value of x

#include <iostream>
using namespace std;

// Function to assign value to y according
// to value of x
int assignValue(int a, int b, int x)
{
    int y;
    int arr[2];

    // Store both values in an array
    // value 'a' at 0th index
    arr[0] = a;

    // Value 'b' at 1th index
    arr[1] = b;

    // Assign value to 'y' taking 'x' as index
    y = arr[x];

    return y;
}

// Driver code
int main()
{
    int a = 5;
    int b = 10;
    int x = 0;

    cout << "Value assigned to 'y' is "
         << assignValue(a, b, x);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to assign value to y according
// to value of x

public class GFG {
    static int assignValue(int a, int b, int x)
    {
        int y;
        int arr[] = new int[2];

        // Store both values in an array
        // value 'a' at 0th index
        arr[0] = a;

        // Value 'b' at 1th index
        arr[1] = b;

        // Assign value to 'y' taking 'x' as index
        y = arr[x];

        return y;
    }

    // Driver Method
    public static void main(String[] args)
    {
        int a = 5;
        int b = 10;
        int x = 0;

        System.out.println("Value assigned to 'y' is "
                           + assignValue(a, b, x));
    }
}
```

## 计算机编程语言

```cpp
# Python 3 program to assign value to
# y according to value of x

# Function to assign value to y
# according to value of x

def assignValue(a, b, x):

    arr = [0] * 2

    # Store both values in an array
    # value 'a' at 0th index
    arr[0] = a

    # Value 'b' at 1th index
    arr[1] = b

    # Assign value to 'y' taking 'x'
    # as index
    y = arr[x]

    return y

# Driver code
if __name__ == "__main__":

    a = 5
    b = 10
    x = 0

    print("Value assigned to 'y' is",
          assignValue(a, b, x))

# This code is contributed by ita_c
```

## C#

```cpp
// C# program to assign value to y according
// to value of x
using System;

public class GFG {

    static int assignValue(int a, int b, int x)
    {
        int y;
        int[] arr = new int[2];

        // Store both values in an array
        // value 'a' at 0th index
        arr[0] = a;

        // Value 'b' at 1th index
        arr[1] = b;

        // Assign value to 'y' taking 'x'
        // as index
        y = arr[x];

        return y;
    }

    // Driver Code
    public static void Main()
    {
        int a = 5;
        int b = 10;
        int x = 0;

        Console.Write("Value assigned to "
                      + "'y' is " + assignValue(a, b, x));
    }
}

// This code is contributed by nitin mittal.
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to assign value
// to y according to value of x

// Function to assign value
// to y according to value of x
function assignValue($a, $b, $x)
{
    $y;
    $arr = array(0, 0);

    // Store both values in an array
    // value 'a' at 0th index
    $arr[0] = $a;

    // Value 'b' at 1th index
    $arr[1] = $b;

    // Assign value to 'y'
    // taking 'x' as index
    $y = $arr[$x];

    return $y;
}

// Driver code
$a = 5;
$b = 10;
$x = 0;

echo "Value assigned to 'y' is " .
        assignValue($a, $b, $x);

// This code is contributed by Anuj_67
?>
```

## java 描述语言

```cpp
<script>
// javascript program to assign value to y according
// to value of x

    function assignValue(a , b , x) {
        var y;
        var arr = Array(2);

        // Store both values in an array
        // value 'a' at 0th index
        arr[0] = a;

        // Value 'b' at 1th index
        arr[1] = b;

        // Assign value to 'y' taking 'x' as index
        y = arr[x];

        return y;
    }

    // Driver Method

        var a = 5;
        var b = 10;
        var x = 0;

        document.write("Value assigned to 'y' is "
        + assignValue(a, b, x));

// This code is contributed by todaysgaurav
</script>
```

**Output**

```cpp
Value assigned to 'y' is 5
```

**溶液 2:**

使用按位“与”运算符。

## C++

```cpp
// C/C++ program to assign value to y according
// to value of x

#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int a = 5;
    int b = 10;
    int x = 1;
    int y;

    if (x & 1)
        y = b;
    else
        y = a;
    cout << "Value assigned to 'y' is " << y << endl;
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to assign value to y according
// to value of x
import java.io.*;
class GFG
{

  // Driver Code
  public static void main (String[] args)
  {   
    int a = 5;
    int b = 10;
    int x = 1;
    int y;
    if ((x & 1) != 0)
      y = b;
    else
      y = a;
    System.out.println("Value assigned to 'y' is " + y);
  }
}

// This code is contributed by avanitrachhadiya2155
```

## 蟒蛇 3

```cpp
# Python3 program to assign value to y
# according to value of x

# Driver Code
a = 5
b = 10
x = 1
y = 0

if ((x & 1) != 0):
    y = b
else:
    y = a

print("Value assigned to 'y' is ", y)

# This code is contributed by ab2127
```

## C#

```cpp
// C# program to assign value to y according
// to value of x
using System;
public class GFG
{

  // Driver Code
  static public void Main ()
  {

    int a = 5;
    int b = 10;
    int x = 1;
    int y;
    if ((x & 1) != 0)
      y = b;
    else
      y = a;
    Console.WriteLine("Value assigned to 'y' is " + y);
  }
}

// This code is contributed by rag2127
```

## java 描述语言

```cpp
<script>

// Javascript program to assign value to y according
// to value of x

    // Driver Code

        var a = 5;
        var b = 10;
        var x = 1;
        var y;
        if ((x & 1) != 0)
            y = b;
        else
            y = a;
        document.write("Value assigned to 'y' is " + y);

// This code contributed by Rajput-Ji

</script>
```

**Output**

```cpp
Value assigned to 'y' is 10
```

参考:[https://www.careercup.com/question?id=5135296679116800](https://www.careercup.com/question?id=5135296679116800)

本文由 [**萨希尔·查布拉(akku)**](https://www.facebook.com/sahil.chhabra.965) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。