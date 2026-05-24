# C# | Char.TryParse() 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-char-tryparse-method/](https://www.geeksforgeeks.org/c-sharp-char-tryparse-method/)

在 C# 中，`Char.TryParse()` 是 `Char` 类方法，用于将给定字符串的值转换为其等效的 Unicode 字符。其性能优于 `Char.Parse()` 方法。

## 语法

```cs
public static bool TryParse(string str, out char result)
```

## 参数

- **str**: 是 `System.String` 类型参数，可以包含单个字符或 `null` 值。
- **result**: 这是一个未初始化的参数，用于在转换成功时存储等效的 Unicode 字符，如果转换失败则存储未定义的值。此参数的类型是 `System.Char`。

## 返回类型

方法返回 `true`，如果成功转换字符串，否则返回 `false`。所以这种方法的返回类型是 `System.Boolean`。

## 注意

当 `str` 为 `null` 或 `空` 或 `长度` 不等于 1 时则转换失败。

## 示例 1

下面是演示 `Char.TryParse()` 方法用法的程序。

```cs
// C# program to illustrate the
// Char.TryParse () Method
using System;

class GFG {

// Main Method
    static public void Main()
    {

// Declaration of data type
        bool result;
        Char value;

// Input Capital letter A
        result = Char.TryParse("A", out value);

// Display boolean type result
        Console.WriteLine(result);
        Console.WriteLine(value.ToString());

// Input Capital letter Z
        result = Char.TryParse("Z", out value);

// Display boolean type result
        Console.WriteLine(result);
        Console.WriteLine(value.ToString());

// Input Symbol letter
        result = Char.TryParse("{content}quot;", out value);

// Display boolean type result
        Console.WriteLine(result);
        Console.WriteLine(value.ToString());

// Input number
        result = Char.TryParse("100", out value);

// Display boolean type result
        Console.WriteLine(result);
        Console.WriteLine(value.ToString());

// Input small letter z
        result = Char.TryParse("z", out value);

// Display boolean type result
        Console.WriteLine(result);
        Console.WriteLine(value.ToString());
    }
}
```

## 输出

```cs
True
A
True
Z
True
$
False

True
z
```

## 示例 2

下面是一个演示 `Char.TryParse()` 方法在输入不是单个字符并以符号开头时使用的程序。

```cs
// C# program to illustrate the
// Char.TryParse () Method
using System;

class GFG {

// Main Method
    static public void Main()
    {

// Declaration of data type
        bool result;
        Char value;

// Input is  String return false
        result = Char.TryParse("GeeksforGeeks", out value);

// Display boolean type result
        Console.WriteLine(result);
        Console.WriteLine(value.ToString());

// Input letter start with symbol  <
        result = Char.TryParse("<N", out value);

// Display boolean type result
        Console.WriteLine(result);
        Console.WriteLine(value.ToString());
    }
}
```

## 输出

```cs
False

False
```