# String.Format 方法在 C# 中的使用示例（第三部分）

> 原文：[https://www.geeksforgeeks.org/string-format-method-in-c-sharp-with-examples-set-3/](https://www.geeksforgeeks.org/string-format-method-in-c-sharp-with-examples-set-3/)

在 C# 中，`Format()` 是 `String` 类的一个方法。此方法用于将指定字符串中的一个或多个格式项替换为指定对象的字符串表示。换句话说，这个方法是用来将变量、对象或表达式的值插入到另一个字符串中。

这个方法可以通过传递不同类型的参数来重载。`Format()` 方法的重载列表中共有 **8** 个方法，其中 6 个在 **Set-1** 和 **Set-2** 中讨论，其余在本文中讨论。

1.  `String.Format(String, Object)` 方法
2.  `String.Format(String, Object[])` 方法
3.  `String.Format(IFormatProvider, String, Object)` 方法
4.  `String.Format(IFormatProvider, String, Object[])` 方法
5.  `String.Format(String, Object, Object)` 方法
6.  `String.Format(String, Object, Object, Object)` 方法
7.  `String.Format(IFormatProvider, String, Object, Object)` 方法
8.  `String.Format(IFormatProvider, String, Object, Object, Object)` 方法

## `String.Format(IFormatProvider, String, Object, Object)` 方法

此方法用于将字符串中的格式项替换为两个指定对象的字符串表示形式。参数提供区域性特定的格式信息。

### 语法

```cs
public static string Format (IFormatProvider provider, string format, object arg0, object arg1);
```

### 参数

该方法有以下参数：

> `provider`：该参数是提供区域性特定格式信息的对象。
> `format`：此参数为所需的复合格式字符串。
> `arg0`：该参数是第一个要格式化的对象。
> `arg1`：该参数是第二个要格式化的对象。

### 返回值

此方法返回字符串。它是 `format` 的副本，其中格式项被 `arg0` 和 `arg1` 的字符串表示所取代。

### 示例

```cs
// C# program to illustrate the 
// String.Format(IFormatProvider,
// String, Object, Object) Method

using System;

public class GFG
{
    // Main method
    public static void Main(string[] args)
    {

        string formatString =
        "Value: {0,0}\n" +
        "NOT of Value: {1,0}";

        int value1 = 169;

        System.Globalization.CultureInfo culture =
        new System.Globalization.CultureInfo("es-ES");

        string result = String.Format
        (culture, formatString, value1, ~value1);

        Console.WriteLine(result);
    }
}
```

### 输出

```cs
Value: 169
NOT of Value: -170
```

## `String.Format(IFormatProvider, String, Object, Object, Object)` 方法

此方法用于将字符串中的格式项替换为三个指定对象的字符串表示形式。参数提供区域性特定的格式信息。

### 语法

```cs
public static string Format (IFormatProvider provider, string format, object arg0, object arg1, object arg2);
```

### 参数

该方法有以下参数：

> `provider`：该参数是提供特定于区域性的格式信息的对象。
> `format`：此参数为所需的复合格式字符串。
> `arg0`：该参数是第一个要格式化的对象。
> `arg1`：该参数是第二个要格式化的对象。
> `arg2`：该参数是第三个要格式化的对象。

### 返回值

此方法返回字符串。它是 `format` 的副本，其中格式项被 `arg0`、`arg1` 和 `arg2` 的字符串表示所取代。

### 示例

```cs
// C# program to illustrate the 
// String.Format(IFormatProvider,
// String, Object, Object, Object) Method

using System;

public class GFG
{
    // Main method
    public static void Main(string[] args)
    {

        string formatString =
        "Value 1: {0,0}\n" +
        "Value 2: {1,0}\n" +
        "Sum of Values : {2,0}";

        int value1 = 169;
        int value2 = 961;

        System.Globalization.CultureInfo culture =
        new System.Globalization.CultureInfo("es-ES");

        string result = String.Format
        (culture, formatString, value1, value2,
        value1 + value2);

        Console.WriteLine(result);
    }
}
```

### 输出

```cs
Value 1: 169
Value 2: 961
Sum of Values : 1130
```