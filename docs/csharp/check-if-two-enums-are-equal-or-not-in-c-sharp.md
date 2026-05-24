# 检查 C# 中两个枚举是否相等

> 原文:[https://www . geesforgeks . org/check-if-two-enum-is-equal-or-not-in-c-sharp/](https://www.geeksforgeeks.org/check-if-two-enums-are-equal-or-not-in-c-sharp/)

**枚举。Equals(Object)方法**用于检查当前实例是否等于指定对象。该方法覆盖*值类型。Equals(Object)* 定义如何计算枚举成员的相等性。

**语法:**

```cs
public override bool Equals (object obj);
```

这里，obj 是要与当前实例进行比较的对象，或者为 null。

**返回:**如果对象是与当前实例相同类型和相同基础值的枚举值，则该方法返回 *true* ，否则返回 *false* 。

**例:**

```cs
// C# program to illustrate the
// Enum.Equals(Object) Method
using System;

class GFG {

    // taking two enums
    enum Clothes { Jeans,
                   Shirt }
    ;
    enum Colors { Blue,
                  Black }
    ;

    // Main Method
    public static void Main()
    {

        Clothes cl1 = Clothes.Jeans;
        Clothes cl2 = Clothes.Shirt;

        Colors c1 = Colors.Blue;
        Colors c2 = Colors.Black;
        Colors c3 = Colors.Blue;

        // using the method
        Console.WriteLine(c1.Equals(c3));
        Console.WriteLine(c1.Equals(c2));
        Console.WriteLine(cl1.Equals(cl2));
    }
}
```

**输出:**

```cs
True
False
False

```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。枚举。平等？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.enum.equals?view=netframework-4.8)