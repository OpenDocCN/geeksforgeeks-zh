# 检查两个给定的圆是否相互接触或相交

> 原文: [https://www.geeksforgeeks.org/check-two-given-circles-touch-intersect/](https://www.geeksforgeeks.org/check-two-given-circles-touch-intersect/)

有两个圆 A 和 B，其中心为 `C1(x1, y1)` 和 `C2(x2, y2)`，半径为 `R1` 和 `R2`。任务是检查圆圈 A 和 B 是否相互接触。

### 举例:

```
Input : C1 = (3,  4)
        C2 = (14, 18)
        R1 = 5, R2 = 8
Output : Circles do not touch each other.

Input : C1 = (2,  3)
        C2 = (15, 28)
        R1 = 12, R2 = 10
Output : Circles intersect with each other.

Input : C1 = (-10,  8)
        C2 = (14, -24)
        R1 = 30, R2 = 10
Input : -10 8
        14 -24 
        30 10
Output : Circle touch each other.
```

圆心 `C1` 和 `C2` 之间的距离计算为：
`C1C2 = sqrt((x1 - x2)^2 + (y1 - y2)^2)`。

有三种情况：
1. 如果 `C1C2 == R1 + R2`
     圆 A 和 B 彼此相切。
2. 如果 `C1C2 > R1 + R2`
     圆 A 和 B 彼此不接触。
3. 如果 `C1C2 < R1 + R2`
     圆彼此相交。

## C++

```cpp
// C++ program to check if two
// circles touch each other or not.
#include <bits/stdc++.h>
using namespace std;

int circle(int x1, int y1, int x2,
           int y2, int r1, int r2)
{
    int distSq = (x1 - x2) * (x1 - x2) +
                 (y1 - y2) * (y1 - y2);
    int radSumSq = (r1 + r2) * (r1 + r2);
    if (distSq == radSumSq)
        return 1;
    else if (distSq > radSumSq)
        return -1;
    else
        return 0;
}

// Driver code
int main()
{
    int x1 = -10, y1 = 8;
    int x2 = 14, y2 = -24;
    int r1 = 30, r2 = 10;
    int t = circle(x1, y1, x2,
                   y2, r1, r2);
    if (t == 1)
        cout << "Circle touch to"
             << " each other.";
    else if (t < 0)
        cout << "Circle not touch"
             << " to each other.";
    else
        cout << "Circle intersect"
             << " to each other.";
    return 0;
}
```

## Java

```java
// Java program to check if two
// circles touch each other or not.
import java.io.*;

class GFG
{
    static int circle(int x1, int y1, int x2,
                      int y2, int r1, int r2)
    {
        int distSq = (x1 - x2) * (x1 - x2) +
                     (y1 - y2) * (y1 - y2);
        int radSumSq = (r1 + r2) * (r1 + r2);
        if (distSq == radSumSq)
            return 1;
        else if (distSq > radSumSq)
            return -1;
        else
            return 0;
    }

    // Driver code
    public static void main (String[] args)
    {
        int x1 = -10, y1 = 8;
        int x2 = 14, y2 = -24;
        int r1 = 30, r2 = 10;
        int t = circle(x1, y1, x2,
                       y2, r1, r2);
        if (t == 1)
            System.out.println ( "Circle touch to" +
                              " each other.");
        else if (t < 0)
            System.out.println ( "Circle not touch" +
                              " to each other.");
        else
            System.out.println ( "Circle intersect" +
                              " to each other.");

    }
}

// This article is contributed by vt_m.
```

## Python 3

```python
# Python3 program to
# check if two circles touch
# each other or not.

def circle(x1, y1, x2, y2, r1, r2):

    distSq = (x1 - x2) * (x1 - x2) + (y1 - y2) * (y1 - y2);
    radSumSq = (r1 + r2) * (r1 + r2);
    if (distSq == radSumSq):
        return 1
    elif (distSq > radSumSq):
        return -1
    else:
        return 0

# Driver code
x1 = -10
y1 = 8
x2 = 14
y2 = -24
r1 = 30
r2 = 10

t = circle(x1, y1, x2, y2, r1, r2)
if (t == 1):
    print("Circle touch to each other.")
elif (t < 0):
    print("Circle not touch to each other.")
else:
    print("Circle intersect to each other.")

# This code is contributed by
# Smitha Dinesh Semwal
```

## C#

```csharp
// C# program to check if two
// circles touch each other or not.
using System;

class GFG
{
    static int circle(int x1, int y1, int x2,
                      int y2, int r1, int r2)
    {
        int distSq = (x1 - x2) * (x1 - x2) +
                     (y1 - y2) * (y1 - y2);
        int radSumSq = (r1 + r2) * (r1 + r2);
        if (distSq == radSumSq)
            return 1;
        else if (distSq > radSumSq)
            return -1;
        else
            return 0;
    }

    // Driver code
    public static void Main ()
    {
        int x1 = -10, y1 = 8;
        int x2 = 14, y2 = -24;
        int r1 = 30, r2 = 10;
        int t = circle(x1, y1, x2,
                       y2, r1, r2);
        if (t == 1)
            Console.WriteLine ( "Circle touch" +
                          " to each other.");
        else if (t < 0)
            Console.WriteLine( "Circle not touch" +
                            " to each other.");
        else
            Console.WriteLine ( "Circle intersect" +
                              " to each other.");

    }
}

// This code is contributed by vt_m.
```

## PHP

```php
<?php
// PHP program to check if two
// circles touch each other or not.

function circle($x1, $y1, $x2,
                $y2, $r1, $r2)
{
    $distSq = ($x1 - $x2) * ($x1 - $x2) +
              ($y1 - $y2) * ($y1 - $y2);
    $radSumSq = ($r1 + $r2) * ($r1 + $r2);
    if ($distSq == $radSumSq)
        return 1;
    else if ($distSq > $radSumSq)
        return -1;
    else
        return 0;
}

// Driver code
$x1 = -10; $y1 = 8;
$x2 = 14; $y2 = -24;
$r1 = 30; $r2 = 10;
$t = circle($x1, $y1, $x2,
            $y2, $r1, $r2);
if ($t == 1)
    echo "Circle touch to each other.";
else if ($t < 0)
    echo "Circle not touch to each other.";
else
    echo "Circle intersect to each other.";

// This code is contributed by vt_m.
?>
```

## JavaScript

```javascript
<script>

// JavaScript program to check if two
// circles touch each other or not.

function circle(x1, y1, x2,
                      y2, r1, r2)
    {
        let distSq = (x1 - x2) * (x1 - x2) +
                     (y1 - y2) * (y1 - y2);
        let radSumSq = (r1 + r2) * (r1 + r2);
        if (distSq == radSumSq)
            return 1;
        else if (distSq > radSumSq)
            return -1;
        else
            return 0;
    }

// Driver Code
        let x1 = -10, y1 = 8;
        let x2 = 14, y2 = -24;
        let r1 = 30, r2 = 10;
        let t = circle(x1, y1, x2,
                       y2, r1, r2);
        if (t == 1)
            document.write ( "Circle touch to" +
                              " each other.");
        else if (t < 0)
            document.write( "Circle not touch" +
                              " to each other.");
        else
            document.write ( "Circle intersect" +
                              " each other.");

 // This code is contributed by susmitakundugoaldanga.
</script>
```

**输出:**

```
Circle touch to each other.
```

本文由**达曼德拉·库马尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。