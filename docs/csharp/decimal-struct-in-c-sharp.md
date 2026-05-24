# c# 中的十进制结构

> 原文:[https://www.geeksforgeeks.org/decimal-struct-in-c-sharp/](https://www.geeksforgeeks.org/decimal-struct-in-c-sharp/)

在 C# 中，Decimal Struct 类用于表示十进制浮点数。十进制数的范围是+79，228，162，514，264，337，593，543，950，335 到-79，228，162，514，264，337，593，543，950，335。由于其范围广泛，它通常用于需要大量有效整数和小数位数且无舍入误差的金融计算。您还可以对十进制类型执行数学运算，如加法、减法、除法、乘法等。

#### 构造器

| 构造器 | 描述 |
| **十进制(双精度)** | 将 Decimal 的新实例初始化为指定的双精度浮点数的值。 |
| **十进制（Int32）** | 将 Decimal 的新实例初始化为指定的 32 位有符号整数的值。 |
| **十进制（Int32[]）** | 将 Decimal 的新实例初始化为以二进制表示并包含在指定数组中的十进制值。 |
| **十进制（Int64）** | 将 Decimal 的新实例初始化为指定的 64 位有符号整数的值。 |
| **十进制(单)** | 将 Decimal 的新实例初始化为指定的单精度浮点数的值。 |
| **十进制 （UInt32）** | 将 Decimal 的新实例初始化为指定的 32 位无符号整数的值。 |
| **十进制 （UInt64）** | 将 Decimal 的新实例初始化为指定的 64 位无符号整数的值。 |
| **十进制（Int32， Int32， Int32， Boolean， Byte）** | 从指定实例组成部分的参数初始化 Decimal 的新实例。 |

#### 菲尔茨

| 田 | 描述 |
| **最大值** | 表示十进制的最大可能值。该字段是常量和只读的。 |
| 小写 | 表示负数 1(-1)。 |
| **最小值** | 表示小数的最小可能值。该字段是常量和只读的。 |
| **一** | 代表数字一(1)。 |
| **零** | 表示数字零(0)。 |

**示例:**

```cs
// C# program to illustrate the
// use of MaxValue and MinValue field
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // Display the Minimum and Maximum values
        Console.WriteLine("Display Maximum value "+ 
              "of Decimal: {0}", Decimal.MaxValue);

        Console.WriteLine("Display Minimum value of "+
                    "Decimal: {0}", Decimal.MinValue);
    }
}
```

**Output:**

```cs
Display Maximum value of Decimal: 79228162514264337593543950335
Display Minimum value of Decimal: -79228162514264337593543950335

```

#### 方法

| 方法 | 描述 |
| **[加(小数，小数)](https://www.geeksforgeeks.org/decimal-add-method-in-c-sharp/)** | 添加两个指定的十进制值。 |
| **[【上限(小数)](https://www.geeksforgeeks.org/decimal-ceiling-method-in-c-sharp/)** | 返回大于或等于指定十进制数的最小整数值。 |
| **[【比较(小数，小数)](https://www.geeksforgeeks.org/decimal-compare-method-in-c-sharp/)** | 比较两个指定的十进制值。 |
| **CompareTo()** | 将此实例与指定的对象或小数进行比较，并返回它们的相对值的指示。 |
| **[【除(十进制，十进制)](https://www.geeksforgeeks.org/decimal-divide-method-in-c-sharp/)** | 将两个指定的十进制值相除。 |
| **等于()** | 返回一个值，该值指示 Decimal 的两个实例是否表示相同的值。 |
| **[【楼层(小数)](https://www.geeksforgeeks.org/decimal-floor-method-in-c-sharp/)** | 将指定的十进制数向负无穷大舍入到最接近的整数。 |
| **FromOACurrency(Int64)** | 将包含 OLE 自动化货币值的指定 64 位有符号整数转换为等效的十进制值。

 |
| **获取比特（十进制）** | 将指定的 Decimal 实例的值转换为其等效的二进制表示形式。 |
| **GetHashCode（）** | 返回此实例的哈希代码。 |
| **GetTypeCode()** | 返回十进制值类型的类型代码。 |
| **[【乘法(十进制，十进制)](https://www.geeksforgeeks.org/decimal-multiply-method-in-c-sharp/)** | 将两个指定的十进制值相乘。 |
| **[【取反(小数)](https://www.geeksforgeeks.org/decimal-negate-method-in-c-sharp/)** | 返回指定的十进制值乘以负一的结果。 |
| **解析()** | 将数字的字符串表示形式转换为其十进制等价形式。 |
| **[【余数(小数，小数)](https://www.geeksforgeeks.org/decimal-remainder-method-in-c-sharp/)** | 在除以两个十进制值后计算余数。 |
| **Round()** | 将值舍入到最接近的整数或指定的小数位数。 |
| **[【减法(小数，小数)](https://www.geeksforgeeks.org/decimal-subtract-method-in-c-sharp/)** | 从另一个指定的十进制值中减去一个。 |
| **[【tobyte(十进制)](https://www.geeksforgeeks.org/decimal-tobyte-method-in-c-sharp/)** | 将指定的十进制值转换为等效的 8 位无符号整数。 |
| **[【todouble(decimal)](https://www.geeksforgeeks.org/decimal-todouble-method-in-c-sharp/)** | 将指定的十进制值转换为等效的双精度浮点数。 |
| **[ToInt16（十进制）](https://www.geeksforgeeks.org/decimal-toint16-method-in-c-sharp/)** | 将指定的十进制值转换为等效的 16 位有符号整数。 |
| **[ToInt32（十进制）](https://www.geeksforgeeks.org/decimal-toint32-method-in-c-sharp/)** | 将指定的十进制值转换为等效的 32 位有符号整数。 |
| **[ToInt64（十进制）](https://www.geeksforgeeks.org/decimal-toint64-method-in-c-sharp/)** | 将指定的十进制值转换为等效的 64 位有符号整数。 |
| **到当前值(十进制)** | 将指定的十进制值转换为等效的 OLE 自动化货币值，该值包含在 64 位有符号整数中。 |
| **[to byte(十进制)](https://www.geeksforgeeks.org/decimal-tosbyte-method-in-c-sharp/)** | 将指定的十进制值转换为等效的 8 位有符号整数。 |
| **[【to single(十进制)](https://www.geeksforgeeks.org/decimal-tosingle-method-in-c-sharp/)** | 将指定的十进制值转换为等效的单精度浮点数。 |
| **ToString()** | 将此实例的数值转换为其等效的字符串表示形式。 |
| **TouInt16（十进制）** | 将指定的十进制值转换为等效的 16 位无符号整数。 |
| **TouInt32（十进制）** | 将指定的十进制值转换为等效的 32 位无符号整数。 |
| **TouInt64（十进制）** | 将指定的十进制值转换为等效的 64 位无符号整数。 |
| **截断(十进制)** | 返回指定小数的整数位数；任何小数位数都将被丢弃。 |
| **尽力剖析()** | 将数字的字符串表示形式转换为其十进制等价形式。返回值指示转换是成功还是失败。 |

**示例:**

```cs
// C# program to illustrate the
// use of Add(Decimal, Decimal)
// method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Addition of two Decimal values
        // Using Add() method
        Decimal val1 = 349;
        Decimal val2 = 590;
        Decimal result;
        result = Decimal.Add(val1, val2);

        // Display the result
        Console.WriteLine("Addition is: {0}", result);
    }
}
```

**Output:**

```cs
Addition is: 939

```

#### 经营者

| 操作员 | 描述 |
| **加法(十进制，十进制)** | 添加两个指定的十进制值。 |
| **减量(十进制)** | 将十进制操作数减 1。 |
| **除法(十进制，十进制)** | 将两个指定的十进制值相除。 |
| **等式(十进制，十进制)** | 返回一个值，该值指示两个十进制值是否相等。 |
| **显式(单到十进制)** | 定义单精度浮点数到十进制数的显式转换。 |
| **显式(双精度到十进制)** | 定义双精度浮点数到十进制数的显式转换。 |
| **显式(十进制至整数 32)** | 定义小数到 32 位无符号整数的显式转换。 |
| **显式(十进制至十六进制)** | 定义十进制到 16 位无符号整数的显式转换。 |
| **显式(十进制到单个)** | 定义小数到单精度浮点数的显式转换。 |
| **显式(十进制到字节)** | 定义小数到 8 位有符号整数的显式转换。 |
| **显式(十进制到 UInt64)** | 定义小数到 64 位无符号整数的显式转换。 |
| **显式(十进制到 Int32)** | 定义小数到 32 位有符号整数的显式转换。 |
| **显式(十进制到 Int16)** | 定义十进制到 16 位有符号整数的显式转换。 |
| **显式(十进制到双精度)** | 定义小数到双精度浮点数的显式转换。 |
| **显式(十进制到字符)** | 定义十进制到 Unicode 字符的显式转换。 |
| **显式(十进制到字节)** | 定义小数到 8 位无符号整数的显式转换。 |
| **显式(十进制到 Int64)** | 定义小数到 64 位有符号整数的显式转换。 |
| **大整数(十进制，十进制)** | 返回一个值，该值指示指定的小数是否大于另一个指定的小数。 |
| **大整数(十进制，十进制)** | 返回一个值，该值指示指定的小数是否大于或等于另一个指定的小数。 |
| **隐式(UInt32 至十进制)** | 定义 32 位无符号整数到十进制数的隐式转换。 |
| **隐式(UInt16 至十进制)** | 定义 16 位无符号整数到十进制数的隐式转换。 |
| **隐式(字节到十进制)** | 定义 8 位有符号整数到十进制的隐式转换。 |
| **隐式(Int64 至十进制)** | 定义 64 位有符号整数到十进制的隐式转换。 |
| **隐式(字节到十进制)** | 定义 8 位无符号整数到十进制数的隐式转换。 |
| **隐式(Int16 至十进制)** | 定义 16 位有符号整数到十进制的隐式转换。 |
| **隐式(字符到十进制)** | 定义 Unicode 字符到十进制的隐式转换。 |
| **隐式(UInt64 至十进制)** | 定义 64 位无符号整数到十进制数的隐式转换。 |
| **隐式(Int32 至 Decimal)** | 定义 32 位有符号整数到十进制的隐式转换。 |
| **增量(小数)** | 将十进制操作数增加 1。 |
| **不等式(十进制，十进制)** | 返回一个值，该值指示两个十进制对象是否具有不同的值。 |
| **莱辛(十进制，十进制)** | 返回一个值，该值指示指定的小数是否小于另一个指定的小数。 |
| **lesthanorequal(十进制，十进制)** | 返回一个值，该值指示指定的小数是否小于或等于另一个指定的小数。 |
| **模数(十进制，十进制)** | 返回两个指定的十进制值相除后的余数。 |
| **乘法(十进制，十进制)** | 将两个指定的十进制值相乘。 |
| **减法(十进制，十进制)** | 减去两个指定的十进制值。 |
| **一元连接(小数)** | 否定指定的十进制操作数的值。 |
| **UnaryPlus(小数)** | 返回十进制操作数的值(操作数的符号不变)。 |

**示例:**

```cs
// C# program to illustrate the
// use of Decrement and Increment
// operator
using System;

class GFG {

    static public void Main()
    {
        Decimal myval1 = 1000;
        Decimal myval2 = 10000;

        // Using Decrement operator we decrease myval1 by 1
        Console.WriteLine("My value 1 is: {0}", myval1);
        Console.WriteLine("Decrease myval1 by 1:{0}", --myval1);
        Console.WriteLine();

        // Using Increment operator we increase myval2 by 1
        Console.WriteLine("My value 2 is: {0}", myval2);
        Console.WriteLine("Increase myval2 by 1:{0}", ++myval2);
    }
}
```

**Output:**

```cs
My value 1 is: 1000
Decrease myval1 by 1:999

My value 2 is: 10000
Increase myval2 by 1:10001

```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.decimal?视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal?view=netframework-4.7.2)