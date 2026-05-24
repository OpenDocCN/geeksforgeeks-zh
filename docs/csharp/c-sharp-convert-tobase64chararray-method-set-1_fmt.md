# C# | Convert.ToBase64CharArray() 方法 | Set-1

> 原文: [https://www.geeksforgeeks.org/c-sharp-convert-tobase64chararray-method-set-1/](https://www.geeksforgeeks.org/c-sharp-convert-tobase64chararray-method-set-1/)

此方法用于将 8 位无符号整数数组的子集转换为以 64 位为基数编码的 Unicode 字符数组的等效子集。参数将子集指定为输入和输出数组中的偏移量，以及输入数组中要转换的元素数量。

## 语法:

> `public static int ToBase64CharArray(byte[] inArray, int offsetIn, int length, char[] outArray, int offsetOut);`

## 参数:

*   `inArray`: 8 位无符号整数的输入数组。
*   `offsetIn`: `inArray` 内的一个位置。
*   `length`: 需要转换的 `inArray` 的元素个数。
*   `outArray`: Unicode 字符的输出数组。
*   `offsetOut`: 输出数组中的一个位置。

## 返回值:

该方法返回一个 32 位有符号整数，包含 `outArray` 中的字节数。

## 异常:

*   `ArgumentNullException`: 如果 `inArray` 或 `outArray` 为空。
*   `ArgumentOutOfRangeException`: 如果 `offsetIn`、`offsetOut` 或 `length` 为负，**或** `offsetIn` 加上 `length` 大于 `inArray.Length`，**或** `offsetOut` 加上要返回的元素数大于 `outArray.Length`。

以下程序说明了 `Convert.ToBase64CharArray()` 方法的使用:

## 例 1:

```cs
// C# program to demonstrate the
// Convert.FromBase64String(String) 
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // defining and initializing
            // byte1 and byte2
            byte[] byte1 = {2, 4, 6, 8, 10, 12,
                            14, 16, 18, 20};

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

        long arrayLength = (long)((4.0d / 3.0d) *
                                  bytes.Length);

        // If array length is not divisible
        // by 4, go up to the next multiple
        // of 4.
        if (arrayLength % 4 != 0)
            arrayLength += 4 - arrayLength % 4;

        // creating object of char array
        char[] base64CharArray = new char[arrayLength];

        // converting byte to base 64 string
        int val = Convert.ToBase64CharArray(bytes, 0,
                   bytes.Length, base64CharArray, 0);

        Console.WriteLine("Total no of bytes: {0}", val);

        // display the base64CharArray
        Console.Write("base64CharArray: ");
        for (int j = 0; j < base64CharArray.Length; j++)
            Console.Write("{0}", base64CharArray[j]);
        Console.WriteLine("");
    }
}
```

**Output:**

```cs
For byte1
Total no of bytes: 16
base64CharArray: AgQGCAoMDhASFA==

For byte2
Total no of bytes: 8
base64CharArray: ChQeKDI=
```

## 示例 2: 适用于 `ArgumentNullException`

```cs
// C# program to demonstrate the
// Convert.FromBase64String(String)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // defining and initializing
            // byte1 
            byte[] byte1 = {2, 4, 6, 8, 10, 12,
                            14, 16, 18, 20};

            // calling get() Method
            get(byte1, "byte1");

            // converting base 64 
            // string to byte array
            Console.WriteLine("inArray and outArray are null.");

            int val = Convert.ToBase64CharArray(null, 0,
                                                10, null, 0);

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

        long arrayLength = (long)((4.0d / 3.0d) * 
                                  bytes.Length);

        // If array length is not divisible 
        // by 4, go up to the next multiple
        // of 4.
        if (arrayLength % 4 != 0)
            arrayLength += 4 - arrayLength % 4;

        // creating object of char array
        char[] base64CharArray = new char[arrayLength];

        // converting byte to base 64 string
        int val = Convert.ToBase64CharArray(bytes, 0,
                   bytes.Length, base64CharArray, 0);

        Console.WriteLine("Total no of bytes: {0}", val);

        // display the base64CharArray
        Console.Write("base64CharArray: ");
        for (int j = 0; j < base64CharArray.Length; j++)
            Console.Write("{0}", base64CharArray[j]);
        Console.WriteLine("\n");
    }
}
```

**Output:**

```cs
For byte1
Total no of bytes: 16
base64CharArray: AgQGCAoMDhASFA==

inArray and outArray are null.
Exception Thrown: System.ArgumentNullException
```

## 例 3: 为 `ArgumentOutOfRangeException`

```cs
// C# program to demonstrate the
// Convert.FromBase64String(String)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // defining and initializing
            // byte1 and byte2
            byte[] byte1 = {2, 4, 6, 8, 10, 12,
                            14, 16, 18, 20};

            byte[] byte2 = {10, 20, 30, 40, 50};

            // calling get() Method
            get(byte1, "byte1");

            // converting base 64 string
            // to byte array
            Console.WriteLine("length of inArray is negative");

            char[] base64CharArray = new char[10];
            int val = Convert.ToBase64CharArray(byte2, 0,
                         -10, base64CharArray, 0);

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

        long arrayLength = (long)((4.0d / 3.0d) * bytes.Length);

        // If array length is not divisible 
        // by 4, go up to the next multiple 
        // of 4.
        if (arrayLength % 4 != 0)
            arrayLength += 4 - arrayLength % 4;

        // creating object of char array
        char[] base64CharArray = new char[arrayLength];

        // converting byte to base 64 string
        int val = Convert.ToBase64CharArray(bytes, 0,
                   bytes.Length, base64CharArray, 0);

        Console.WriteLine("Total no of bytes: {0}", val);

        // display the base64CharArray
        Console.Write("base64CharArray: ");
        for (int j = 0; j < base64CharArray.Length; j++)
            Console.Write("{0}", base64CharArray[j]);
        Console.WriteLine("\n");
    }
}
```

**Output:**

```cs
For byte1
Total no of bytes: 16
base64CharArray: AgQGCAoMDhASFA==

length of inArray is negative
Exception Thrown: System.ArgumentOutOfRangeException
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.convert.tobase64chararray?view=netframework-4.7.2#System_Convert_ToBase64CharArray_System_Byte___System_Int32_System_Int32_System_Char___System_Int32_](https://docs.microsoft.com/en-us/dotnet/api/system.convert.tobase64chararray?view=netframework-4.7.2#System_Convert_ToBase64CharArray_System_Byte___System_Int32_System_Int32_System_Char___System_Int32_)