# 如何在 C# 中获取枚举的 hashcode？

> 原文:[https://www . geesforgeks . org/how-to-get-hashcode-for-enum-in-c-sharp/](https://www.geeksforgeeks.org/how-to-get-the-hashcode-for-enum-in-c-sharp/)

**枚举。GetHashCode 方法**用于获取当前实例的值的 HashCode。该方法继承自[对象类](https://www.geeksforgeeks.org/c-sharp-object-class/)。

**语法:**

```cs
public override int GetHashCode ();
```

**返回:**该方法返回 32 位有符号整数哈希码。

**例:**

```cs
// C# program to illustrate the
// Enum.GetHashCode() Method
using System;

class GFG {

    enum Color {Blue, Black};

    // Main Method
    public static void Main(String[] args)
    {
        Color c1 = Color.Blue;
        Console.Write("HashCode of Enum Constant " + c1 + " : ");

        // Using the GetHashCode() Method
        Console.WriteLine(c1.GetHashCode());

        Color c2 = Color.Black;
        Console.Write("Hashcode of Enum Constant " + c2 + " : ");

        // Using the GetHashCode Method
        Console.WriteLine(c2.GetHashCode());
    }
}
```

**输出:**

```cs
HashCode of Enum Constant Blue : 0
Hashcode of Enum Constant Black : 1

```

**参考:**

*   [https://docs。微软。com/en-us/dotnet/API/system。枚举。gethashcode？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.enum.gethashcode?view=netframework-4.8)