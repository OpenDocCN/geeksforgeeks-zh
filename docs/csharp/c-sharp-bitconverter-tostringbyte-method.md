# C# | BitConverter。ToString(Byte[])方法

> 原文:[https://www . geesforgeks . org/c-sharp-bit converter-tostringbyte-method/](https://www.geeksforgeeks.org/c-sharp-bitconverter-tostringbyte-method/)

此方法用于将指定字节数组中每个元素的数值转换为其等效的十六进制字符串表示形式。

**语法:**

```cs
public static string ToString (byte[] value);
```

这里，*值*是一个字节数组。

**返回值:**该方法返回一串由连字符分隔的十六进制对，其中每对代表*值*中的对应元素。例如“6E-1D-9A-00”。

**异常:**如果字节数组或者你可以说*值*为空，这个方法抛出 **ArgumentNullException** 。

以下程序说明了**位转换器的使用。ToString(Byte[])** 方法:

**例 1:**

```cs
// C# program to demonstrate
// BitConverter.ToString(Byte[]);
// Method
using System;

public class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Define an array of byte values.
            byte[] array1 = {0, 1, 2, 4, 8, 16,
                             32, 64, 128, 255};

            // Display the values of the myArr.
            Console.Write("Initial Array: ");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(array1);

            // Getting hex string of byte values
            string value = BitConverter.ToString(array1);

            // Display the string
            Console.Write("string: ");
            Console.Write("{0}", value);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining the method
    // PrintIndexAndValues
    public static void PrintIndexAndValues(byte[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {

            Console.Write("{0} ", myArr[i]);
        }
        Console.WriteLine();
        Console.WriteLine();
    }
}
```

**Output:**

```cs
Initial Array: 0 1 2 4 8 16 32 64 128 255 

string: 00-01-02-04-08-10-20-40-80-FF

```

**示例 2:** 适用于*参数异常*

```cs
// C# program to demonstrate
// BitConverter.ToString(Byte[]);
// Method
using System;

public class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Define an array of byte values.
            byte[] array1 = null;

            // Getting hex string of byte values
            string value = BitConverter.ToString(array1);

            // Display the string
            Console.Write("string: ");
            Console.Write("{0}", value);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Exception Thrown: System.ArgumentNullException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . bit converter . tostring？view = net framework-4 . 7 . 2 # System _ BitConverter _ ToString _ System _ Byte _ _](https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.tostring?view=netframework-4.7.2# System_BitConverter_ToString_System_Byte___)