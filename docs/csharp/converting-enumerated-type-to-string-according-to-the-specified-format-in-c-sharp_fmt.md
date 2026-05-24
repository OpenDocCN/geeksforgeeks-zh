# 根据 C# 中指定的格式将枚举类型转换为字符串

> 原文：[https://www.geeksforgeeks.org/converting-enumerated-type-to-string-according-to-the-specified-format-in-c-sharp/](https://www.geeksforgeeks.org/converting-enumerated-type-to-string-according-to-the-specified-format-in-c-sharp/)

`Enum.Format(Type, Object, String)` 方法用于将指定枚举类型的指定值按照指定格式转换为其等价的字符串表示形式。

## 语法：

```cs
public static string Format (Type enumType, object value, string format);
```

## 参数：

*   `enumType`：是要转换的值的枚举类型。
*   `value`：是要转换的值。
*   `format`：是要使用的输出格式。

## 返回：

该方法返回值的字符串表示形式。

## 异常：

*   `ArgumentNullException`：如果 `enumType`、`value` 或 `format` 参数为空。
*   `ArgumentException`：如果 `enumType` 参数不是枚举类型，或者该值来自与枚举类型不同的枚举，或者该值类型不是枚举类型的基础类型。
*   `FormatException`：如果 `format` 参数包含无效值。
*   `InvalidOperationException`：如果 `format` 等于“X”，但枚举类型未知。

下面的程序说明了上述方法的使用。

## 例 1：

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
        Console.WriteLine("The hex value of my Animal  is {0}.",
                          Enum.Format(typeof(Animals), fav, "x"));
    }
}
```

## Output：

```cs
My favorite Animal is Cat.
The value of my favorite Animal is 1.
The hex value of my Animal  is 00000001.
```

## 例 2：

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

## 运行时错误：

> 未处理异常:
> System.ArgumentNullException: 值不能为空。
> 参数名称: format

**注意：** 以下是格式参数的一些有效值。

*   “D”或“d”：表示十进制形式的 `value` 参数。
*   “X”或“x”：表示十六进制格式的 `value` 参数。它不会导致“0x”。

## 参考：

*   [https://docs.microsoft.com/en-us/dotnet/api/system.enum.format?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.enum.format?view=netframework-4.8)