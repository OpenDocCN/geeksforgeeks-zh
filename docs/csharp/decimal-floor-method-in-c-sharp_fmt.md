# 小数。C# 中的 `Floor()` 方法

> 原文：[https://www.geeksforgeeks.org/decimal-floor-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-floor-method-in-c-sharp/)

此方法用于将小数舍入到最接近负无穷大的整数。

## 语法

`public static decimal Floor(decimal d);`

## 参数

`d`：该参数指定要四舍五入的小数。

## 返回值

如果 `d` 有小数部分，则小于 `d` 的下一个整数；如果 `d` 没有小数部分，则 `d` 不变返回。请注意，该方法返回 `decimal` 类型的整数值。

## 示例

下面的程序说明了 `Decimal.Floor(Decimal)` 方法的使用：

### 例 1

```cs
// C# program to demonstrate the
// Decimal.Floor(Decimal) Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {

// Declaring the decimal variable
        Decimal a = 4.01m;

// finding the floor of the Decimal value
        // using floor() method;
        Decimal value = Decimal.Floor(a);

// Display the Floor
        Console.WriteLine("Floor Value is : {0}",
                                    value);
    }
}
```

**输出：**

```cs
Floor Value is : 4
```

### 例 2

```cs
// C# program to demonstrate the
// Decimal.Floor(Decimal) Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {

// Declaring the decimal variable
        Decimal a = -5.03m;

// finding the floor of the Decimal value
        // using floor() method;
        Decimal value = Decimal.Floor(a);

// Display the Floor
        Console.WriteLine("Floor Value is : {0}",
                                    value);
    }
}
```

**输出：**

```cs
Floor Value is : -6
```

### 例 3

```cs
// C# program to demonstrate the
// Decimal.Floor(Decimal) Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {

// Declaring the decimal variable
        Decimal a = 2.00m;

// finding the floor of
        // the Decimal value
        // using floor() method;
        Decimal value = Decimal.Floor(a);

// Display the Floor
        Console.WriteLine("Floor Value is : {0}",
                                    value);
    }
}
```

**输出：**

```cs
Floor Value is : 2
```