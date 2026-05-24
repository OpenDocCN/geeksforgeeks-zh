# MathF.Atan2() 方法（C#）及示例

> 原文：[https://www.geeksforgeeks.org/mathf-atan2-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/mathf-atan2-method-in-c-sharp-with-examples/)

`MathF.Atan2(Single, Single)` 方法用于返回正切为两个指定数字商的角度。基本上，它返回一个角度θ（以弧度测量），其值介于 -π 和 π 之间。这是正 x 轴和点 (x, y) 之间的逆时针角度。

## 语法
```csharp
public static float Atan2 (float y, float x);
```

## 参数
- `y`：类型点的 y 坐标，`Single`。
- `x`：点的 x 坐标，`Single`。

## 返回值
该方法返回类型为 `Single` 的角度θ。

## 注
一个角度θ（以弧度测量），使得 -π ≤ θ ≤ π，`tan(θ) = value1 / value2`，其中 (value1, value2) 是笛卡尔平面中的点。返回值有两个条件：
- 当点位于笛卡尔平面时
- 当点位于象限的边界上时

## 示例 1
```csharp
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

**输出：**
```csharp

```

## 示例 2
```csharp
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

**输出：**
```csharp

```