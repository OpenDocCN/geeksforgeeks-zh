# 可内接半圆的最大矩形

> 原文：[https://www.geeksforgeeks.org/largest-rectangle-that-can-be-inscribed-in-a-semicircle/](https://www.geeksforgeeks.org/largest-rectangle-that-can-be-inscribed-in-a-semicircle/)

给定一个半径为 `r` 的半圆，我们必须找到半圆中可以内接的最大矩形，底部位于直径上。

**例：**

```
Input : r = 4
Output : 16

Input : r = 5 
Output :25
```

![](img/47904e1dac5ce5212f87433719212aac.png)

设 `r` 为半圆半径，`x` 为矩形底边的一半，`y` 为矩形高度。我们希望面积最大化，`A = 2xy`。
所以从图中我们有，
`y = √(r^2–x^2)`
所以，`A = 2*x*(√(r^2–x^2))`，或者 `dA/dx = 2*√(r^2–x^2)-2*x^2/√(r^2–x^2)`
设置这个导数等于 0 并求解为 `x`，
`dA/dx = 0`
或者，`2*√(r^2–x^2)–2*x^2/√(r^2–x^2)= 0`
`2r^2–4x^2 = 0`
`x = r/√2`
这是面积的最大值 as，
`dA/dx>0` 当 `x<r/√2` 和，`dA/dx < 0` 当 `x>r/√2`
所以，最大面积 `A=r^2`

## C++

```cpp
// C++ Program to find the
// the biggest rectangle
// which can be inscribed
// within the semicircle
#include <bits/stdc++.h>
using namespace std;

// Function to find the area
// of the biggest rectangle
float rectanglearea(float r)
{

    // the radius cannot be negative
    if (r < 0)
        return -1;

    // area of the rectangle
    float a = r * r;

    return a;
}

// Driver code
int main()
{
    float r = 5;
    cout << rectanglearea(r) << endl;
    return 0;
}
```

## Java

```java
// Java Program to find the
// the biggest rectangle
// which can be inscribed
// within the semicircle
class GFG
{

// Function to find the area
// of the biggest rectangle
static float rectanglearea(float r)
{

// the radius cannot be negative
if (r < 0)
    return -1;

// area of the rectangle
float a = r * r;

return a;
}

// Driver code
public static void main(String[] args)
{
    float r = 5;
    System.out.println((int)rectanglearea(r));
}
}

// This code is contributed
// by ChitraNayal
```

## Python 3

```python
# Python 3 Program to find the
# the biggest rectangle
# which can be inscribed
# within the semicircle

# Function to find the area
# of the biggest rectangle
def rectanglearea(r) :

    # the radius cannot
    # be negative
    if r < 0 :
        return -1

    # area of the rectangle
    a = r * r

    return a

# Driver Code
if __name__ == "__main__" :

    r = 5

    # function calling
    print(rectanglearea(r))

# This code is contributed
# by ANKITRAI1
```

## C#

```csharp
// C# Program to find the
// the biggest rectangle
// which can be inscribed
// within the semicircle
using System;

class GFG
{

// Function to find the area
// of the biggest rectangle
static float rectanglearea(float r)
{

// the radius cannot be negative
if (r < 0)
    return -1;

// area of the rectangle
float a = r * r;

return a;
}

// Driver code
public static void Main()
{
    float r = 5;
    Console.Write((int)rectanglearea(r));
}
}

// This code is contributed
// by ChitraNayal
```

## PHP

```php
<?php
// PHP Program to find the
// the biggest rectangle
// which can be inscribed
// within the semicircle

// Function to find the area
// of the biggest rectangle
function rectanglearea($r)
{

    // the radius cannot
    // be negative
    if ($r < 0)
        return -1;

    // area of the rectangle
    $a = $r * $r;

    return $a;
}

// Driver code
$r = 5;
echo rectanglearea($r)."\n";

// This code is contributed
// by ChitraNayal
?>
```

## JavaScript

```javascript
<script>

// javascript Program to find the
// the biggest rectangle
// which can be inscribed
// within the semicircle

// Function to find the area
// of the biggest rectangle
function rectanglearea(r)
{

    // the radius cannot be negative
    if (r < 0)
        return -1;

    // area of the rectangle
    var a = r * r;

    return a;
}

// Driver code

var r = 5;
document.write(parseInt(rectanglearea(r)));

// This code is contributed by Amit Katiyar

</script>
```

**输出：**

```
25
```