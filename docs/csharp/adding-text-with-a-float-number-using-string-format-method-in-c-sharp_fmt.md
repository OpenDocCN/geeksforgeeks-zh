# 使用字符串添加带浮点数的文本。C# 中的 `Format()` 方法

> 原文：[https://www.geeksforgeeks.org/adding-text-with-a-float-number-using-string-format-method-in-c-sharp/](https://www.geeksforgeeks.org/adding-text-with-a-float-number-using-string-format-method-in-c-sharp/)

这里的任务是使用 `String.Format()` 方法将文本 `T` 添加到浮点数 `F` 中。

**示例：**

> **输入：** `F = 12.3`，`T = "abc"`
> **输出：** `12abc.abc3`
>
> **输入：** `F = 0.0`，`T = "geeks"`
> **输出：** `geeks 0.0 geeks`

可以使用 `String.Format()` 方法将文本 `T` 添加到浮点数 `F` 中，方式如下：

*   仅在浮点数 `F` 的整数部分的左侧添加文本 `T`
*   仅在浮点数 `F` 的整数部分的右侧添加文本 `T`
*   仅在浮点数 `F` 的小数部分的左侧添加文本 `T`
*   仅在浮点数 `F` 的小数部分的右侧添加文本 `T`
*   将文本 `T` 添加到浮点数 `F` 的小数点两侧
*   将文本 `T` 添加到浮点数 `F` 的两侧

以下是以上不同方式的实现：

## 示例 1：仅在浮点数 `F` 的整数部分的左侧添加文本 `T`

```cs
// C# program to add text T
// only to left of integral
// part of a float number F.

using System;

public class GFG{

    // function to add text at
    // left of integral part
    // of a float number.
    static string Add_text(float F, string T)
    {
        // string format
        string s = "{0:";
        s += T;
        s += "0.0}";

        // use of String.Format() method
        return String.Format(s, F);
    }

    // Main Method
    static void Main(string[] args)
    {
        float F = 12.3f;
        string T = "abc";

        //function calling
        string str = Add_text(F, T);

        // print the added text float number
        Console.WriteLine(str);
    }
}
```

**输出：**

```cs
abc12.3
```

## 示例 2：仅在浮点数 `F` 的整数部分的右侧添加文本 `T`

```cs
// C# program to add text T
// only to right of integral
// part of a float number F.

using System;

public class GFG{

    // function to add text at
    // right of integral part
    // of a float number.
    static string Add_text(float F, string T)
    {
        // string format
        string s = "{0:0";
        s += T;
        s += ".0}";

        // use of String.Format() method
        return String.Format(s, F);
    }

    // Main Method
    static void Main(string[] args)
    {
        float F = 12.3f;
        string T = "abc";

        // function calling
        string str = Add_text(F, T);

        // print the added text float number
        Console.WriteLine(str);
    }
}
```

**输出：**

```cs
12abc.3
```

## 示例 3：仅在浮点数 `F` 的小数部分的左侧添加文本 `T`

```cs
// C# program to add text T
// only to left of fractional
// part of a float number F.

using System;

public class GFG{

    // function to add text at
    // left of fractional part
    // of a float number F.
    static string Add_text(float F, string T)
    {
        // string format
        string s = "{0:0.";
        s += T;
        s += "0}";

        // use of String.Format() method
        return String.Format(s, F);
    }

    // Main Method
    static void Main(string[] args)
    {
        float F = 12.3f;
        string T = "abc";

        // function calling
        string str = Add_text(F, T);

        // print the added text
        // float number
        Console.WriteLine(str);
    }
}
```

**输出：**

```cs
12.abc3
```

## 示例 4：仅在浮点数 `F` 的小数部分的右侧添加文本 `T`

```cs
// C# program to add text T
// only to right of fractional
// part of a float number F.

using System;

public class GFG{

    // function to add text at
    // right of fractional part
    // of a float number F.
    static string Add_text(float F, string T)
    {
        // string format
        string s = "{0:0.0";
        s += T;
        s += "}";

        // use of String.Format() method
        return String.Format(s, F);
    }

    // Main Method
    static void Main(string[] args)
    {
        float F = 12.3f;
        string T = "abc";

        // function calling
        string str = Add_text(F, T);

        // print the added text float number
        Console.WriteLine(str);
    }
}
```

**输出：**

```cs
12.3abc
```

## 示例 5：在浮点数 `F` 的小数点两侧添加文本 `T`

```cs
// C# program to add text
// to both side of decimal
// point of a float number

using System;

public class GFG{

    // function to add text at
    // both side of decimal
    // point of a float number
    static string Add_text(float F, string T)
    {
        // string format
        string s = "{0:0";
        s += T;
        s += ".";
        s += T;
        s += "0}";

        // use of String.Format() method
        return String.Format(s, F);
    }

    // Main Method
    static void Main(string[] args)
    {
        float F = 12.3f;
        string T = "abc";

        // function calling
        string str = Add_text(F, T);

        // print the added text float number
        Console.WriteLine(str);
    }
}
```

**输出：**

```cs
12abc.abc3
```

## 示例 6：在浮点数 `F` 的两侧添加文本 `T`

```cs
// C# program to add text
// to both side of a float number

using System;

public class GFG{

    // function to add text at
    // both side of a float number
    static string Add_text(float F, string T)
    {
        // string format
        string s = "{0:";
        s += T;
        s += "0.0";
        s += T;
        s += "}";

        // use of String.Format() method
        return String.Format(s, F);
    }

    // Main Method
    static void Main(string[] args)
    {
        float F = 12.3f;
        string T = "abc";

        // function calling
        string str = Add_text(F, T);

        // print the added text float number
        Console.WriteLine(str);
    }
}
```

**输出：**

```cs
abc12.3abc
```