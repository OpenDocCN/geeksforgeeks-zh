# C# | Convert.ToBase64String()方法 | Set-1

> 原文: [https://www.geeksforgeeks.org/c-sharp-convert-tobase64string-method-set-1/](https://www.geeksforgeeks.org/c-sharp-convert-tobase64string-method-set-1/)

`Convert.ToBase64String()`方法用于将8位无符号整数数组的值转换为其等效的字符串表示形式，该字符串表示形式以64位为基数进行编码。此方法的重载中有以下4种方法：

*   `ToBase64String(Byte[], Int32, Int32)`方法
*   `ToBase64String(Byte[], Int32, Int32, Base64FormattingOptions)`方法
*   `ToBase64String(Byte[], Base64FormattingOptions)`方法
*   `ToBase64String(Byte[])`方法

这里我们只讨论第一种方法。

`ToBase64String(Byte[], Int32, Int32)`方法用于将8位无符号整数数组的子集转换为其等效的字符串表示形式，该字符串表示形式用基数为64的数字进行编码。参数将子集指定为输入数组中的偏移量，以及要转换的数组中的元素数量。

## 语法:

```cs
public static string ToBase64String (byte[] inArray, int offset, int length);
```

## 参数:

*   `inArray`：是一个8位无符号整数的数组。
*   `offset`：是`inArray`的偏移。
*   `length`：是要转换的`inArray`的元素个数。

## 返回值:

该方法从位置`offset`开始，返回`inArray`中`length`个元素以64为基数的字符串表示。

## 异常:

*   `ArgumentNullException`：如果`inArray`为空。
*   `ArgumentOutOfRangeException`：如果`offset`或`length`为负，或者`offset`加上`length`大于`inArray`的长度。

以下程序说明了`Convert.ToBase64String(Byte[], Int32, Int32)`方法的使用：

## 例 1:

```cs
// C# program to demonstrate the
// Convert.ToBase64String() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // defining and initializing
            // byte1 and byte2
            byte[] byte1 = {2, 4, 6, 8, 10,
                       12, 14, 16, 18, 20};

            byte[] byte2 = {10, 20, 30, 40, 50};

            // calling get() Method
            get(byte1, "byte1");

            Console.WriteLine("");
            get(byte2, "byte2");
        }

        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(),
                        e.Message);
        }
    }

    // Defining get() method
    public static void get(byte[] bytes, string str)
    {
        Console.WriteLine("For {0}", str);

        // converting byte to base 64 string
        string val = Convert.ToBase64String(bytes,
                                 0, bytes.Length);

        // display the converted string
        Console.WriteLine("converted string: {0}", val);
    }
}
```

## 输出:

```cs
For byte1
converted string: AgQGCAoMDhASFA==

For byte2
converted string: ChQeKDI=
```

## 示例 2: 适用于`ArgumentNullException`

```cs
// C# program to demonstrate the
// Convert.ToBase64String() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // defining and initializing
            // byte1
            byte[] byte1 = {2, 4, 6, 8, 10,
                       12, 14, 16, 18, 20};

            // calling get() Method
            get(byte1, "byte1");

            Console.WriteLine("");

            // converting base 64 string 
            // to byte array
            Console.WriteLine("bye array is null");

            string val = Convert.ToBase64String(null, 0, 10);
            Console.WriteLine("Converted byte value: {0}", val);
        }

        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(),
                        e.Message);
        }
    }

    // Defining get() method
    public static void get(byte[] bytes, string str)
    {
        Console.WriteLine("For {0}", str);

        // converting byte to base 64 string
        string val = Convert.ToBase64String(bytes, 
                                 0, bytes.Length);

        // display the converted string
        Console.WriteLine("converted string: {0}", val);
    }
}
```

## 输出:

```cs
For byte1
converted string: AgQGCAoMDhASFA==

bye array is null
Exception Thrown: System.ArgumentNullException
```

## 例 3: 为`ArgumentOutOfRangeException`

```cs
// C# program to demonstrate the
// Convert.ToBase64String() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // defining and initializing
            // byte1
            byte[] byte1 = {2, 4, 6, 8, 10,
                       12, 14, 16, 18, 20};

            // calling get() Method
            get(byte1, "byte1");

            Console.WriteLine("");

            // converting base 64 string to byte array
            Console.WriteLine("Length is negative");

            string val = Convert.ToBase64String(byte1, 0, -10);

            Console.WriteLine("Converted byte value: {0}", val);
        }

        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(),
                        e.Message);
        }
    }

    // Defining get() method
    public static void get(byte[] bytes, string str)
    {
        Console.WriteLine("For {0}", str);

        // converting byte to base 64 string
        string val = Convert.ToBase64String(bytes,
                                 0, bytes.Length);

        // display the converted string
        Console.WriteLine("converted string: {0}", val);
    }
}
```

## 输出:

```cs
For byte1
converted string: AgQGCAoMDhASFA==

Length is negative
Exception Thrown: System.ArgumentOutOfRangeException
```

## 参考:

*   [https://docs.microsoft.com/en-us/dotnet/api/system.convert.tobase64string?view=netframework-4.7.2#System_Convert_ToBase64String_System_Byte___System_Int32_System_Int32_](https://docs.microsoft.com/en-us/dotnet/api/system.convert.tobase64string?view=netframework-4.7.2#System_Convert_ToBase64String_System_Byte___System_Int32_System_Int32_)