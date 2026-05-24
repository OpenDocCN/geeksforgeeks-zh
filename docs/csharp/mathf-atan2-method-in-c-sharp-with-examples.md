# MathF。C# 中的 Atan2()方法，带示例

> 原文:[https://www . geesforgeks . org/mathf-atan 2-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-atan2-method-in-c-sharp-with-examples/)

**MathF。Atan2(Single，Single)** 方法用于返回正切为两个指定数字商的角度。基本上，它返回一个角度θ(以弧度测量)，其值介于-π和π之间。这是正 x 轴和点(x，y)之间的逆时针角度。

> **语法:**公共静态 float Atan2 (float y，float x)；
> 
> **参数:**
> **y:** 类型点的 y 坐标系统.单.
> **x:** 点的 x 坐标系统.单

**返回值:**该方法返回类型*系统的角度θ。单*。

**注:**一个角度θ(以弧度测量)，使得-π ≤ θ ≤ π，tan(θ) = value1 / value2，其中(value1，value2)是笛卡尔平面中的点。返回值有两个条件:

*   当点位于笛卡尔平面时
*   当点位于象限的边界上时

**例 1:**

```cs
// C# program to demonstrate the 
// MathF.Atan2(Single, Single) Method
using System; 

class Geeks { 

    // Main method 
    public static void Main() 
    { 
        // using MathF.Atan2(Single, Single) Method 
        // and converting result into degree 
        Console.Write(MathF.Atan2(10f, 10f) * (180 / MathF.PI)); 
    } 
} 
```

**Output:**

```cs
45

```

**例 2:**

```cs
// C# program to demonstrate the 
// MathF.Atan2(Single, Single) Method
using System; 

class Geeks { 

    // Main method 
    public static void Main() 
    { 
        // using MathF.Atan2(Single, Single) Method 
        // and converting result into degree 
        Console.Write(MathF.Atan2(0f, -7f) * (180 / MathF.PI)); 
    } 
} 
```

**Output:**

```cs
180

```