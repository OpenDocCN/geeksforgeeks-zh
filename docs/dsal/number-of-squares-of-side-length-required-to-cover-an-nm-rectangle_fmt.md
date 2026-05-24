# 覆盖一个 N*M 矩形所需的边长平方数

> 原文：[https://www.geeksforgeeks.org/number-of-squares-of-side-length-required-to-cover-an-nm-rectangle/](https://www.geeksforgeeks.org/number-of-squares-of-side-length-required-to-cover-an-nm-rectangle/)

给出三个数字 `N`、`M`、`a`。找到覆盖 `N * M` 矩形所需的尺寸 `a*a` 的方块数。

**注** :

*   允许覆盖大于矩形的表面，但矩形必须被覆盖。
*   不允许打破正方形。
*   正方形的边应该与长方形的边平行。

**示例** :

```
Input: N = 6, M = 6, a = 4
Output: 4

Input: N = 2, M = 3, a = 1
Output: 6
```

## 方法

一个有效的方法是进行观察，找到公式。每个正方形的边必须平行于矩形的边的约束允许分别分析 X 轴和 Y 轴，即需要多少个长度为 `a` 的正方形来覆盖长度为 `m` 和 `n` 的矩形，并取这两个量的乘积。覆盖 `m` 尺寸矩形所需的边长为 `a` 的小正方形的数量为 `ceil(m/a)`。同样，覆盖 `n` 个矩形所需的 `a` 个正方形的数量是 `ceil(n/a)`。

那么，答案将是 `ceil(m/a) * ceil(n/a)`。

以下是上述方法的实现：

## C++

```cpp
// CPP program to find number of squares
// of a*a required to cover n*m rectangle
#include <bits/stdc++.h>
using namespace std;

// function to find number of squares
// of a*a required to cover n*m rectangle
int Squares(int n, int m, int a)
{
    return ((m + a - 1) / a) * ((n + a - 1) / a);
}

// Driver code
int main()
{
    int n = 6, m = 6, a = 4;

    // function call
    cout << Squares(n, m, a);

    return 0;
}
```

## Java

```java
// Java program to find number of squares
// of a*a required to cover n*m rectangle
import java.util.*;

class solution
{

// function to find a number of squares
// of a*a required to cover n*m rectangle
static int Squares(int n, int m, int a)
{

    return ((m + a - 1) / a) * ((n + a - 1) / a);

}

// Driver code
public static void main(String arr[])
{
    int n = 6, m = 6, a = 4;

    // function call
    System.out.println(Squares(n, m, a));

}

}
//This code is contributed by Surendra_Gangwar
```

## Python 3

```python
# Python 3 program to find number
# of squares of a*a required to
# cover n*m rectangle

# function to find number of
# squares of a*a required to
# cover n*m rectangle
def Squares(n, m, a):
    return (((m + a - 1) // a) *
            ((n + a - 1) // a))

# Driver code
if __name__ == "__main__":
    n = 6
    m = 6
    a = 4

    # function call
    print(Squares(n, m, a))

# This code is contributed
# by ChitraNayal
```

## C#

```csharp
// CSHARP program to find number of squares
// of a*a required to cover n*m rectangle

using System;

class GFG
{
    // function to find a number of squares
    // of a*a required to cover n*m rectangle
    static int Squares(int n, int m, int a)
    {

        return ((m + a - 1) / a) * ((n + a - 1) / a);

    }

    static void Main()
    {
          int n = 6, m = 6, a = 4;

         // function call
         Console.WriteLine(Squares(n, m, a));
    }
    // This code is contributed by ANKITRAI1
}
```

## PHP

```php
<?php
// PHP program to find number of squares
// of a*a required to cover n*m rectangle

// function to find number of squares
// of a*a required to cover n*m rectangle
function Squares($n, $m, $a)
{
    return ((int)(($m + $a - 1) / $a)) *
           ((int)(($n + $a - 1) / $a));
}

// Driver code
$n = 6; $m = 6; $a = 4;

// function call
echo Squares($n, $m, $a);

// This code is contributed
// by Akanksha Rai
?>
```

## JavaScript

```javascript
<script>

// JavaScript program to find number of squares
// of a*a required to cover n*m rectangle

// function to find a number of squares
// of a*a required to cover n*m rectangle
function Squares(n, m, a)
{
    return parseInt(((m + a - 1) / a)) *
           parseInt(((n + a - 1) / a));
}

// Driver code
var n = 6, m = 6, a = 4;

// Function call
document.write(Squares(n, m, a));

// This code is contributed by Ankita saini

</script>
```

**Output:**

```
4
```