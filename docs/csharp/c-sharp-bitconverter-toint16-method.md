# C# | BitConverter。ToInt16()方法

> 原文:[https://www . geesforgeks . org/c-sharp-bit converter-to int 16-method/](https://www.geeksforgeeks.org/c-sharp-bitconverter-toint16-method/)

此方法用于返回从字节数组中指定位置的两个字节转换而来的 16 位有符号整数。

**语法:**

```cs
public static short ToInt16 (byte[] value, int startIndex);
```

**参数:**

> **值:**是字节数组。
> **起始指数:**是数值内的起始位置。

**返回值:**这个方法返回一个 16 位有符号整数，由 startIndex 开始的两个字节组成。

**异常:**

> **参数异常:**如果*开始索引*等于*值的长度*减 1。
> **ArgumentNullException:**如果值为空。
> **ArgumentOutOfRangeException:**如果 startIndex 小于零或者大于*值*的长度减 1。

以下程序说明了**位转换器的使用。ToInt16(字节[]，Int32)** 方法:

**例 1:**

## C#

```cs
// C# program to demonstrate
// BitConverter.ToInt16(Byte[], Int32);
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array of byte values.
        byte[] bytes = {32, 0, 0, 42, 0, 65, 0, 125, 0,
                        197, 0, 168, 3, 41, 4, 125, 32};

        // Display the values of the myArr.
        Console.Write("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

        // print char value
        Console.WriteLine("index byte Array     short value");
        for (int index = 0; index < bytes.Length - 1;
                                index = index + 2) {

            short values = BitConverter.ToInt16(bytes, index);

            Console.WriteLine(" {0}     {1}         {2}",
            index, BitConverter.ToString(bytes, index, 2), values);
        }
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

**输出:**

```cs
Initial Array: 32 0 0 42 0 65 0 125 0 197 0 168 3 41 4 125 32 

index    byte Array     short value
  0        20-00         32
  2        00-2A         10752
  4        00-41         16640
  6        00-7D         32000
  8        00-C5         -15104
  10        00-A8         -22528
  12        03-29         10499
  14        04-7D         32004
```

**示例 2:** 适用于*参数异常*

## C#

```cs
// C# program to demonstrate
// BitConverter.ToInt16(Byte[], Int32);
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array of byte values.
        byte[] bytes = {32, 0, 0, 42, 0, 65, 0, 125, 0,
                        197, 0, 168, 3, 41, 4, 125};

        // Display the values of the myArr.
        Console.Write("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

        // print char value
        Console.WriteLine("index element     short value");
        for (int index = 1; index < bytes.Length;
                            index = index + 2) {

            if (index == bytes.Length - 1) {

                Console.WriteLine();
                Console.WriteLine("startIndex equals the"+
                              " length of value minus 1.");
                short values = BitConverter.ToInt16(bytes, index);
                Console.WriteLine(" {0}     {1}         {2}",
                index, BitConverter.ToString(bytes, index, 2), values);
            }
            else {

                short values = BitConverter.ToInt16(bytes, index);
                Console.WriteLine(" {0}     {1}         {2}",
                index, BitConverter.ToString(bytes, index, 2),
                                                      values);
            }
        }
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

// Defining the method
// PrintIndexAndValues
public static void PrintIndexAndValues(byte[] myArr)
{
    for (int i = 0; i < myArr.Length; i++) {

        Console.Write("{0} ", myArr[i]);
    }

    Console.WriteLine();
    Console.WriteLine();
    Console.WriteLine("initial Array in string: {0} ",
                    BitConverter.ToString(myArr));
    Console.WriteLine();
}
}
```

**输出:**

```cs
Initial Array: 32 0 0 42 0 65 0 125 0 197 0 168 3 41 4 125 

initial Array in string: 20-00-00-2A-00-41-00-7D-00-C5-00-A8-03-29-04-7D 

index    element     short value
  1      00-00         0
  3      2A-00         42
  5      41-00         65
  7      7D-00         125
  9      C5-00         197
  11      A8-03         936
  13      29-04         1065

startIndex equals the length of value minus 1.
Exception Thrown: System.ArgumentException
```

**例 3:** 为*argumentout of range exception*

## C#

```cs
// C# program to demonstrate
// BitConverter.ToInt16(Byte[], Int32);
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Define an array of byte values.
            byte[] bytes = {32, 0, 0, 42, 0, 65, 0, 125, 0,
                               197, 0, 168, 3, 41, 4, 125};

            // Display the values of the myArr.
            Console.Write("Initial Array: ");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(bytes);

            // print char value
            Console.WriteLine("index    element     short value");
            for (int index = 0; index < bytes.Length + 1;
                                    index = index + 2) {

                if (index == bytes.Length) {
                    Console.WriteLine();
                    Console.WriteLine("startIndex is greater than "+
                                    "the length of value minus 1.");
                    short values = BitConverter.ToInt16(bytes, index);
                }
                else {
                    short values = BitConverter.ToInt16(bytes, index);
                    Console.WriteLine("  {0}      {1}         {2}",
                      index, BitConverter.ToString(bytes, index, 2), values);
                }
            }
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

    // Defining the method
    // PrintIndexAndValues
    public static void PrintIndexAndValues(byte[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {

            Console.Write("{0} ", myArr[i]);
        }

        Console.WriteLine();
        Console.WriteLine();
        Console.WriteLine("initial Array in string: {0} ",
                           BitConverter.ToString(myArr));
        Console.WriteLine();
    }
}
```

**输出:**

```cs
Initial Array: 32 0 0 42 0 65 0 125 0 197 0 168 3 41 4 125 

initial Array in string: 20-00-00-2A-00-41-00-7D-00-C5-00-A8-03-29-04-7D 

index    element     short value
  0      20-00         32
  2      00-2A         10752
  4      00-41         16640
  6      00-7D         32000
  8      00-C5         -15104
  10      00-A8         -22528
  12      03-29         10499
  14      04-7D         32004

startIndex is greater than the length of value minus 1.
Exception Thrown: System.ArgumentOutOfRangeException
```

**示例 4:** 适用于*参数异常*

## C#

```cs
// C# program to demonstrate
// BitConverter.ToInt16(Byte[], Int32);
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Define an array of byte values.
            byte[] bytes = null;

            // get the char value

            short values = BitConverter.ToInt16(bytes, 0);
            Console.Write("{0}", values);
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
}
```

**输出:**

```cs
Exception Thrown: System.ArgumentNullException
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . bit converter . to int 16？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.toint16?view=netframework-4.7.2)