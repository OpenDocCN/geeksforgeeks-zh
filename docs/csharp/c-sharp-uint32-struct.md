# C# | UInt32 Struct

> 原文:[https://www.geeksforgeeks.org/c-sharp-uint32-struct/](https://www.geeksforgeeks.org/c-sharp-uint32-struct/)

在 C# 中，UInt32 结构用于表示从 0 到 4，294，967，295 范围内的 32 位无符号整数(也称为 **uint** 数据类型)。它还提供了不同类型的方法来比较这种类型的实例，将实例的值转换为其字符串表示形式，将数字的字符串表示形式转换为这种类型的实例，等等。该结构在**系统**命名空间下定义。UInt32 结构继承了继承[对象类](https://www.geeksforgeeks.org/c-sharp-object-class/)的值类型类。

#### 菲尔茨

| 田 | 描述 |
| [最大值](https://www.geeksforgeeks.org/uint32-maxvalue-field-in-c-sharp-with-examples/) | 代表 UInt32 的最大可能值。该字段是常量。 |
| **[最小值](https://www.geeksforgeeks.org/uint32-minvalue-field-in-c-sharp-with-examples/)** | 表示 UInt32 的最小可能值。该字段是常量。 |

**示例:**

```cs
// C# program to illustrate the 
// fields of UInt32 struct
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Unsigned 32-bit integer
        uint val = 4294967295;

        // Checking the unsigned integer
        if (val.Equals(UInt32.MinValue)) 
        {
            Console.WriteLine("Equal to MinValue!");
        }

        else if (val.Equals(UInt32.MaxValue)) 
        {
            Console.WriteLine("Equal to MaxValue!");
        }
        else {
            Console.WriteLine("Not Equal!");
        }
    }
}
```

**Output:**

```cs
Equal to MaxValue!

```

#### 方法

| 方法 | 描述 |
| **[【共享()](https://www.geeksforgeeks.org/uint32-compareto-method-in-c-sharp-with-examples/)** | 将当前实例与指定的对象或 UInt32 进行比较，并返回其相对值的指示。 |
| **[等于()](https://www.geeksforgeeks.org/uint32-equals-method-in-c-sharp-with-examples/)** | 返回一个值，该值显示当前实例是否等于指定的对象或 UInt32。 |
| **[GethashCode（）](https://www.geeksforgeeks.org/uint32-gethashcode-method-in-c-sharp-with-examples/)** | 返回此实例的哈希代码。 |
| **[【gettype code()](https://www.geeksforgeeks.org/uint32-gettypecode-method-in-c-sharp-with-examples/)** | 返回值类型 UInt32 的类型代码。 |
| **解析()** | 将数字的字符串表示形式转换为其等效的 32 位无符号整数。 |
| **[ToString()](https://www.geeksforgeeks.org/uint32-tostring-method-in-c-sharp-with-examples-set-1/)** | 将此实例的数值转换为其等效的字符串表示形式。 |
| **尽力剖析()** | 尝试将数字的字符串表示形式转换为等效的 32 位无符号整数。返回值指示转换是成功还是失败。 |

**示例:**

```cs
// C# program to illustrate how to get the
// hash code of the 32-bit Unsigned integer
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // UInt32 variable
        uint myval = 33453242;

        // Get the hash code
        // Using GetHashCode Method
        int res = myval.GetHashCode();
        Console.WriteLine("The hash code of myval is: {0}", res);
    }
}
```

**Output:**

```cs
The hash code of myval is: 33453242

```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.uint32?视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.uint32?view=netframework-4.8)