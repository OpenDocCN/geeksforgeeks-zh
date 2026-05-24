# C# | UInt16 Struct

> 原文:[https://www.geeksforgeeks.org/c-sharp-uint16-struct/](https://www.geeksforgeeks.org/c-sharp-uint16-struct/)

在 C# 中，UInt16 结构用于表示 16 位无符号整数(也称为 **ushort** 数据类型)，从*范围 0 到 65535* 开始。它提供了不同类型的方法来执行各种操作，比如比较这种类型的实例，将实例的值转换成它的字符串表示，将数字的字符串表示转换成这种类型的实例，等等。该结构在**系统**命名空间下定义。UInt16 结构继承了继承[对象类](https://www.geeksforgeeks.org/c-sharp-object-class/)的值类型类。

#### 菲尔茨

| 田 | 描述 |
| [最大值](https://www.geeksforgeeks.org/uint16-maxvalue-field-in-c-sharp-with-examples/) | 代表 UInt16 的最大可能值。该字段是常量。 |
| **[最小值](https://www.geeksforgeeks.org/uint16-minvalue-field-in-c-sharp-with-examples/)** | 表示 UInt16 的最小可能值。该字段是常量。 |

**示例:**

```cs
// C# program to illustrate the 
// fields of UInt16 struct
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Unsigned 16-bit integer
        ushort val = 295;

        // Checking the unsigned integer
        if (val.Equals(UInt16.MinValue)) 
        {
            Console.WriteLine("Equal to MinValue..!");
        }

        else if (val.Equals(UInt16.MaxValue)) 
        {
            Console.WriteLine("Equal to MaxValue");
        }

        else 
        {
            Console.WriteLine("Not equal");
        }
    }
}
```

**Output:**

```cs
Not equal

```

#### 方法

| 方法 | 描述 |
| **[【共享()](https://www.geeksforgeeks.org/uint16-compareto-method-in-c-sharp-with-examples/)** | 将当前实例与指定的对象或 UInt16 进行比较，并返回其相对值的指示。 |
| **[等于()](https://www.geeksforgeeks.org/uint16-equals-method-in-c-sharp-with-examples/)** | 返回一个值，该值显示当前实例是否等于指定的对象或 UInt16。 |
| **[GethashCode（）](https://www.geeksforgeeks.org/uint16-gethashcode-method-in-c-sharp-with-examples/)** | 返回此实例的哈希代码。 |
| **[【gettype code()](https://www.geeksforgeeks.org/uint16-gettypecode-method-in-c-sharp-with-examples/)** | 返回值类型 UInt16 的类型代码。 |
| **解析()** | 将数字的字符串表示形式转换为其等效的 16 位无符号整数。 |
| **[ToString()](https://www.geeksforgeeks.org/uint16-tostring-method-in-c-sharp-with-examples-set-1/)** | 将此实例的数值转换为其等效的字符串表示形式。 |
| **尽力剖析()** | 将数字的字符串表示形式转换为其等效的 16 位无符号整数。返回值指示转换是成功还是失败。 |

**示例:**

```cs
// C# program to illustrate how to get the hash 
// code of the 16-bit Unsigned integer
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // UInt16 variable
        ulong myval = 545;

        // Get the hash code
        // Using GetHashCode Method
        int res = myval.GetHashCode();

        Console.WriteLine("The hash code of myval is: {0}", res);
    }
}
```

**Output:**

```cs
The hash code of myval is: 545

```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.uint16?视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.uint16?view=netframework-4.8)