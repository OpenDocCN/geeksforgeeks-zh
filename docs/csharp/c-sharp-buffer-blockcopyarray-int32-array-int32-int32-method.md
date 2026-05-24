# C# |缓冲区。块复制(数组，Int32，数组，Int32，Int32)方法

> 原文:[https://www . geesforgeks . org/c-sharp-buffer-block copyright-int 32-array-int 32-int 32-method/](https://www.geeksforgeeks.org/c-sharp-buffer-blockcopyarray-int32-array-int32-int32-method/)

此方法用于将指定数量的字节从从特定偏移量开始的源数组复制到从特定偏移量开始的目标数组。
**语法:**

```cs
public static void BlockCopy (Array src, int srcOffset, Array dst, int dstOffset, int count);
```

**参数:**

> **src:** 是源缓冲区。
> **srcOffset:** 是进入 *src* 的从零开始的字节偏移量。
> **dst:** 是目的缓冲区。
> **dstOffset:** 从零开始的字节偏移量变为 *dst* 。
> **计数:**要复制的字节数。

**例外:**

*   **ArgumentNullException:** 如果 *src* 或 *dst* 为空。
*   **参数异常:**如果 *src* 或 *dst* 不是基元数组 ***或*** ，则 *src* 中的字节数小于 *srcOffset* 加上*计数*。 ***或****dst*中的字节数小于 *dstOffset* 加上 *count* 。
*   **ArgumentOutOfRangeException:**如果 *srcOffset* 、 *dstOffset* 或 *count* 小于 0。

以下程序说明了**缓冲区的使用。BlockCopy(Array，Int32，Array，Int32，Int32)** 方法:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Buffer.BlockCopy(Array, Int32,
// Array, Int32, Int32) Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Declaring src and dest array
        long[] src = {15, 16, 17, 18 };
        long[] dest = {17, 18, 19, 20 };

        Console.WriteLine("Initial Array values:");
        Console.WriteLine();

        // Display hexadecimal values
        Console.WriteLine("Array element in hexadecimal form:");
        displayhexvalue(src, "src");
        displayhexvalue(dest, "dest");

        // display Individual byte
        Console.WriteLine("Individual bytes:");
        displaybytes(src, "src");
        displaybytes(dest, "dest");

        // copying the specified number of bytes
        // using Buffer.BlockCopy() method
        Buffer.BlockCopy(src, 4, dest, 7, 6);

        Console.WriteLine();
        Console.WriteLine("Array after operation:");
        Console.WriteLine();

        // display hexadecimal values
        Console.WriteLine("Array element in hexadecimal form:");
        displayhexvalue(src, "src");
        displayhexvalue(dest, "dest");

        // display hexadecimal value
        Console.WriteLine("Individual bytes:");
        displaybytes(src, "src");
        displaybytes(dest, "dest");
    }
    catch (ArgumentNullException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
    catch (ArgumentOutOfRangeException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
    catch (ArgumentException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
}

// Display the individual
// array element values
// in hexadecimal.
public static void displayhexvalue(Array a,
                              string name)
{
    // print the name
    Console.Write("{0, 5}:", name);

    // Display value one by one
    for (int i = 0; i < a.Length; i++)
        Console.Write(" {0:X16} ", a.GetValue(i));

    Console.WriteLine();
}

// Display the individual
// bytes in the array
// in hexadecimal.
public static void displaybytes(Array arr,
                              string name)
{
    // print the name
    Console.Write("{0, 5}:", name);

    // loop to traverse
    // every element of the array
    for (int i = 0; i < arr.Length; i++) {

        // getting byte array
        // converted from long array
        byte[] bytes = BitConverter.GetBytes((long)arr.GetValue(i));

        // display each byte value
        foreach(byte byteValue in bytes)
            Console.Write(" {0:X2}", byteValue);
    }
    Console.WriteLine();
}
}
```

**输出:**

> 初始数组值:
> 十六进制形式的数组元素:
> src:0000000000000000000000000000000000000000011 00000000000000000012
> dest:000000000000000000000000000000000000000012 000000000000000000000000000000000012 00 00 00 14 00 00 00 00 00 00 00 00
> 运算后的数组:
> 十六进制形式的数组元素:
> src:000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000 00 00 10 00 00 00 00 13 00 00 00 00 00 00 00 00 14 00 00 00 00 00 00 00 00 00

**例 2:** 为 *ArgumentNullException* 为

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Buffer.BlockCopy(Array, Int32,
// Array, Int32, Int32) Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Declaring src and dest array
        long[] src = {15, 16, 17, 18};
        long[] dest = {17, 18, 19, 20};

        Console.WriteLine("Initial Array values:");
        Console.WriteLine();

        // Display hexadecimal values
        Console.WriteLine("Array element in hexadecimal form:");
        displayhexvalue(src, "src");
        displayhexvalue(dest, "dest");

        // display Individual byte
        Console.WriteLine("Individual bytes:");
        displaybytes(src, "src");
        displaybytes(dest, "dest");

        // copying the specified number of bytes
        // using Buffer.BlockCopy() method
        Console.WriteLine("src and dst are null:");
        Buffer.BlockCopy(null, 4, null, 7, 6);

        Console.WriteLine();
        Console.WriteLine("Array after operation:");
        Console.WriteLine();

        // display hexadecimal values
        Console.WriteLine("Array element in hexadecimal form:");
        displayhexvalue(src, "src");
        displayhexvalue(dest, "dest");

        // display hexadecimal value
        Console.WriteLine("Individual bytes:");
        displaybytes(src, "src");
        displaybytes(dest, "dest");
    }
    catch (ArgumentNullException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
    catch (ArgumentOutOfRangeException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
    catch (ArgumentException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
}

// Display the individual array
// element values in hexadecimal.
public static void displayhexvalue(Array a,
                              string name)
{
    // print the name
    Console.Write("{0, 5}:", name);

    // Display value one by one
    for (int i = 0; i < a.Length; i++)
        Console.Write(" {0:X16} ", a.GetValue(i));

    Console.WriteLine();
}

// Display the individual bytes
// in the array in hexadecimal.
public static void displaybytes(Array arr,
                              string name)
{

    // print the name
    Console.Write("{0, 5}:", name);

    // loop to traverse every
    // element of the array
    for (int i = 0; i < arr.Length; i++) {

        // getting byte array converted
        // from long array
        byte[] bytes = BitConverter.GetBytes((long)arr.GetValue(i));

        // display each byte value
        foreach(byte byteValue in bytes)
            Console.Write(" {0:X2}", byteValue);
    }
    Console.WriteLine();
}
}
```

**输出:**

> 初始数组值:
> 十六进制形式的数组元素:
> src:0000000000000000000000000000000000000000011 00000000000000000012
> dest:000000000000000000000000000000000000000012 000000000000000000000000000000000012 00 00 00 14 00 00 00 00 00 00 00 00
> src 和 dst 为空:
> 抛出异常:系统。 ArgumentNullException

**例 3:** 为*argumentout of rangeexception*为

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Buffer.BlockCopy(Array, Int32,
// Array, Int32, Int32) Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Declaring src and dest array
        long[] src = {15, 16, 17, 18};
        long[] dest = {17, 18, 19, 20};

        Console.WriteLine("Initial Array values:");
        Console.WriteLine();

        // Display hexadecimal values
        Console.WriteLine("Array element in hexadecimal form:");
        displayhexvalue(src, "src");
        displayhexvalue(dest, "dest");

        // display Individual byte
        Console.WriteLine("Individual bytes:");
        displaybytes(src, "src");
        displaybytes(dest, "dest");

        // copying the specified number of bytes
        // using Buffer.BlockCopy() method
        Console.WriteLine("srcoffest and destoffset are less than zero:");
        Buffer.BlockCopy(src, -4, dest, -7, 6);

        Console.WriteLine();
        Console.WriteLine("Array after operation:");
        Console.WriteLine();

        // display hexadecimal values
        Console.WriteLine("Array element in hexadecimal form:");
        displayhexvalue(src, "src");
        displayhexvalue(dest, "dest");

        // display hexadecimal value
        Console.WriteLine("Individual bytes:");
        displaybytes(src, "src");
        displaybytes(dest, "dest");
    }
    catch (ArgumentNullException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
    catch (ArgumentOutOfRangeException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
    catch (ArgumentException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
}

// Display the individual array
// element values in hexadecimal.
public static void displayhexvalue(Array a,
                              string name)
{
    // print the name
    Console.Write("{0, 5}:", name);

    // Display value one by one
    for (int i = 0; i < a.Length; i++)
        Console.Write(" {0:X16} ", a.GetValue(i));

    Console.WriteLine();
}

// Display the individual bytes
// in the array in hexadecimal.
public static void displaybytes(Array arr,
                             string name)
{
    // print the name
    Console.Write("{0, 5}:", name);

    // loop to traverse every
    // element of the array
    for (int i = 0; i < arr.Length; i++) {

        // getting byte array converted
        // from long array
        byte[] bytes = BitConverter.GetBytes((long)arr.GetValue(i));

        // display each byte value
        foreach(byte byteValue in bytes)
            Console.Write(" {0:X2}", byteValue);
    }
    Console.WriteLine();
}
}
```

**输出:**

> 初始数组值:
> 十六进制形式的数组元素:
> src:0000000000000000000000000000000000000000011 00000000000000000012
> dest:000000000000000000000000000000000000000012 000000000000000000000000000000000012 00 00 00 14 00 00 00 00 00 00 00
> srcoffest 和 destoffset 小于零:
> 异常抛出:系统。 argumentoutofrangerexception

**例 4:** 为*议论文异常*为

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Buffer.BlockCopy(Array, Int32,
// Array, Int32, Int32)
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Declaring src and dest array
        long[] src = {15, 16, 17, 18};
        long[] dest = {17, 18, 19, 20};

        Console.WriteLine("Initial Array values:");
        Console.WriteLine();

        // Display hexadecimal values
        Console.WriteLine("Array element in hexadecimal form:");
        displayhexvalue(src, "src");
        displayhexvalue(dest, "dest");

        // display Individual byte
        Console.WriteLine("Individual bytes:");
        displaybytes(src, "src");
        displaybytes(dest, "dest");

        // copying the specified number of bytes
        // using Buffer.BlockCopy() method
        Console.WriteLine("srcoffest and destoffset are less than zero:");
        Buffer.BlockCopy(src, 4, dest, 7, 70);

        Console.WriteLine();
        Console.WriteLine("Array after operation:");
        Console.WriteLine();

        // display hexadecimal values
        Console.WriteLine("Array element in hexadecimal form:");
        displayhexvalue(src, "src");
        displayhexvalue(dest, "dest");

        // display hexadecimal value
        Console.WriteLine("Individual bytes:");
        displaybytes(src, "src");
        displaybytes(dest, "dest");
    }
    catch (ArgumentNullException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
    catch (ArgumentOutOfRangeException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
    catch (ArgumentException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
}

// Display the individual array
// element values in hexadecimal.
public static void displayhexvalue(Array a,
                               string name)
{
    // print the name
    Console.Write("{0, 5}:", name);

    // Display value one by one
    for (int i = 0; i < a.Length; i++)
        Console.Write(" {0:X16} ", a.GetValue(i));

    Console.WriteLine();
}

// Display the individual bytes
// in the array in hexadecimal.
public static void displaybytes(Array arr,
                              string name)
{
    // print the name
    Console.Write("{0, 5}:", name);

    // loop to traverse every
    // element of the array
    for (int i = 0; i < arr.Length; i++) {

        // getting byte array
        // converted from long array
        byte[] bytes = BitConverter.GetBytes((long)arr.GetValue(i));

        // display each byte value
        foreach(byte byteValue in bytes)
            Console.Write(" {0:X2}", byteValue);
    }
    Console.WriteLine();
}
}
```

**输出:**

> 初始数组值:
> 十六进制形式的数组元素:
> src:0000000000000000000000000000000000000000011 00000000000000000012
> dest:000000000000000000000000000000000000000012 000000000000000000000000000000000012 00 00 00 14 00 00 00 00 00 00 00
> srcoffest 和 destoffset 小于零:
> 异常抛出:系统。 ArgumentException

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . buffer . block copy？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.buffer.blockcopy?view=netframework-4.7.2)