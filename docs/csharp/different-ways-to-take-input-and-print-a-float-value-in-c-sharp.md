# 在 C# 中获取输入和打印浮点值的不同方式

> 原文:[https://www . geeksforgeeks . org/不同的方式获取输入并打印 c-sharp 中的浮点值/](https://www.geeksforgeeks.org/different-ways-to-take-input-and-print-a-float-value-in-c-sharp/)

在 [C# ](https://www.geeksforgeeks.org/csharp-programming-language/) 中，我们知道**控制台。ReadLine()** 方法用于从标准输出设备读取字符串。如果默认情况下该值不是字符串类型，则该值被转换为浮点类型。有不同的方法可以将输入转换为浮点值。以下方法可用于此目的:

*   **单身。解析()方法**
*   **浮动。解析()方法**
*   **转换。ToSingle()方法**

## **单身。解析()方法**

**单身。Parse()方法** 用于将给定的字符串值转换为浮点值。该方法包括以下内容:

*   **单** 就是一个班。
*   **解析()** 是其法。

**语法:**

```cs
float_value = Single.Parse(Console.ReadLine());

```

**示例:**使用 Single 输入浮点值。解析()方法

## C#

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

**控制台输入:**

```cs
12.34

```

**输出:**

```cs
Value = 12.34

```

## **浮动。解析()方法**

**浮动。Parse()方法** 用于将给定的字符串值转换为浮点值。该方法包括以下内容:

*   **浮** 是 **单** 类的别名。
*   **解析()** 是其法。

**语法:**

```cs
float_value = float.Parse(Console.ReadLine());

```

**示例:**使用 float 输入浮点值。解析()方法

## C#

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

**控制台输入:**

```cs
12.34

```

**输出:**

```cs
Value = 12.34

```

## **转换。ToSingle()方法**

**转换。ToSingle()方法** 用于将给定对象转换为浮点值。该方法包括以下内容:

*   **转换** 就是一个班。
*   **【to single()】**是其法。

**语法:**

```cs
float_value = Convert.ToSingle(Console.ReadLine());

```

**示例:**使用转换输入浮点值。ToSingle()方法

## C#

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

**控制台输入:**

```cs
12.34

```

**输出:**

```cs
Value = 12.34

```