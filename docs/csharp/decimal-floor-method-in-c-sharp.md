# 小数。C# 中的 Floor()方法

> 原文:[https://www . geesforgeks . org/decimal-floor-method in-c-sharp/](https://www.geeksforgeeks.org/decimal-floor-method-in-c-sharp/)

此方法用于将小数舍入到最接近负无穷大的整数。

> **语法:**公共静态十进制 Floor(十进制 d)；
> 
> **参数:**
> **d** :该参数指定要四舍五入的小数。
> 
> **返回值**:如果 d 有小数部分，则小于 *d* **或** *d* 的下一个整数十进制数没有小数部分， *d* 不变返回。请注意，该方法返回十进制类型的整数值。

下面的程序说明了**小数的使用。楼层(十进制)法:**

**例 1:**

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

**Output:**

```cs
Floor Value is : 4

```

**例 2:**

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

**Output:**

```cs
Floor Value is : -6

```

**例 3:**

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

**Output:**

```cs
Floor Value is : 2

```