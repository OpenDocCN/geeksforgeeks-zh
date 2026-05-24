# C# | 数据类型

> 原文: [https://www.geeksforgeeks.org/c-sharp-data-types/](https://www.geeksforgeeks.org/c-sharp-data-types/)

数据类型指定有效的 [C#](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 变量可以保存的数据类型。C# 是一种**强类型编程语言**，因为在 [C#](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 中，每种类型的数据（如整数、字符、浮点等）都是作为编程语言的一部分预定义的，为给定程序定义的所有常量或变量都必须用其中一种数据类型来描述。

## 数据类型在 C# 中主要分为三类

*   **数值数据类型**
*   **参考数据类型**
*   **指针数据类型**

### 1. 值数据类型

在 [C#](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 中，值数据类型将直接将变量值存储在内存中，它还将接受有符号和无符号文本。这些数据类型的派生类是 `System.ValueType`。以下是 [C#](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 编程语言中**不同的值数据类型**:

*   **有符号&无符号整数类型:** 有 8 种整数类型，支持 8 位、16 位、32 位和 64 位有符号或无符号形式的值。`System.Int64`、`long`、`ushort`、`uint`、`ulong`。

| 别名 | 类型名 | 类型 | 大小（位) | 范围 | 缺省值 |
| --- | --- | --- | --- | --- | --- |
| `sbyte` | `System.Sbyte` | 带符号整数 | 8 | -128 到 127 | 0 |
| `short` | `System.Int16` | 带符号整数 | 16 | -32768 到 32767 | 0 |
| `int` | `System.Int32` | 带符号整数 | 32 | -2<sup>31</sup> 至 2<sup>31</sup> -1 | 0 |
| `long` | `System.Int64` | 带符号整数 | 64 | -2<sup>63</sup> 至 2<sup>63</sup>-1 | 0L |
| `byte` | `System.Byte` | 无符号整数 | 8 | 0 到 255 | 0 |
| `ushort` | `System.UInt16` | 无符号整数 | 16 | 0 到 65535 | 0 |
| `uint` | `System.UInt32` | 无符号整数 | 32 | 0 至 2<sup>32</sup> | 0 |
| `ulong` | `System.UInt64` | 无符号整数 | 64 | 0 至 2<sup>64</sup> | 0 |

*   **浮点类型:** 包含小数点的浮点数据类型有 2 种。
    *   **`float`**: 是 **32 位单精度**浮点类型。它有 7 位数的精度。要初始化一个浮点变量，使用后缀 `f` 或 `F`。如，`float x = 3.5F`。如果后缀 `f` 或 `F` 不使用，那么它被视为 `double`。
    *   **`double`**: 是 **64 位双精度**浮点型。它有 14-15 位精度。若要初始化双精度变量，请使用后缀 `d` 或 `D`。但不一定要使用后缀，因为默认情况下，浮动数据类型是 `double` 类型。

| 别名 | 类型名 | 大小(位) | 范围(约) | 缺省值 |
| --- | --- | --- | --- | --- |
| `float` | `System.Single` | 32 | 1.5 × 10<sup>-45</sup> 至 3.4 × 10<sup>38</sup> | 0.0F |
| `double` | `System.Double` | 64 | 5.0 × 10<sup>-324</sup> 至 1.7 × 10<sup>308</sup> | 0.0D |

*   **十进制类型:** `decimal` 类型是适用于金融和货币计算的 128 位数据类型。它有 28-29 位精度。若要初始化十进制变量，请使用后缀 `m` 或 `M`。如，`decimal x = 300.5m`。如果后缀 `m` 或 `M` 不使用，那么它被视为 `double`。`System.Decimal`。

| 别名 | 类型名 | 大小（位) | 范围（约) | 缺省值 |
| --- | --- | --- | --- | --- |
| `decimal` | `System.Decimal` | 128 | 1.0 × 10<sup>-28</sup> 至 7.9228×10<sup>28</sup> | 0.0M |

*   **字符类型:** 字符类型表示一个 UTF-16 代码单元或表示 16 位 Unicode 字符。

| 别名 | 类型名 | 尺寸单位(位) | 范围 | 缺省值 |
| --- | --- | --- | --- | --- |
| `char` | `System.Char` | 16 | U+0000 至 U+ffff | '\0' |

**示例:**

```cs
// C# program to demonstrate 
// the above data types
using System;
namespace ValueTypeTest {

    class GeeksforGeeks {

        // Main function
        static void Main()
        {

            // declaring character
            char a = 'G';

            // Integer data type is generally
            // used for numeric values
            int i = 89;

            short s = 56;

            // this will give error as number
            // is larger than short range
            // short s1 = 87878787878;

            // long uses Integer values which 
            // may signed or unsigned
            long l = 4564;

            // UInt data type is generally
            // used for unsigned integer values
            uint ui = 95;

            ushort us = 76;
            // this will give error as number is
            // larger than short range

            // ulong data type is generally
            // used for unsigned integer values
            ulong ul = 3624573;

            // by default fraction value
            // is double in C#
            double d = 8.358674532;

            // for float use 'f' as suffix
            float f = 3.7330645f;

            // for float use 'm' as suffix
            decimal dec = 389.5m;

            Console.WriteLine("char: " + a);
            Console.WriteLine("integer: " + i);
            Console.WriteLine("short: " + s);
            Console.WriteLine("long: " + l);
            Console.WriteLine("float: " + f);
            Console.WriteLine("double: " + d);
            Console.WriteLine("decimal: " + dec);
            Console.WriteLine("Unsinged integer: " + ui);
            Console.WriteLine("Unsinged short: " + us);
            Console.WriteLine("Unsinged long: " + ul);
        }
    }
}
```

