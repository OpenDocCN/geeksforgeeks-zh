# C# 中 byte 和 sbyte 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-byte-and-sbyte-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-byte-and-sbyte-in-c-sharp/)

在 [C#](https://www.geeksforgeeks.org/csharp-programming-language/) 中，一个单字节用于存储 8 位值。[`byte`](https://www.geeksforgeeks.org/byte-struct-in-c-sharp/) 和 [`sbyte`](https://www.geeksforgeeks.org/c-sharp-sbyte-struct-fields/) 是用于数据的字节类型。

## byte

此结构用于表示 **8 位无符号**整数。`byte` 是不可变的值类型，范围从 0 到 255。

**例：**

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

**输出：**

```cs
Minimum value of byte: 0
Maximum value of byte: 255
```

## sbyte

此结构用于表示 **8 位有符号**整数。`sbyte` 代表数值范围从 -128 到 +127 的整数。

**例：**

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

**输出：**

```cs
Minimum value of sbyte: -128
Maximum value of sbyte: 127
```

## byte 和 sbyte 的区别

| 序号 | byte | sbyte |
| :--- | :--- | :--- |
| **1.** | `byte` 用于表示 8 位无符号整数 | `sbyte` 用于表示 8 位有符号整数 |
| **2.** | `byte` 代表无符号字节。 | `sbyte` 代表有符号字节。 |
| **3.** | 只能存储正数字节。 | 可以存储负数字节和正数字节。 |
| **4.** | 占用内存 8 位空间。 | 在内存中也占用 8 位空间。 |
| **5.** | `byte` 的范围是从 0 到 255。 | `sbyte` 范围从 -128 到 127 |
| **6.** | 声明 `byte` 的语法：<br>`byte variable_name;` | 声明 `sbyte` 的语法：<br>`sbyte variable_name;` |