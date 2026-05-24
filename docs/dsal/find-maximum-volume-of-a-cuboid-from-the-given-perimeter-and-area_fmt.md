# 从给定的周长和面积找到长方体的最大体积

> 原文：[https://www.geeksforgeeks.org/find-maximum-volume-of-a-cuboid-from-the-given-perimeter-and-area/](https://www.geeksforgeeks.org/find-maximum-volume-of-a-cuboid-from-the-given-perimeter-and-area/)

给定周长 `P` 和面积 `A`，任务是由给定的周长和表面积计算出长方体形状的最大体积。

**示例：**

```
Input: P = 24, A = 24
Output: 8

Input: P = 20, A = 14
Output: 3
```

**方法：** 对于给定的长方体周长，我们有 `P = 4(l+b+h)` — (I)；
对于给定的长方体面积，我们有 `A = 2(lb+bh+lh)` — (ii)。
长方体的体积是 `V = lbh`
体积取决于三个变量 `l`，`b`，`h`，让我们让它只取决于长度。

> `V = lbh`，
> => `V = l(A/2-(lb+lh))` {来自等式(ii)}
> => `V = lA/2–l^2(b+h)`
> => `V = lA/2–l^2(P/4-l)` {来自等式(I)}
> => `V = lA/2–l^2P/4+l^3` — (iii)
> `dV/dl = A/2–lP/2+3l^2`
> 解完 `l` 中的二次方程后，我们有 `l = (P – (P^2-24A)^(1/2))/12`
> 代入(iii)中 `l` 的值，就可以很容易找到最大容积。

下面是上述方法的实现：

## C++

```cpp
// C++ implementation of the above approach
#include <bits/stdc++.h>
using namespace std;

// function to return maximum volume
float maxVol(float P, float A)
{
    // calculate length
    float l = (P - sqrt(P * P - 24 * A)) / 12;

    // calculate volume
    float V = l * (A / 2.0 - l * (P / 4.0 - l));

    // return result
    return V;
}

// Driver code
int main()
{
    float P = 20, A = 16;

    // Function call
    cout << maxVol(P, A);

    return 0;
}
```

## Java

```java
// Java implementation of the above approach
import java.util.*;

class Geeks {

    // function to return maximum volume
    static float maxVol(float P, float A)
    {
        // calculate length
        float l
            = (float)(P - Math.sqrt(P * P - 24 * A)) / 12;

        // calculate volume
        float V
            = (float)(l * (A / 2.0 - l * (P / 4.0 - l)));

        // return result
        return V;
    }

    // Driver code
    public static void main(String args[])
    {
        float P = 20, A = 16;

        // Function call
        System.out.println(maxVol(P, A));
    }
}

// This code is contributed by Kirti_Mangal
```

## Python 3

```python
# Python3 implementation of the
# above approach
from math import sqrt

# function to return maximum volume
def maxVol(P, A):

    # calculate length
    l = (P - sqrt(P * P - 24 * A)) / 12

    # calculate volume
    V = l * (A / 2.0 - l * (P / 4.0 - l))

    # return result
    return V

# Driver code
if __name__ == '__main__':
    P = 20
    A = 16

    # Function call
    print(maxVol(P, A))

# This code is contributed
# by Surendra_Gangwar
```

## C#

```csharp
// C# implementation of the above approach
using System;

class GFG {

    // function to return maximum volume
    static float maxVol(float P, float A)
    {
        // calculate length
        float l
            = (float)(P - Math.Sqrt(P * P - 24 * A)) / 12;

        // calculate volume
        float V
            = (float)(l * (A / 2.0 - l * (P / 4.0 - l)));

        // return result
        return V;
    }

    // Driver code
    public static void Main()
    {
        float P = 20, A = 16;

        // Function call
        Console.WriteLine(maxVol(P, A));
    }
}

// This code is contributed
// by Akanksha Rai
```

## PHP

```php
<?php
// PHP implementation of the above approach

// function to return maximum volume
function maxVol($P, $A)
{
    // calculate length
    $l = ($P - sqrt($P * $P - 24 * $A)) / 12;

    // calculate volume
    $V = $l * ($A / 2.0 - $l *
              ($P / 4.0 - $l));

    // return result
    return $V;
}

// Driver code
$P = 20;
$A = 16;

// Function call
echo maxVol($P, $A);

// This code is contributed by mits
?>
```

## JavaScript

```javascript
<script>
// javascript implementation of the above approach

// function to return maximum volume
function maxVol( P,  A)
{

    // calculate length
    let l = (P - Math.sqrt(P * P - 24 * A)) / 12;

    // calculate volume
    let V = l * (A / 2.0 - l * (P / 4.0 - l));

    // return result
    return V;
}

// Driver code
    let P = 20, A = 16;

    // Function call
    document.write(maxVol(P, A).toFixed(5));

// This code is contributed by aashish1995
</script>
```

**Output**

```
4.14815
```