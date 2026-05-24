# C# | BitConverter 类

> 原文:[https://www.geeksforgeeks.org/c-sharp-bitconverter-class/](https://www.geeksforgeeks.org/c-sharp-bitconverter-class/)

BitConverter 类的用途是将基本数据类型转换为字节数组，将字节数组转换为基本数据类型。该类在`System` 命名空间下定义。此类提供不同类型的方法来执行转换。基本上，一个字节被定义为一个 8 位无符号整数。这个类有助于操纵值类型的基本形式，如一系列字节。这是在静态方法的帮助下完成的。BitConverter 类的静态方法用于将每个基元类型转换为字节数组或从字节数组转换出来。

**字段:**

*   **IslitleEndian**:这表示在这种计算机体系结构中数据存储的字节顺序(“字符顺序”)。

#### 方法

| 方法 | 描述 |
| **[双 to T64 位(双)](https://www.geeksforgeeks.org/c-sharp-bitconverter-doubletoint64bits-method/)** | 将指定的双精度浮点数转换为 64 位有符号整数。 |
| **位元组()** | 将指定的数据转换为字节数组。 |
| **int 32 bitstosing()** | 将指定的 32 位有符号整数转换为单精度浮点数。 |
| **[int 64 bitstodouble(Int64)](https://www.geeksforgeeks.org/c-sharp-bitconverter-int64bitstodouble-method/)** | 将指定的 64 位有符号整数转换为双精度浮点数。 |
| **单身形 32 位()** | 将指定的单精度浮点数转换为 32 位有符号整数。 |
| **[【tobooean(字节[]，Int32)](https://www.geeksforgeeks.org/c-sharp-bitconverter-toboolean-method/)** | 返回从字节数组中指定位置的字节转换而来的布尔值。 |
| [火炬(字节[]，int 32)](https://www.geeksforgeeks.org/c-sharp-bitconverter-tochar-method/)T3] | 返回从字节数组中指定位置的两个字节转换而来的 Unicode 字符。 |
| **[【todouble(字节[]，Int32)](https://www.geeksforgeeks.org/c-sharp-bitconverter-todouble-method/)** | 返回从字节数组中指定位置的八个字节转换而来的双精度浮点数。 |
| **[【Tet 16(字节[]，Int32)](https://www.geeksforgeeks.org/c-sharp-bitconverter-toint16-method/)** | 返回从字节数组中指定位置的两个字节转换而来的 16 位有符号整数。 |
| **[【Tet 32(字节[]，Int32)](https://www.geeksforgeeks.org/c-sharp-bitconverter-toint32-method/)** | 返回从字节数组中指定位置的四个字节转换而来的 32 位有符号整数。 |
| **[tot 64(字节[]，Int32)](https://www.geeksforgeeks.org/c-sharp-bitconverter-toint64-method/)** | 返回从字节数组中指定位置的八个字节转换而来的 64 位有符号整数。 |
| **[ToSingle(Byte[]，Int32)](https://www.geeksforgeeks.org/c-sharp-bitconverter-tosingle-method/)** | 返回从字节数组中指定位置的四个字节转换而来的单精度浮点数。 |
| **[ToString()](https://www.geeksforgeeks.org/c-sharp-bitconverter-tostringbyte-method/)** | 将指定字节数组中每个元素的数值转换为其等效的十六进制字符串表示形式。 |
| **[ToUInt16（字节[]， Int32）](https://www.geeksforgeeks.org/c-sharp-bitconverter-touint16-method/)** | 返回从字节数组中指定位置的两个字节转换而来的 16 位无符号整数。 |
| **[ToUInt32（字节[]， Int32）](https://www.geeksforgeeks.org/c-sharp-bitconverter-touint32-method/)** | 返回从字节数组中指定位置的四个字节转换而来的 32 位无符号整数。 |
| **[ToUInt64（字节[]， Int32）](https://www.geeksforgeeks.org/c-sharp-bitconverter-touint64-method/)** | 返回从字节数组中指定位置的八个字节转换而来的 64 位无符号整数。 |

**例 1:**

```cs
// C# program to illustrate the
// use of GetBytes(Int64) method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating and initializing an array
        long[] ele = {0, long.MaxValue, long.MinValue,
                         1000000000000000, -100000000, 
                       0xDDDDDDDDD, -0xAAAAAAAAAAAA };

        // Display the elements
        Console.WriteLine("Elements are:");
        foreach(long i in ele)
        {
            Console.WriteLine(i);
        }

        foreach(var num in ele)
        {

            // Get the specified 64-bit signed
            // integer value as an array of bytes.
            // using GetBytes(Int64) method
            byte[] BArr = BitConverter.GetBytes(num);

            // Display the elements
            Console.WriteLine("Element: {0}", 
                BitConverter.ToString(BArr));
        }
    }
}
```

**输出:**

```cs
Elements are:
0
9223372036854775807
-9223372036854775808
1000000000000000
-100000000
59556879837
-187649984473770
Element: 00-00-00-00-00-00-00-00
Element: FF-FF-FF-FF-FF-FF-FF-7F
Element: 00-00-00-00-00-00-00-80
Element: 00-80-C6-A4-7E-8D-03-00
Element: 00-1F-0A-FA-FF-FF-FF-FF
Element: DD-DD-DD-DD-0D-00-00-00
Element: 56-55-55-55-55-55-FF-FF

```

**例 2:**

```cs
// C# program to illustrate the
// use of Int64BitsToDouble(Int64)
// method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        long ele = 0xFFFFFFFFFFFFFFF;

        // Converts the given 64-bit signed
        // integer to a double-precision 
        // floating point number using the 
        // Int64BitsToDouble(Int64) method
        double R = BitConverter.Int64BitsToDouble(ele);

        // Display the element
        Console.WriteLine("Converted Element is : {0}", R);
    }
}
```

**输出:**

```cs
Converted Element is : 1.28822975391943E-231
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . bit converter？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter?view=netframework-4.7.2)