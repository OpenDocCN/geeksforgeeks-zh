# 根据 C# 中指定的格式将枚举类型转换为字符串

> 原文:[https://www . geesforgeks . org/converting-enumerated-type-to-string-按照 c-sharp 中指定的格式/](https://www.geeksforgeeks.org/converting-enumerated-type-to-string-according-to-the-specified-format-in-c-sharp/)

**枚举。Format(Type，Object，String)方法**用于将指定枚举类型的指定值按照指定格式转换为其等价的字符串表示形式。

**语法:**

```cs
public static string Format (Type enumType, object value, string format);
```

**参数:**

*   **枚举类型:**是要转换的值的枚举类型。
*   **值:**是要转换的值。
*   **格式:**是要使用的输出格式。

**返回:**该方法返回值的字符串表示形式。

**异常:**

*   **参数空异常:**如果*枚举类型*、*值*或*格式*参数为空。
*   **参数异常:**如果*枚举类型*参数不是枚举类型，或者该值来自与枚举类型不同的枚举，或者该值类型不是枚举类型的基础类型。
*   **格式异常:**如果*格式*参数包含无效值。
*   **无效操作异常:**如果*格式*等于“X”，但枚举类型未知。

下面的程序说明了上述方法的使用。

**例 1:**

```cs
// C# program to illustrate the
// Enum.Format(Type, Object,
// String) Method
using System;

enum Animals { Dog,
               Cat,
               Cow };

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        Animals fav = Animals.Cat;

        Console.WriteLine("My favorite Animal is {0}.", fav);

        // using the Method and here
        // "d" specify the value in
        // decimal form.
        Console.WriteLine("The value of my favorite Animal is {0}.",
                          Enum.Format(typeof(Animals), fav, "d"));

        // using the Method and here
        // "x" specify the value in
        // hexadecimal form.
        Console.WriteLine("The hex value of my Animal  is {0}.",
                          Enum.Format(typeof(Animals), fav, "x"));
    }
}
```

**Output:**

```cs
My favorite Animal is Cat.
The value of my favorite Animal is 1.
The hex value of my Animal  is 00000001.

```

**例 2:**

```cs
// C# program to illustrate the
// Enum.Format(Type, Object,
// String) Method
using System;

enum Animals { Dog,
               Cat,
               Cow };

class GFG {

    // Main Method
    public static void Main()
    {

        Animals fav = Animals.Cat;

        Console.WriteLine("My favorite Animal is {0}.", fav);

        // using the Method and format is null
        // thats why it give exception
        Console.WriteLine("The value of my favorite Animal is {0}.",
                          Enum.Format(typeof(Animals), fav, null));
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentNullException:值不能为空。
> 参数名称:格式

**注意:**以下是格式参数的一些有效值。

*   “D”或“D”:表示十进制形式的值参数。
*   “X”或“X”:表示十六进制格式的值参数。它不会导致“0x”。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . enum . format？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.enum.format?view=netframework-4.8)