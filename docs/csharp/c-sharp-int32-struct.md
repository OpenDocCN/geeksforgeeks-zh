# C# | Int32 Struct

> 原文:[https://www.geeksforgeeks.org/c-sharp-int32-struct/](https://www.geeksforgeeks.org/c-sharp-int32-struct/)

在 C# 中，Int32 Struct 表示从范围 **-2，147，483，648 到+2，147，483，647** 开始的 32 位有符号整数(也称为 **int** 数据类型)。它还提供了不同类型的方法来执行各种操作。你可以进行加法、减法、乘法等数学运算。在 Int32 类型上。它支持“与”、“或”、“异或”等按位运算。它完全支持标准和自定义数字格式字符串。可以调用[转换](https://www.geeksforgeeks.org/c-sharp-convert-class/)和[数学类](https://www.geeksforgeeks.org/c-sharp-math-class/)的方法对 Int32 值进行运算。Int32 结构继承了继承[对象类](https://www.geeksforgeeks.org/c-sharp-object-class/)的 ValueType 类。

#### 菲尔茨

| 菲尔茨 | 描述 |
| **[MaxValue](https://www.geeksforgeeks.org/int32-maxvalue-field-in-c-sharp-with-examples/)** | 该字段用于表示一个 Int32 的最大可能值。该字段是常量。 |
| **[MinValue](https://www.geeksforgeeks.org/int32-minvalue-field-in-c-sharp-with-examples/)** | 此字段用于表示 Int32 的最小可能值。该字段是常量。 |

**例:**

```cs
// C# program to illustrate the 
// MaxValue and MinValue field
using System;

class GFG {

    // Main method
    static public void Main()
    {
        Int32 var1 = 34;
        Int32 var2 = 30;
        Int32 var3 = 59;

        // Get the Maximum and Minimum value 
        // of Int32 type Using MaxValue and 
        // MinValue field
        Console.WriteLine("Value 1: {0}", var1);
        Console.WriteLine("Value 2: {0}", var2);
        Console.WriteLine("Value 3: {0}", var3);

        Console.WriteLine("Maximum Value: {0}",
                               Int32.MaxValue);

        Console.WriteLine("Minimum Value: {0}",
                               Int32.MinValue);
    }
}
```

**输出:**

```cs
Value 1: 34
Value 2: 30
Value 3: 59
Maximum Value: 2147483647
Minimum Value: -2147483648

```

#### 方法

| 方法 | 描述 |
| **[【比较】()](https://www.geeksforgeeks.org/int32-compareto-method-in-c-sharp-with-examples/)** | 此方法用于将此实例与指定的对象或 Int32 进行比较，并返回其相对值的指示。 |
| **[Equals()](https://www.geeksforgeeks.org/int32-equals-method-in-c-sharp-with-examples/)** | 此方法用于返回一个值，该值指示此实例是否等于指定对象或 Int32。 |
| **[GetHashCode()](https://www.geeksforgeeks.org/int32-gethashcode-method-in-c-sharp-with-examples/)** | 此方法用于返回此实例的哈希代码。 |
| **[GetTypeCode()](https://www.geeksforgeeks.org/int32-gettypecode-method-in-c-sharp-with-examples/)** | 此方法用于返回值类型为 Int32 的 TypeCode。 |
| **Parse()** | 此方法用于将数字的字符串表示形式转换为其 32 位有符号整数等效形式。 |
| **[to string()](https://www.geeksforgeeks.org/c-sharp-int32-tostring-method-set-1/)** | 此方法用于将此实例的数值转换为其等效的字符串表示形式。 |
| **TryParse()** | 此方法用于将数字的字符串表示形式转换为其 32 位有符号整数的等效形式。返回值指示操作是否成功。 |

**例 1:**

```cs
// C# program to demonstrate the 
// Int32.Equals(Object) Method 
using System; 
using System.Globalization; 

class GFG { 

    // Main Method 
    public static void Main() 
    { 
        // Declaring and initializing value1 
        int value1 = 70; 

        // Declaring and initializing value2 
        object value2 = 89; 

        // using Equals(object) method 
        bool status = value1.Equals(value2); 

        // checking the status 
        if (status) 
            Console.WriteLine("{0} is equal to {1}", 
                                value1, value2); 
        else
            Console.WriteLine("{0} is not equal to {1}", 
                            value1, value2); 
    } 
} 
```

**输出:**

```cs
70 is not equal to 89

```