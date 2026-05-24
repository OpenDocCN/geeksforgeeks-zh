# 在给定斜率的直线上找到给定距离的点

> 原文: [https://www.geeksforgeeks.org/find-points-at-a-given-distance-on-a-line-of-given-slope/](https://www.geeksforgeeks.org/find-points-at-a-given-distance-on-a-line-of-given-slope/)

给定二维点 `p` 的坐标 `(x0, y0)`。求距其距离为 `L` 的点，这样由这些点连接而成的直线斜率为 `m`。

## 示例

```
Input : p = (2, 1)
        L = sqrt(2)
        M = 1
Output :3, 2
        1, 0
Explanation:
The two points are sqrt(2) distance away 
from the source and have the required slope
m = 1.

Input : p = (1, 0)
        L = 5
        M = 0
Output : 6, 0
        -4, 0
```

我们需要找到与给定点距离为 `L` 的两个点，在斜率为 `m` 的直线上。
这个想法已经在下面的帖子中介绍过了。
[使用中点找到矩形的角](https://www.geeksforgeeks.org/find-corners-of-rectangle-using-mid-points/)

根据输入斜率，问题可以分为 3 类。

1.  如果斜率为零，我们只需要调整源点的 `x` 坐标。
2.  如果斜率是无限的，我们需要调整 `y` 坐标。
3.  对于斜率的其他值，我们可以使用以下等式来找到这些点。

![Given that the point (x, y) is at distance l away from (x_0, y_0) \\newline \\newline (y-y_0)^{2} + (x-x_0)^{2}= l^{2} \\newline \\newline Also as the line that passes through (x, y) and (x0, y0) satisfies \\newline \\newline \\frac{y-y_0}{x-x_0}= m \\newline \\newline Rearranging we get \\newline y=y_0+m*(x-x_0) \\newline \\newline Putting the values in first equation \\newline \\newline m^2.(x-x_0)^2+(x-x_0)^2=l^2 \\newline \\newline Hence, we have \\newline \\newline x=x_0\\pm l.\\sqrt{\\frac{1}{1+m^2}} \\newline \\newline y=y_0 \\pm m.l.\\sqrt{\\frac{1}{1+m^2}}](img/9510caef2d796d872216ada311be3415.png "Rendered by QuickLaTeX.com")

现在使用上面的公式，我们可以找到所需的点。

## C++

```
// C++ program to find the points on a line of
// slope M at distance L
#include <bits/stdc++.h>
using namespace std;

// structure to represent a co-ordinate
// point
struct Point {

float x, y;
    Point()
    {
        x = y = 0;
    }
    Point(float a, float b)
    {
        x = a, y = b;
    }
};

// Function to print pair of points at
// distance 'l' and having a slope 'm'
// from the source
void printPoints(Point source, float l,
                                 int m)
{
    // m is the slope of line, and the
    // required Point lies distance l
    // away from the source Point
    Point a, b;

// slope is 0
    if (m == 0) {
        a.x = source.x + l;
        a.y = source.y;

b.x = source.x - l;
        b.y = source.y;
    }

// if slope is infinite
    else if (m == std::numeric_limits<float>
                                 ::max()) {
        a.x = source.x;
        a.y = source.y + l;

b.x = source.x;
        b.y = source.y - l;
    }
    else {
        float dx = (l / sqrt(1 + (m * m)));
        float dy = m * dx;
        a.x = source.x + dx;
        a.y = source.y + dy;
        b.x = source.x - dx;
        b.y = source.y - dy;
    }

// print the first Point
    cout << a.x << ", " << a.y << endl;

// print the second Point
    cout << b.x << ", " << b.y << endl;
}

// driver function
int main()
{
    Point p(2, 1), q(1, 0);
    printPoints(p, sqrt(2), 1);
    cout << endl;
    printPoints(q, 5, 0);
    return 0;
}
```

## Java

```
// Java program to find the points on 
// a line of slope M at distance L
class GFG{

// Class to represent a co-ordinate
// point
static class Point
{
    float x, y;
    Point()
    {
        x = y = 0;
    }
    Point(float a, float b)
    {
        x = a;
        y = b;
    }
};

// Function to print pair of points at
// distance 'l' and having a slope 'm'
// from the source
static void printPoints(Point source,
                        float l, int m)
{

// m is the slope of line, and the
    // required Point lies distance l
    // away from the source Point
    Point a = new Point();
    Point b = new Point();

// Slope is 0
    if (m == 0)
    {
        a.x = source.x + l;
        a.y = source.y;

b.x = source.x - l;
        b.y = source.y;
    }

// If slope is infinite
    else if (Double.isInfinite(m))
    {
        a.x = source.x;
        a.y = source.y + l;

b.x = source.x;
        b.y = source.y - l;
    }
    else
    {
        float dx = (float)(l / Math.sqrt(1 + (m * m)));
        float dy = m * dx;
        a.x = source.x + dx;
        a.y = source.y + dy;
        b.x = source.x - dx;
        b.y = source.y - dy;
    }

// Print the first Point
    System.out.println(a.x + ", " + a.y);

// Print the second Point
    System.out.println(b.x + ", " + b.y);
}

// Driver code
public static void main(String[] args)
{
    Point p = new Point(2, 1),
          q = new Point(1, 0);
    printPoints(p, (float)Math.sqrt(2), 1);

System.out.println();

printPoints(q, 5, 0);
}
}

// This code is contributed by Rajnis09
```

## C#

```
// C# program to find the points on 
// a line of slope M at distance L
using System;

class GFG{

// Class to represent a co-ordinate
// point
public class Point
{
    public float x, y;

public Point()
    {
        x = y = 0;
    }

public Point(float a, float b)
    {
        x = a;
        y = b;
    }
};

// Function to print pair of points at
// distance 'l' and having a slope 'm'
// from the source
static void printPoints(Point source,
                        float l, int m)
{

// m is the slope of line, and the
    // required Point lies distance l
    // away from the source Point
    Point a = new Point();
    Point b = new Point();

// Slope is 0
    if (m == 0)
    {
        a.x = source.x + l;
        a.y = source.y;

b.x = source.x - l;
        b.y = source.y;
    }

// If slope is infinite
    else if (Double.IsInfinity(m))
    {
        a.x = source.x;
        a.y = source.y + l;

b.x = source.x;
        b.y = source.y - l;
    }
    else
    {
        float dx = (float)(l / Math.Sqrt(
                           1 + (m * m)));
        float dy = m * dx;
        a.x = source.x + dx;
        a.y = source.y + dy;
        b.x = source.x - dx;
        b.y = source.y - dy;
    }

// Print the first Point
    Console.WriteLine(a.x + ", " + a.y);

// Print the second Point
    Console.WriteLine(b.x + ", " + b.y);
}

// Driver code
public static void Main(String[] args)
{
    Point p = new Point(2, 1),
          q = new Point(1, 0);

printPoints(p, (float)Math.Sqrt(2), 1);

Console.WriteLine();

printPoints(q, 5, 0);
}
}

// This code is contributed by Amit Katiyar
```

## 输出

```
3, 2
1, 0

6, 0
-4, 0
```

本文由 [**阿舒托什·库马尔**](https://in.linkedin.com/in/ashutosh-kumar-9527a7105) 供稿😀如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `review-team@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。