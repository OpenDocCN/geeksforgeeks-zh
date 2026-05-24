# 在 C# 中获取输入和打印浮点值的不同方式

> 原文：[https://www.geeksforgeeks.org/different-ways-to-take-input-and-print-a-float-value-in-c-sharp/](https://www.geeksforgeeks.org/different-ways-to-take-input-and-print-a-float-value-in-c-sharp/)

在 [C#](https://www.geeksforgeeks.org/csharp-programming-language/) 中，我们知道`Console.ReadLine()`方法用于从标准输出设备读取字符串。如果默认情况下该值不是字符串类型，则该值被转换为浮点类型。有不同的方法可以将输入转换为浮点值。以下方法可用于此目的：

*   `Single.Parse()`方法
*   `float.Parse()`方法
*   `Convert.ToSingle()`方法

## `Single.Parse()`方法

`Single.Parse()`方法用于将给定的字符串值转换为浮点值。该方法包括以下内容：

*   `Single`就是一个类。
*   `Parse()`是其方法。

**语法：**

```cs
float_value = Single.Parse(Console.ReadLine());
```

**示例：** 使用`Single.Parse()`方法输入浮点值

```cs
// C# program to Take input 
// of a float value using 
// Single.Parse() Method

using System;
using System.Text;

public class GFG{

    // Main Method
    static void Main(string[] args)
    {
        //declaring a float variables
        float value = 0.0f;

        // use of Single.Parse() Method
        value = Single.Parse(Console.ReadLine());

        //printing the value
        Console.WriteLine("Value = {0}", value);
    }
}
```

**控制台输入：**

```cs
12.34
```

**输出：**

```cs
Value = 12.34
```

## `float.Parse()`方法

`float.Parse()`方法用于将给定的字符串值转换为浮点值。该方法包括以下内容：

*   `float`是`Single`类的别名。
*   `Parse()`是其方法。

**语法：**

```cs
float_value = float.Parse(Console.ReadLine());
```

**示例：** 使用`float.Parse()`方法输入浮点值

```cs
// C# program to Take input 
// of a float value using 
// float.Parse() Method

using System;
using System.Text;

public class GFG{

    // Main Method
    static void Main(string[] args)
    {
        // declaring a float variables
        float value = 0.0f;

        // use of float.Parse() Method
        value = float.Parse(Console.ReadLine());

        // printing the value
        Console.WriteLine("Value = {0}", value);
    }
}
```

**控制台输入：**

```cs
12.34
```

**输出：**

```cs
Value = 12.34
```

## `Convert.ToSingle()`方法

`Convert.ToSingle()`方法用于将给定对象转换为浮点值。该方法包括以下内容：

*   `Convert`就是一个类。
*   `ToSingle()`是其方法。

**语法：**

```cs
float_value = Convert.ToSingle(Console.ReadLine());
```

**示例：** 使用`Convert.ToSingle()`方法输入浮点值

```cs
// C# program to Take input 
// of a float value using 
// Convert.ToSingle() method

using System;
using System.Text;

public class GFG{

    // Main Method
    static void Main(string[] args)
    {
        // declaring a float variable
        float value = 0.0f;

        // use of Convert.ToSingle() Method
        value = Convert.ToSingle(Console.ReadLine());

        // printing the value
        Console.WriteLine("Value = {0}", value);
    }
}
```

**控制台输入：**

```cs
12.34
```

**输出：**

```cs
Value = 12.34
```