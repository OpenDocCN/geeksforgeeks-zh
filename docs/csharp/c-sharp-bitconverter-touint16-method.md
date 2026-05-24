# C# | BitConverter。图注 16 方法

> 原文:[https://www . geesforgeks . org/c-sharp-bit converter-touint 16-method/](https://www.geeksforgeeks.org/c-sharp-bitconverter-touint16-method/)

此方法用于返回从字节数组中指定位置的两个字节转换而来的 16 位无符号整数。
**语法:**

```cs
public static ushort ToUInt16 (byte[] value, int startIndex);
```

**参数:**

> **值:**是字节数组。
> **起始指数:**是数值内的起始位置。

**返回值:**该方法返回一个 16 位无符号整数，由从*开始的两个字节组成*。
**例外:**

*   **参数异常:**如果 startIndex 等于字节长度减 1。
*   **ArgumentNullException:** 如果字节为空。
*   **argumentoutofrangerexception:**如果 startIndex 小于零或大于字节长度减 1。

以下程序说明了**位转换器的使用。途观 16 法**:
T3】例 1:T5】

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// BitConverter.ToUInt16(Byte[], Int32);
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Define an array of byte values.
            byte[] bytes = {32, 0, 0, 42, 0, 65,
                            0, 125, 0, 197, 0,
                            168, 3, 41, 4, 125,
                                           32};

            // Display the values of the myArr.
            Console.Write("Initial Array: ");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(bytes);

            // print char value
            Console.WriteLine("index    byte Array     ushort value");
            for (int index = 0; index < bytes.Length - 1;
                                    index = index + 2) {

                ushort values = BitConverter.ToUInt16(bytes, index);

                Console.WriteLine("  {0}        {1}          {2}",
                               index, BitConverter.ToString(bytes,
                                               index, 2), values);
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

**Output:** 

```cs
Initial Array: 32 0 0 42 0 65 0 125 0 197 0 168 3 41 4 125 32 

index    byte Array     ushort value
  0        20-00          32
  2        00-2A          10752
  4        00-41          16640
  6        00-7D          32000
  8        00-C5          50432
  10        00-A8          43008
  12        03-29          10499
  14        04-7D          32004
```

**例 2:** 为*议论文异常*为

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// BitConverter.ToUInt16(Byte[], Int32);
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Define an array of byte values.
            byte[] bytes = {32, 0, 0, 42, 0, 65,
                              0, 125, 0, 197, 0,
                           168, 3, 41, 4, 125 };

            // Display the values of the myArr.
            Console.Write("Initial Array: ");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(bytes);

            // print char value
            Console.WriteLine("index    element     ushot value");
            for (int index = 1; index < bytes.Length;
                                 index = index + 2) {

                if (index == bytes.Length - 1) {

                    Console.WriteLine();
                    Console.WriteLine("startindex is {0} which is equals to "+
                                        "the length of Array minus 1.", index);

                    ushort values = BitConverter.ToUInt16(bytes, index);

                    Console.WriteLine("  {0}      {1}         {2}",
                                index, BitConverter.ToString(bytes,
                                                index, 2), values);
                }
                else {
                    ushort values = BitConverter.ToUInt16(bytes, index);
                    Console.WriteLine("  {0}      {1}         {2}",
                                index, BitConverter.ToString(bytes,
                                                index, 2), values);
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

**Output**

```cs
Initial Array: 32 0 0 42 0 65 0 125 0 197 0 168 3 41 4 125 

initial Array in string: 20-00-00-2A-00-41-00-7D-00-C5-00-A8-03-29-04-7D 

index    element     ushot value
  1      00-00         0
  3      2A-00         42
  5      41-00         65
  7      7D-00         125
  9      C5-00         197
  11      A8-03         936
  13      29-04         1065

startindex is 15 which is equals to the length of Array minus 1.
Exception Thrown: System.ArgumentException
```

**例 3:** 为*argumentout of rangeexception*为

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// BitConverter.ToUInt16(Byte[], Int32);
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
            Console.WriteLine("index    element     ushot value");
            for (int index = 0; index < bytes.Length + 1;
                                    index = index + 2) {

                if (index == bytes.Length) {

                    Console.WriteLine();
                    Console.WriteLine("startindex is {0} which is greater than "+
                                          "the length of Array minus 1.", index);

                    ushort values = BitConverter.ToUInt16(bytes, index);
                    Console.WriteLine("  {0}      {1}         {2}",
                                index, BitConverter.ToString(bytes,
                                                index, 2), values);
                }

                else {
                    ushort values = BitConverter.ToUInt16(bytes, index);
                    Console.WriteLine("  {0}      {1}         {2}",
                                index, BitConverter.ToString(bytes,
                                                index, 2), values);
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

**Output**

```cs
Initial Array: 32 0 0 42 0 65 0 125 0 197 0 168 3 41 4 125 

initial Array in string: 20-00-00-2A-00-41-00-7D-00-C5-00-A8-03-29-04-7D 

index    element     ushot value
  0      20-00         32
  2      00-2A         10752
  4      00-41         16640
  6      00-7D         32000
  8      00-C5         50432
  10      00-A8         43008
  12      03-29         10499
  14      04-7D         32004

startindex is 16 which is greater than the length of Array minus 1.
Exception Thrown: System.ArgumentOutOfRangeException
```

**例 4:** 为 *ArgumentNullException* 为

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// BitConverter.ToUInt16(Byte[], Int32);
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Define an array of byte values.
            byte[] bytes = null;

            // get the long value

            ushort values = BitConverter.ToUInt16(bytes, 0);
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

**Output:** 

```cs
Exception Thrown: System.ArgumentNullException
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . bit converter . touint 16？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.touint16?view=netframework-4.7.2)