**输出:**

```cs
char: G
integer: 89
short: 56
long: 4564
float: 3.733064
double: 8.358674532
decimal: 389.5
Unsinged integer: 95
Unsinged short: 76
Unsinged long: 3624573
```

**示例:**

```cs
// C# program to demonstrate the Sbyte
// signed integral data type
using System;
namespace ValueTypeTest {

    class GeeksforGeeks {

        // Main function
        static void Main()
        {
            sbyte a = 126;

            // sbyte is 8 bit 
            // singned value
            Console.WriteLine(a);

            a++;
            Console.WriteLine(a);

            // It overflows here because
            // byte can hold values 
            // from -128 to 127
            a++;
            Console.WriteLine(a);

            // Looping back within 
            // the range
            a++;
            Console.WriteLine(a);
        }
    }
}
```

**输出:**

```cs

```

**示例:**

```cs
// C# program to demonstrate 
// the byte data type
using System;
namespace ValueTypeTest {

    class GeeksforGeeks {

        // Main function
        static void Main()
        {
            byte a = 0;

            // byte is 8 bit 
            // unsigned value
            Console.WriteLine(a);

            a++;
            Console.WriteLine(a);

            a = 254;

            // It overflows here because
            // byte can hold values from
            // 0 to 255
            a++;
            Console.WriteLine(a);

            // Looping back within the range
            a++;
            Console.WriteLine(a);
        }
    }
}
```

**输出:**

```cs

```

*   **布尔类型:** 它必须被赋予 `true` 或 `false` 值。`bool` 类型的值不会被隐式或显式地（使用强制转换）转换为任何其他类型。但程序员可以轻松编写转换代码。

| 别名 | 类型名 | 价值观念 |
| --- | --- | --- |
| `bool` | `System.Boolean` | `true`/`false` |

**示例:**

```cs
// C# program to demonstrate the
// boolean data type
using System;
namespace ValueTypeTest {

    class GeeksforGeeks {

        // Main function
        static void Main() 
        {

            // boolean data type
            bool b = true;     
            if (b == true)
                Console.WriteLine("Hi Geek");
        } 
    }
}
```

**输出:**

```cs
Hi Geek
```

### 2. 引用数据类型

引用数据类型将包含变量值的内存地址，因为引用类型不会将变量值直接存储在内存中。内置引用类型有 `string`、`object`。

*   **`string`**: 代表一系列 Unicode 字符，其类型名为 `System.String`。所以，`string` 和 `String` 是等价的。
    **例:**

```cs
string s1 = "hello"; // creating through string keyword  
String s2 = "welcome"; // creating through String class
```

*   **`object`**: 在 C# 中，所有类型，预定义的和用户定义的，引用类型和值类型，都直接或间接继承自 `Object`。所以基本上它是 C# 中所有数据类型的基类。在赋值之前，它需要类型转换。当值类型的变量转换为 `object` 时，这称为**装箱（boxing）**。当 `object` 类型的变量转换为值类型时，这称为**拆箱（unboxing）**。其类型名是 `System.Object`。

**示例:**

```cs
// C# program to demonstrate 
// the Reference data types
using System;
namespace ValueTypeTest {

    class GeeksforGeeks {

        // Main Function
        static void Main() 
        {
```

### 3. Pointer Data Type
指针数据类型将包含变量值的内存地址。要获取指针详情，我们有两个符号：`ampersand (&)` 和 `asterisk (*)`。

`ampersand (&)`：被称为地址运算符，用于确定变量的地址。
`asterisk (*)`：也称为间接运算符，用于访问地址对应的值。

**语法：**
```cs
type* identifier;
```

**示例：**
```cs
int* p1, p;   // Valid syntax
int *p1, *p;   // Invalid
```

**示例：**
```cs
// Note: This program will not work on
// online compiler
// Error: Unsafe code requires the `unsafe' 
// command line option to be specified
// For its solution:
// Go to your project properties page and
// check under Build the checkbox Allow
// unsafe code.
using System;
namespace Pointerprogram {

    class GFG {

        // Main function
        static void Main()
        {
            unsafe
            {
                // declare variable
                int n = 10;

                // store variable n address 
                // location in pointer variable p
                int* p = &n;
                Console.WriteLine("Value :{0}", n);
                Console.WriteLine("Address :{0}", (int)p);
            }
        }
    }
}
```