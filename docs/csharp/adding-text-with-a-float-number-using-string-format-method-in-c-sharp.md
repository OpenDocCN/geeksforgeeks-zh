# 使用字符串添加带浮点数的文本。C# 中的 Format()方法

> 原文:[https://www . geesforgeks . org/add-text-with-float-number-use-string-format-method-in-c-sharp/](https://www.geeksforgeeks.org/adding-text-with-a-float-number-using-string-format-method-in-c-sharp/)

这里的任务是使用**字符串添加带有浮点数**的文本 **T** 。Format()** 方法。**

**示例:**

> **输入:** F = 12.3，T =【ABC】
> T3】输出: 12abc.abc3
> 
> **输入:** F = 0.0，T =【极客】
> T3】输出:极客 0.0 极客

可以使用**字符串将文本 **T** 添加到浮点数 **F** 中。格式()**方法如下:

*   仅在浮点数 **F.** 的**整数部分**的左侧添加文本 **T**
*   仅在浮点数**的**整数部分**的右侧添加文本 **T****
*   仅在浮点数 **F.** 的**小数部分**的左侧添加文本 **T**
*   仅在浮点数**的**小数部分**的右侧添加文本 **T****
*   将文字 **T** 添加到浮点数**f**的**小数点**两侧
*   将文本 **T** 添加到浮点数**f**的两侧

以下是以上不同方式的实现:

**示例 1:** 仅在浮点数 **F.** 的**组成部分**的左侧添加文本 **T**

## C#

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

**输出:**

```cs
abc12.3

```

**示例 2:** 仅在浮点数 **F.** 的**组成部分**的右侧添加文本 **T**

## C#

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

**输出:**

```cs
12abc.3

```

**示例 3:** 仅在浮点数 **F.** 的**小数部分**的左侧添加文本 **T**

## C#

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

**输出:**

```cs
12.abc3

```

**示例 4:** 仅在浮点数 **F.** 的**小数部分**的右侧添加文本 **T**

## C#

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

**输出:**

```cs
12.3abc

```

**示例 5:** 在浮点数 **F.** 的**小数点**两侧添加文本 **T**

## C#

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

**输出:**

```cs
12abc.abc3

```

**示例 6:** 在浮点数**的两侧添加文本 **T****

## C#

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

**输出:**

```cs
abc12.3abc

```