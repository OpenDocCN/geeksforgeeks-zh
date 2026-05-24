# C# 中的类型系统统一。NET

> 原文:[https://www . geesforgeks . org/type-system-union-in-c-sharp-net/](https://www.geeksforgeeks.org/type-system-unification-in-c-sharp-net/)

C# 中的类型系统统一意味着 C# 中的所有数据类型都直接或间接继承自`object`类。或者你可以说所有类型都被认为是对象。在 C# 中，基元类型被称为值类型，基本上是结构。在内部，结构和`class`继承了`object`类。这就是为什么所有类型都被间接认为是对象，这个术语被称为“统一”类型系统统一。

**示例:**所有预定义的类型(如`short`、`int` `long` 等。)是结构。以下是预定义的类型及其等效的结构:

| 预定义类型 | 等效结构 |
| --- | --- |
| `short` | [`System.Int16`](https://www.geeksforgeeks.org/c-sharp-int16-struct/) |
| `int` | [`System.Int32`](https://www.geeksforgeeks.org/c-sharp-int32-struct/) |
| `long` | [`System.Int64`](https://www.geeksforgeeks.org/c-sharp-int-64-struct/) |
| `ushort` | [`System.UInt16`](https://www.geeksforgeeks.org/c-sharp-uint16-struct/) |
| `uint` | [`System.UInt32`](https://www.geeksforgeeks.org/c-sharp-uint32-struct/) |
| `ulong` | [`System.UInt64`](https://www.geeksforgeeks.org/c-sharp-uint64-struct/) |
| `byte` | `System.Byte` |
| `sbyte` | `System.SByte` |
| `bool` | `System.Boolean` |
| `char` | `System.Char` |
| `float` | `System.Single` |
| `double` | `System.Double` |
| `decimal` | `System.Decimal` |

**示例:**在下面的程序中，值数据类型(如`int`、`char`、`bool`)被用作对象，因为类型系统与返回表示该特定对象的字符串的方法`ToString()`相统一。

```cs
// C# implementation of Type System Unification
using System;

class GFG {

    // Main Method
    public static void Main(string[] args)
    {
        // Value data types
        int i = 1;
        char c = 'A';
        bool b = true;

        Console.WriteLine(i.ToString());
        Console.WriteLine(c.ToString());
        Console.WriteLine(b.ToString());
    }
}
```

**Output:**

```cs
1
A
True
```

## 装箱和拆箱

类型系统统一支持装箱和取消装箱，因为任何值数据类型都可以被视为对象。所以，当一个值类型的数据如`int`、`char`、`bool` 等。被转换成一个对象类型，这就是所谓的装箱。相反，当对象类型转换回数据类型时，称为取消装箱。

**装箱:**`int`、`char`、`bool` 等数值数据类型。在装箱中隐式转换为`object`类型。首先，分配一个`object`类型，然后将值数据类型中的值复制到`object`类型中。

**示例:**

```cs
// C# implementation of Boxing
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // int value data type
        int val = 8;

        // boxing
        object obj = val;

        System.Console.WriteLine("val = {0}", val);
        System.Console.WriteLine("obj = {0}", obj);
    }
}
```

**Output:**

```cs
val = 8
obj = 8
```

**取消装箱:**一个`object`类型被转换为一个值类型数据，如`int`、`char`、`bool` 等。显式取消装箱。首先，检查`object`类型是否是值数据类型的装箱值。如果是，则`object`类型中的值被复制出来。

**示例:**

```cs
// C# implementation of Unboxing
using System;

class GFG {

    // Main Method
    static public void Main()
    {
        // int value data type
        int val1 = 8;

        // boxing
        object obj = val1;

        // unboxing
        int val2 = (int)obj;

        Console.WriteLine("val1 = " + val1);
        Console.WriteLine("obj = " + obj);
        Console.WriteLine("val2 = " + val2);
    }
}
```

**Output:**

```cs
val1 = 8
obj = 8
val2 = 8
```

**类型系统统一的好处:**类型系统统一非常有用，因为它提供了数据类型作为值数据类型或对象类型的双重好处。值数据类型可以在需要时使用，如果需要，可以使用装箱将其转换为对象类型，因为类型系统统一的固有特性。