# C# Convert 类

> 原文：[https://www.geeksforgeeks.org/c-sharp-convert-class/](https://www.geeksforgeeks.org/c-sharp-convert-class/)

`Convert` 类提供了不同的方法来将一个基本数据类型转换为另一个基本数据类型。`Convert` 类支持的基本类型有布尔值、字符、字节、`Int16`、`Int32`、`Int64`、`UInt16`、`UInt32`、`UInt64`、`Single`、`Double`、`Decimal`、`DateTime` 和 `String`。它还提供了支持其他转换的方法。该类在 `System` 命名空间下定义。

## Convert 类特性

*   它提供了用于将每个基类型转换为其他基类型的方法。
*   它提供了用于将整数值转换为非十进制字符串表示形式的方法，还将表示非十进制数字的字符串转换为整数值。
*   它提供了用于将任何自定义对象转换为任何基类型的方法。
*   它提供了一组支持 base64 编码的方法。
*   如果缩小转换导致数据丢失，可能会发生 `OverflowException`。

## 字段

*   `DBNull`：它是一个常数，代表缺少数据的数据库列，即数据库空值。

## 方法

| 方法 | 描述 |
| :--- | :--- |
| `ChangeType()` | 它返回一个指定类型的对象，该对象的值相当于一个指定的对象。 |
| `FromBase64CharArray(Char[], Int32, Int32)` | 将 Unicode 字符数组的子集转换为等效的 8 位无符号整数数组，Unicode 字符数组将二进制数据编码为 64 位基数。参数指定输入数组中的子集和要转换的元素数量。 |
| `FromBase64String(String)` | 将指定的字符串转换为等效的 8 位无符号整数数组，该字符串将二进制数据编码为 64 位基数。 |
| `GetTypeCode(Object)` | 返回指定对象的类型代码。 |
| `IsDBNull(Object)` | 返回指定对象是否为 `DBNull` 类型的指示。 |
| `ToBase64CharArray(Byte[], Int32, Int32, Char[], Int32)` | 将 8 位无符号整数数组的子集转换为以 64 位为基数编码的 `Unicode` 字符数组的等效子集。 |
| `ToBase64String(Byte[])` | 将 8 位无符号整数数组的值转换为其等效的字符串表示形式，该字符串表示形式以 64 位为基数进行编码。 |
| `ToBoolean(String)` | 将指定的值转换为等效的布尔值。 |
| `ToByte(String)` | 将指定的值转换为 8 位无符号整数。 |
| `ToChar(String)` | 将指定的值转换为 `Unicode` 字符。 |
| `ToDateTime(String)` | 将指定的值转换为 `DateTime` 值。 |
| `ToDecimal(String)` | 将指定值转换为十进制数。 |
| `ToDouble(String)` | 将指定值转换为双精度浮点数。 |
| `ToInt16(String)` | 将指定的值转换为 16 位有符号整数。 |
| `ToInt32(String)` | 将指定的值转换为 32 位有符号整数。 |
| `ToInt64(String)` | 将指定值转换为 64 位有符号整数。 |
| `ToSByte(String)` | 将指定值转换为 8 位有符号整数。 |
| `ToSingle(String)` | 将指定值转换为单精度浮点数。 |
| `ToUInt16(String)` | 将指定的值转换为 16 位无符号整数。 |
| `ToUInt32(String)` | 将指定的值转换为 32 位无符号整数。 |
| `ToUInt64(String)` | 将指定值转换为 64 位无符号整数。 |

## 例 1

```cs
// C# program to illustrate the
// use of ToBase64String(Byte[])
// method
using System;

class GFG {

    // Main method
    static public void Main()
    {
        // Creating and initializing 
        // Byte array
        byte[] B = { 2, 4, 8, 16, 32 };

        // Display the elements
        Console.WriteLine("BArray is :{0}",
                  BitConverter.ToString(B));

        Console.WriteLine();

        // Convert the given array
        // into a base 64 string.
        String str = Convert.ToBase64String(B);

        // Display the string
        Console.WriteLine("Base 64 string is :{0}", str);
    }
}
```

**输出:**

```cs
BArray is :02-04-08-10-20

Base 64 string is :AgQIECA=
```

## 例 2

```cs
// C# program to illustrate the
// use of ToDecimal(Int16) method
using System;

class GFG {

    // Main method
    static public void Main()
    {
        // Creating and initializing 
        // an array
        short[] ele = {1, Int16.MinValue,
                         0, 106, -32 };
        decimal sol;

        // Display the elements
        Console.WriteLine("Elements are:");
        foreach(short i in ele)
        {
            Console.WriteLine(i);
        }

        foreach(short num in ele)
        {
            // Convert the given Int16
            // values into decimal values
            // using ToDecimal(Int16) method
            sol = Convert.ToDecimal(num);

            // Display the elements
            Console.WriteLine("convert value is: {0}", sol);
        }
    }
}
```

**输出:**

```cs
Elements are:
1
-32768
0
106
-32
convert value is: 1
convert value is: -32768
convert value is: 0
convert value is: 106
convert value is: -32
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.convert?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.convert?view=netframework-4.7.2)