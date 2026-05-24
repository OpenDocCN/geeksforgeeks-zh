# c# 中的字节结构

> 原文:[https://www.geeksforgeeks.org/byte-struct-in-c-sharp/](https://www.geeksforgeeks.org/byte-struct-in-c-sharp/)

在 C# 中，字节结构用于表示 8 位无符号整数。字节是不可变的值类型，字节的范围从 0 到 255。这个类允许您创建字节数据类型，并且您可以对它们执行数学和位操作，如加法、减法、乘法、除法、异或等。

#### 菲尔茨

| 田 | 描述 |
| [最大值](https://www.geeksforgeeks.org/c-sharp-byte-maxvalue-field/) | 它是字节的最大可能值。该字段是常量。 |
| **[最小值](https://www.geeksforgeeks.org/c-sharp-byte-minvalue-field/)** | 它是字节的最小可能值。该字段是常量。 |

**示例:**

```cs
// C# program to illustrate the concept
// of MaxValue and MinValue fields in Byte
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Display the minimum and
        // the maximum value of Byte
        Console.WriteLine("The minimum value "+
                 "of Byte: {0}", Byte.MinValue);

        Console.WriteLine("The maximum value "+
                 "of Byte: {0}", Byte.MaxValue);
    }
}
```

**Output:**

```cs
The minimum value of Byte: 0
The maximum value of Byte: 255

```

#### 方法

| 方法 | 描述 |
| **[【比较对象】](https://www.geeksforgeeks.org/c-sharp-byte-comparetoobject-method/)** | 将当前实例与指定对象进行比较，并返回其相对值的符号。 |
| **[比较](https://www.geeksforgeeks.org/c-sharp-byte-comparetobyte-method/)** | 将此实例与指定的 8 位无符号整数进行比较，并返回其相对值的指示。 |
| **[等于(对象)](https://www.geeksforgeeks.org/c-sharp-byte-equalsobject-method/)** | 获取一个值，该值指示当前实例是否等于指定的对象。 |
| **[等于(字节)](https://www.geeksforgeeks.org/c-sharp-byte-equalsbyte-method/)** | 返回一个值，该值指示此实例和指定的字节对象是否表示相同的值。 |
| **[GethashCode（）](https://www.geeksforgeeks.org/c-sharp-byte-gethashcode-method/)** | 返回此实例的哈希代码。 |
| **[【gettype code()](https://www.geeksforgeeks.org/c-sharp-byte-gettypecode-method/)** | 返回字节值类型的类型代码。 |
| **解析()** | 将数字的字符串表示形式转换为它的等效字节。 |
| **[ToString()](https://www.geeksforgeeks.org/c-sharp-byte-tostring-method-set-1/)** | 将当前字节对象的值转换为其等效的字符串表示形式。 |
| **尽力剖析()** | 尝试将数字的字符串表示形式转换为它的等效字节，并返回一个指示转换是否成功的值。 |

**示例:**

```cs
// C# program to illustrate the concept
// of CompareTo(Byte) method in Byte
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // val1, val2, and val3 are of byte type
        byte val1 = 32;
        byte val2 = 40;
        byte val3 = 10;

        // Display the comparison
        // Using CompareTo(Byte) method
        Console.WriteLine("Comparison 1: {0}",
                         val1.CompareTo(val2));

        Console.WriteLine("Comparison 2: {0}", 
                         val2.CompareTo(val3));

        Console.WriteLine("Comparison 3: {0}", 
                        val3.CompareTo(val3));

        Console.WriteLine("Comparison 4: {0}",
                         val1.CompareTo(val3));
    }
}
```

**Output:**

```cs
Comparison 1: -8
Comparison 2: 30
Comparison 3: 0
Comparison 4: 22

```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.byte?视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.byte?view=netframework-4.7.2)