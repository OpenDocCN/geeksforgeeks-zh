# 找出给定混合物中达到目标比例的添加量

> 原文:[https://www . geesforgeks . org/find-待添加量-达到给定混合物中的目标比率/](https://www.geeksforgeeks.org/find-amount-to-be-added-to-achieve-target-ratio-in-a-given-mixture/)

给你一个装着酒和水混合物的 X 升容器。混合物中含有 10%的水.要增加水与 Y%的比例，必须加多少升水？
输入分别包含 3 个整数:X、W、Y。
输出应为浮点格式，最多 2 个小数点。

**示例:**

> 输入:X = 125，W = 20，Y = 25
> 输出:8.33 升
> 125 的 20%为 25。如果我们加 8.33 升，得到 33.33，是 133.33 的 25%。
> 
> 输入:X = 100，W = 50，Y = 60
> 输出:25

> 让要加入的水量为 1 升.
> 所以，新的混合物量= (X + A)升
> 和混合物中的水量=(旧的量+A)=((X 的 W %)+A)
> 同样，混合物中的水量=新混合物中水的新百分比= Y %的(X + A)
> 现在，我们可以把表达式写成
> —————T5】Y %的(X + A) = W %的 X + A
> ——————————
> 通过简化这个表达式，我们会得到
> **A =[X *(Y–W)]/[100–Y]**
> 插图:
> X = 125，W = 20%，Y = 25%；
> 那么，对于给定的问题，要加入的水量=(125 *(25–20))/(100–25)= 8.33 升。

下面是上述方法的实现:

## C

```cpp
// C program to find amount of water to
// be added to achieve given target ratio.
#include <stdio.h>

float findAmount(float X, float W, float Y)
{
    return (X * (Y - W)) / (100 - Y);
}

int main()
{
    float X = 100, W = 50, Y = 60;
    printf("Water to be added = %.2f ",
                 findAmount(X, W, Y));
    return 0;
}   
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find amount of water to
// be added to achieve given target ratio.

public class GFG {

    static float findAmount(float X, float W, float Y)
    {
        return (X * (Y - W)) / (100 - Y);
    }

    // Driver code
    public static void main(String args[])
    {
           float X = 100, W = 50, Y = 60;
           System.out.println("Water to be added = "+ findAmount(X, W, Y));

    }
    // This code is contributed by ANKITRAI1
}
```

## 蟒蛇 3

```cpp
# Python3 program to find amount
# of water to be added to achieve
# given target ratio.
def findAmount(X, W, Y):

    return (X * (Y - W) / (100 - Y))

X = 100
W = 50; Y = 60
print("Water to be added",
       findAmount(X, W, Y))

# This code is contributed
# by Shrikant13
```

## C#

```cpp
// C# program to find amount of water to
// be added to achieve given target ratio.
using System;
class GFG
{

public static double findAmount(double X,
                                double W,
                                double Y)
{
    return (X * (Y - W)) / (100 - Y);
}

// Driver code
public static void Main()
{
    double X = 100, W = 50, Y = 60;
    Console.WriteLine("Water to be added = {0}",
                           findAmount(X, W, Y));
}
}

// This code is contributed by Soumik
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to find amount of water to
// be added to achieve given target ratio.
function findAmount($X, $W, $Y)
{
    return ($X * ($Y - $W)) / (100 - $Y);
}

// Driver Code
$X = 100; $W = 50; $Y = 60;
echo "Water to be added = " .
      findAmount($X, $W, $Y);

// This code is contributed
// by Akanksha Rai
?>
```

## java 描述语言

```cpp
<script>
    // Javascript program to find amount of water to
    // be added to achieve given target ratio.

    function findAmount(X, W, Y)
    {
        return (X * (Y - W)) / (100 - Y);
    }

    let X = 100, W = 50, Y = 60;
    document.write("Water to be added = "+ findAmount(X, W, Y).toFixed(2));

</script>
```

**Output:** 

```cpp
Water to be added = 25.00
```