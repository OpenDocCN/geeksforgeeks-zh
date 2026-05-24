# 可内接在矩形内的最大椭圆，而矩形又内接在半圆内

> 原文: [https://www.geeksforgeeks.org/largest-ellipse-that-can-be-inscribed-within-a-rectangle-which-in-turn-is-inscribed-within-a-semicircle/](https://www.geeksforgeeks.org/largest-ellipse-that-can-be-inscribed-within-a-rectangle-which-in-turn-is-inscribed-within-a-semicircle/)

这里给定的是一个半径为`r`的半圆，它内接一个长方形，长方形又内接一个椭圆。任务是找到这个最大椭圆的面积。

**例:**

```
Input: r = 5
Output: 19.625

Input: r = 11
Output: 94.985
```

![](img/37823c9aa165ab4d5ce774992c58b0cf.png)

## 算法思路

1.  设矩形的长度=`l`，矩形的宽度=`b`。
2.  设椭圆长轴的长度=`2x`，椭圆短轴的长度=`2y`。
3.  我们知道，半圆内最大矩形的长宽分别为`r/√2`、`√2r`（[这里请参考](https://www.geeksforgeeks.org/largest-rectangle-that-can-be-inscribed-in-a-semicircle/)）。
4.  另外，矩形内椭圆的[面积](https://www.geeksforgeeks.org/area-of-the-biggest-ellipse-inscribed-within-a-rectangle/)=`(π* l * b)/4`=`(πr^2/4)`。

**以下是上述方式的实现：**

## C++

```cpp
// C++ Program to find the biggest ellipse
// which can be inscribed within a rectangle
// which in turn is inscribed within a semicircle

#include <bits/stdc++.h>
using namespace std;

// Function to find the area
// of the biggest ellipse
float ellipsearea(float r)
{

    // the radius cannot be negative
    if (r < 0)
        return -1;

    // area of the ellipse
    float a = (3.14 * r * r) / 4;

    return a;
}

// Driver code
int main()
{
    float r = 5;
    cout << ellipsearea(r) << endl;
    return 0;
}
```

## Java

```java
// Java Program to find the biggest ellipse
// which can be inscribed within a rectangle
// which in turn is inscribed within a semicircle
class GFG
{

// Function to find the area
// of the biggest ellipse
static float ellipsearea(float r)
{

    // the radius cannot be negative
    if (r < 0)
        return -1;

    // area of the ellipse
    float a = (float)((3.14f * r * r) / 4);

    return a;
}

// Driver code
public static void main(String[] args)
{
    float r = 5;
    System.out.println(ellipsearea(r));
}
}

// This code is contributed by Code_Mech.
```

## Python 3

```python
# Python3 Program to find the biggest ellipse
# which can be inscribed within a rectangle
# which in turn is inscribed within a semicircle

# Function to find the area of
# the biggest ellipse
def ellipsearea(r) :

    # the radius cannot be negative
    if (r < 0) :
        return -1;

    # area of the ellipse
    a = (3.14 * r * r) / 4;

    return a;

# Driver code
if __name__ == "__main__" :

    r = 5;
    print(ellipsearea(r));

# This code is contributed by Ryuga
```

## C#

```csharp
// C# Program to find the biggest ellipse
// which can be inscribed within a rectangle
// which in turn is inscribed within a semicircle
using System;
class GFG
{

// Function to find the area
// of the biggest ellipse
static float ellipsearea(float r)
{

    // the radius cannot be negative
    if (r < 0)
        return -1;

    // area of the ellipse
    float a = (float)((3.14 * r * r) / 4);

    return a;
}

// Driver code
public static void Main()
{
    float r = 5;
    Console.WriteLine(ellipsearea(r));
}
}

// This code is contributed by Akanksha Rai
```

## PHP

```php
<?php
// PHP Program to find the biggest ellipse
// which can be inscribed within a rectangle
// which in turn is inscribed within a semicircle

// Function to find the area
// of the biggest ellipse
function ellipsearea($r)
{

    // the radius cannot be negative
    if ($r < 0)
        return -1;

    // area of the ellipse
    $a = (3.14 * $r * $r) / 4;

    return $a;
}

// Driver code
$r = 5;
echo ellipsearea($r) . "\n";

// This code is contributed by Akanksha Rai
?>
```

## JavaScript

```javascript
<script>

// javascript Program to find the biggest ellipse
// which can be inscribed within a rectangle
// which in turn is inscribed within a semicircle

// Function to find the area
// of the biggest ellipse
function ellipsearea(r)
{

    // the radius cannot be negative
    if (r < 0)
        return -1;

    // area of the ellipse
    var a = ((3.14 * r * r) / 4);

    return a;
}

// Driver code
var r = 5;
document.write(ellipsearea(r));

// This code is contributed by Amit Katiyar

</script>
```

**Output:**

```
19.625
```