# c# 中字节和字节的区别

> 原文:[https://www . geesforgeks . org/c-sharp 中字节与字节的差异/](https://www.geeksforgeeks.org/difference-between-byte-and-sbyte-in-c-sharp/)

在 [**C#**](https://www.geeksforgeeks.org/csharp-programming-language/) 中，一个单字节用于存储 8 位值。 [**字节**](https://www.geeksforgeeks.org/byte-struct-in-c-sharp/) 和 [**字节**](https://www.geeksforgeeks.org/c-sharp-sbyte-struct-fields/)b0 用于数据的字节类型。

**字节** **:** 此结构用于表示 ***8 位无符号*** 整数。字节是不可变的值类型，字节的范围从 0 到 255。

**例:**

## C#

```cs
// C# program to demonstrate 
// the byte Struct Fields

using System;
using System.Text;

public class GFG{

    // Main Method
    static void Main(string[] args)
    {

        // printing minimum & maximum values
        Console.WriteLine("Minimum value of byte: " + byte.MinValue);
        Console.WriteLine("Maximum value of byte: " + byte.MaxValue);
    }
}
```

**输出:**

```cs
Minimum value of byte: 0
Maximum value of byte: 255

```

**字节** **:** 此结构用于表示 ***8 位有符号*** 整数。sbyte 代表数值范围从 -128 到+127 的整数。

**例:**

## C#

```cs
// C# program to demonstrate 
// the sbyte Struct Fields

using System;
using System.Text;

public class GFG{

    // Main Method
    static void Main(string[] args)
    {

        // printing minimum & maximum values
        Console.WriteLine("Minimum value of sbyte: " + sbyte.MinValue);
        Console.WriteLine("Maximum value of sbyte: " + sbyte.MaxValue);
    }
}
```

**输出:**

```cs
Minimum value of sbyte: -128
Maximum value of sbyte: 127

```

**c# 中字节和字节的区别**

<figure class="table">

| **先生** | 字节 | 变变 |
| **1。**T3】 | 字节用于表示 8 位无符号整数 | 字节 用于表示 8 位有符号整数 |
| **2。**T3】 | 字节 代表无符号字节。 | sbyte 代表无符号字节。 |
| **3。**T3】 | 只能存储正字节。 | 可以存储负字节和正字节。 |
| **4。**T3】 | 占用内存 8 位空间。 | 在内存中也占用 8 位空间。 |
| **5。**T3】 | T 他的字节范围是从 0 到 255。 | 字节范围从 -128 到 127 |
| **6。**T3】 | 声明字节的语法:

```cs
***byte variable_name;***  
```

 | 声明字节的语法:

```cs
***sbyte variable_name;***  
```

 |

</figure>