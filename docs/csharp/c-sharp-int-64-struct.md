# C# | Int 64 Struct

> 原文:[https://www.geeksforgeeks.org/c-sharp-int-64-struct/](https://www.geeksforgeeks.org/c-sharp-int-64-struct/)

在 C# 中，Int64 Struct 用于表示从范围 **-9，223，372，036，854，775，808 到+9，223，372，036，775，807** 的 64 位有符号整数(也称为**长的**数据类型)。它提供不同类型的方法来执行各种操作。用户可以进行加法、减法、乘法等数学运算。在 Int64 类型上。它支持“与”、“或”、“异或”等按位运算。它完全支持标准和自定义数字格式字符串。用户也可以调用[转换](https://www.geeksforgeeks.org/c-sharp-convert-class/)和[数学类](https://www.geeksforgeeks.org/c-sharp-math-class/)的方法对 Int64 值进行运算。Int64 结构继承了继承[对象类](https://www.geeksforgeeks.org/c-sharp-object-class/)的 ValueType 类。

#### 菲尔茨

| 菲尔茨 | 描述 |
| **[MaxValue](https://www.geeksforgeeks.org/int64-maxvalue-field-in-c-sharp-with-examples/)** | 此字段用于表示一个 Int64 的最大可能值。该字段是常量。 |
| **[MinValue](https://www.geeksforgeeks.org/int64-minvalue-field-in-c-sharp-with-examples/)** | 此字段用于表示 Int64 的最小可能值。该字段是常量。 |

**例 1:**

```cs
// C# program to illustrate the 
// MaxValue and MinValue field
using System;

class GFG {

    // Main method
    static public void Main()
    {
        Int64 var1 = 89;
        Int64 var2 = 50;
        Int64 var3 = 10;

        // Get the Maximum and Minimum value of 
        // Int64 type Using MaxValue and 
        // MinValue field
        Console.WriteLine("Value 1: {0}", var1);
        Console.WriteLine("Value 2: {0}", var2);
        Console.WriteLine("Value 3: {0}", var3);

        Console.WriteLine("Maximum Value: {0}",
                               Int64.MaxValue);

        Console.WriteLine("Minimum Value: {0}",
                               Int64.MinValue);
    }
}
```

**输出:**

```cs
Value 1: 89
Value 2: 50
Value 3: 10
Maximum Value: 9223372036854775807
Minimum Value: -9223372036854775808

```

#### 方法

| 方法 | 描述 |
| **[【比较】()](https://www.geeksforgeeks.org/int64-compareto-method-in-c-sharp-with-examples/)** | 此方法用于将此实例与指定的对象或 Int64 进行比较，并返回其相对值的指示。 |
| **[Equals()](https://www.geeksforgeeks.org/int64-equals-method-in-c-sharp-with-examples/)** | 此方法用于返回一个值，该值指示此实例是否等于指定对象或 Int64。 |
| **[GetHashCode()](https://www.geeksforgeeks.org/int64-gethashcode-method-in-c-sharp-with-examples/)** | 此方法用于返回此实例的哈希代码。 |
| **[GetTypeCode()](https://www.geeksforgeeks.org/int64-gettypecode-method-in-c-sharp-with-examples/)** | 此方法用于返回值类型为 Int64 的 TypeCode。 |
| **Parse()** | 此方法用于将数字的字符串表示形式转换为其 64 位有符号整数等效形式。 |
| **[to string()](https://www.geeksforgeeks.org/c-sharp-int64-tostring-method-set-1/)** | 此方法用于将此实例的数值转换为其等效的字符串表示形式。 |
| **TryParse()** | 此方法用于将数字的字符串表示形式转换为其 64 位有符号整数等效形式。返回值指示转换是成功还是失败。 |

**例 1:**

```cs
// C# program to demonstrate the 
// Int64.Equals(Int64) Method 
using System; 
using System.Globalization; 

class GFG { 

    // Main Method 
    public static void Main() 
    { 
        // Declaring and initializing value1 
        long value1 = 45643212342; 

        // Declaring and initializing value2 
        long value2 = 543256344233; 

        // using Equals(Int64) method 
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
45643212342 is not equal to 543256344233

```