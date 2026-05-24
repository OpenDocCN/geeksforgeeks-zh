# 检查给定点是位于矩形上还是矩形内|设置 3

> 原文: [https://www.geeksforgeeks.org/check-whether-a-given-point-lies-on-or-inside-the-rectangle-set-3/](https://www.geeksforgeeks.org/check-whether-a-given-point-lies-on-or-inside-the-rectangle-set-3/)

给出两个数字 `a` 和 `b`，其中 `b < a`，形成一个顶点为 `(0, b)`, `(b, 0)`, `(a-b, b)`, `(b, a-b)` 的矩形。给定一个点 `(x, y)`，任务是检查该点是否位于矩形内或矩形上。

**举例:**

```
Input: a = 7, b = 2, x = 5, y = 2;
Output: Given point does not lie on the rectangle

Input: a = 7, b = 2, x = 4, y = 5;
Output: Given point lies inside the rectangle
```

## 方法

一种有效的方法是形成矩形的 4 条线方程。然后，如果给定点位于矩形内或矩形上，当且仅当将给定点代入以下方程时：

1.  右侧边线 (`x-y-b = 0`) 必须给出小于或等于零的值。
2.  左侧边线 (`x-y+a = 0`) 必须给出大于或等于零的值。
3.  上边线 (`x+y-2*a+b = 0`) 必须给出小于或等于零的值。
4.  较低的边线 (`x+y-b = 0`) 必须给出大于或等于零的值。

## C++

```cpp
// C++ program to Check whether a given point
// lies inside or on the rectangle or not
#include <bits/stdc++.h>
using namespace std;

// function to Check whether a given point
// lies inside or on the rectangle or not
bool LiesInsieRectangle(int a, int b, int x, int y)
{
    if (x - y - b <= 0 && x - y + b >= 0
        && x + y - 2 * a + b <= 0 && x + y - b >= 0)
        return true;

    return false;
}

// Driver code
int main()
{
    int a = 7, b = 2, x = 4, y = 5;

    if (LiesInsieRectangle(a, b, x, y))
        cout << "Given point lies inside the rectangle";
    else
        cout << "Given point does not lie on the rectangle";

return 0;
}
```

## Java

```java
// Java program to Check whether
// a given point lies inside or
// on the rectangle or not
class GFG
{

// function to Check whether
// a given point lies inside
// or on the rectangle or not
static boolean LiesInsieRectangle(int a, int b,
                                  int x, int y)
{
if (x - y - b <= 0 && x - y + b >= 0 &&
    x + y - 2 * a + b <= 0 && x + y - b >= 0)
    return true;

return false;
}

// Driver code
public static void main(String[] args)
{
    int a = 7, b = 2, x = 4, y = 5;

    if (LiesInsieRectangle(a, b, x, y))
        System.out.println("Given point lies " +
                        "inside the rectangle");
    else
        System.out.println("Given point does not " +
                            "lie on the rectangle");
}
}

// This code is contributed
// by ChitraNayal
```

## Python 3

```python
# Python 3 program to Check whether
# a given point lies inside or on
# the rectangle or not

# function to Check whether a given
# point lies inside or on the
# rectangle or not
def LiesInsieRectangle(a, b, x, y) :

    if(x - y - b <= 0 and
       x - y + b >= 0 and
       x + y - 2 * a + b <= 0 and
       x + y - b >= 0) :
        return True

    return False

# Driver code
if __name__ == "__main__" :

    # multiple assignments
    a, b, x, y = 7, 2, 4, 5

    if LiesInsieRectangle(a, b, x, y) :
        print("Given point lies inside"
                  " the rectangle")
    else :
        print("Given point does not lie"
                " on the rectangle")

# This code is contributed by ANKITRAI1
```

## C#

```csharp
// C# program to Check whether
// a given point lies inside
// or on the rectangle or not
using System;
class GFG
{

// function to Check whether
// a given point lies inside
// or on the rectangle or not
static bool LiesInsieRectangle(int a, int b,
                               int x, int y)
{
if (x - y - b <= 0 &&
    x - y + b >= 0 &&
    x + y - 2 * a + b <= 0 &&
    x + y - b >= 0)
    return true;

return false;
}

// Driver code
public static void Main()
{
    int a = 7, b = 2, x = 4, y = 5;

    if (LiesInsieRectangle(a, b, x, y))
        Console.Write("Given point lies " +
                   "inside the rectangle");
    else
        Console.Write("Given point does not " +
                       "lie on the rectangle");
}
}

// This code is contributed
// by ChitraNayal
```

## PHP

```php
<?php
// PHP program to Check whether
// a given point lies inside
// or on the rectangle or not

// function to Check whether
// a given point lies inside
// or on the rectangle or not
function LiesInsieRectangle($a, $b,
                            $x, $y)
{
    if ($x - $y - $b <= 0 &&
        $x - $y + $b >= 0 &&
        $x + $y - 2 * $a + $b <= 0 &&
        $x + $y - $b >= 0)
        return true;

    return false;
}

// Driver code
$a = 7;
$b = 2;
$x = 4;
$y = 5;

if (LiesInsieRectangle($a, $b,
                       $x, $y))
    echo "Given point lies ".
         "inside the rectangle";
else
    echo "Given point does not".
        " lie on the rectangle";

// This code is contributed by mits
?>
```

## JavaScript

```javascript
<script>

// Javascript program to Check whether a given point
// lies inside or on the rectangle or not

// function to Check whether a given point
// lies inside or on the rectangle or not
function LiesInsieRectangle(a, b, x, y)
{
    if (x - y - b <= 0 && x - y + b >= 0
        && x + y - 2 * a + b <= 0 && x + y - b >= 0)
        return true;

    return false;
}

// Driver code

    let a = 7, b = 2, x = 4, y = 5;

    if (LiesInsieRectangle(a, b, x, y))
        document.write("Given point lies inside the rectangle");
    else
        document.write("Given point does not lie on the rectangle");

// This code is contributed by Mayank Tyagi

</script>
```

**Output:**

```
Given point lies inside the rectangle
```