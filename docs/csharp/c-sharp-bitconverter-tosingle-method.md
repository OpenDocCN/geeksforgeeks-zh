# C# | BitConverter。ToSingle()方法

> 原文:[https://www . geesforgeks . org/c-sharp-bit converter-to single-method/](https://www.geeksforgeeks.org/c-sharp-bitconverter-tosingle-method/)

此方法用于返回从字节数组中指定位置的四个字节转换而来的单精度浮点数。

**语法:**

```cs
public static float ToSingle (byte[] value, int startIndex);
```

**参数:**

> **值:**是字节数组。
> **起始指数:**是数值内的起始位置。

**返回值:**这个方法返回一个单精度浮点数，由 startIndex 开始的四个字节组成。

**异常:**

*   **参数异常:**如果*起始索引*大于或等于*值的长度*减 3，小于或等于*值的长度*减 1。
*   **ArgumentNullException:** 如果值为空。
*   **ArgumentOutOfRangeException:**如果 startIndex 小于零或大于*值*的长度减 1。

以下程序说明了*位转换器的使用。ToSingle(Byte[]，Int32)* 方法:

**例 1:**

```cs
// C# program to demonstrate
// BitConverter.ToSingle(Byte[], Int32)
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array of byte values.
        byte[] bytes = {0, 128, 63, 0, 0,
                        112, 65, 0, 255, 
                        127, 71, 0, 0, 
                        128, 59, 0, 0,
                        128, 47, 73, 70, 
                        131, 5, 75, 6, 
                             158, 63};

        // Display the values of the myArr.
        Console.Write("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

        // print char value
        Console.WriteLine("index     Array elements     float values");
        Console.WriteLine();

        // getting float value and Display it
        for (int index = 0; index < bytes.Length - 3; 
                                 index = index + 4) {

            float values = BitConverter.ToSingle(bytes, index);
            Console.WriteLine(" {0}     {1}         {2}", 
                   index, BitConverter.ToString(bytes,
                                    index, 4), values);
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
Initial Array: 0 128 63 0 0 112 65 0 255 127 71 0 0 128 59 0 0 128 47 73 70 131 5 75 6 158 63 

index     Array elements       float values

  0        00-80-3F-00         5.831554E-39
  4        00-70-41-00         6.009485E-39
  8        FF-7F-47-00         6.566237E-39
  12        00-80-3B-00         5.464212E-39
  16        00-80-2F-49         718848
  20        46-83-05-4B         8749894

```

**示例 2:** 适用于*参数异常*

```cs
// C# program to demonstrate
// BitConverter.ToSingle(Byte[], Int32)
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array of byte values.
        byte[] bytes ={0, 128, 63, 0, 0,
                        112, 65, 0, 255, 
                        127, 71, 0, 0, 
                        128, 59, 0, 0,
                        128, 47, 73, 70, 
                        131, 5, 75, 6, 
                             158, 63};

        // Display the values of the myArr.
        Console.Write("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

        // print char value
        Console.WriteLine("index     Array elements"+
                              "       float values");
        Console.WriteLine();

        // getting float value and Display it
        for (int index = 0; index < bytes.Length - 2; 
                                index = index + 4) {

            if (index == bytes.Length - 3) {
                Console.WriteLine();
                Console.WriteLine("startIndex is equal to"+
                           " the length of bytes minus 3");

                float values = BitConverter.ToSingle(bytes, index);
                Console.WriteLine("  {0}        {1}         {2}", 
                              index, BitConverter.ToString(bytes,
                                              index, 4), values);
            }
            else {
                float values = BitConverter.ToSingle(bytes, index);
                Console.WriteLine("  {0}        {1}         {2}",
                              index, BitConverter.ToString(bytes,
                                              index, 4), values);
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
}
}
```

**输出:**

```cs
Initial Array: 0 128 63 0 0 112 65 0 255 127 71 0 0 128 59 0 0 128 47 73 70 131 5 75 6 158 63 

index     Array elements       float values

  0        00-80-3F-00         5.831554E-39
  4        00-70-41-00         6.009485E-39
  8        FF-7F-47-00         6.566237E-39
  12        00-80-3B-00         5.464212E-39
  16        00-80-2F-49         718848
  20        46-83-05-4B         8749894

startIndex is equal to the length of bytes minus 3
Exception Thrown: System.ArgumentException

```

**例 3:** 为*argumentout of range exception*

```cs
// C# program to demonstrate
// BitConverter.ToSingle(Byte[], Int32)
// Method
using System;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Define an array of byte values.
            byte[] bytes = {0, 128, 63, 0, 0, 112, 65,
                            0, 255, 127, 71, 0, 0, 128,
                            59, 0, 0, 128, 47, 73, 70, 
                            131, 5, 75, 6, 158, 63, 24};

            // Display the values of the myArr.
            Console.Write("Initial Array: ");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(bytes);

            // print char value
            Console.WriteLine("index     Array elements     float values");
            Console.WriteLine();

            // getting float value and Display it
            for (int index = 0; index < bytes.Length + 1;
                                     index = index + 4) {

                if (index == bytes.Length) {
                    Console.WriteLine();
                    Console.WriteLine("startIndex is greater than "+
                                    "the length of bytes minus 1.");

                    float values = BitConverter.ToSingle(bytes, index);
                    Console.WriteLine(" {0}     {1}         {2}", 
                           index, BitConverter.ToString(bytes,
                                            index, 4), values);
                }
                else {
                    float values = BitConverter.ToSingle(bytes, index);
                    Console.WriteLine(" {0}     {1}         {2}",
                           index, BitConverter.ToString(bytes,
                                           index, 4), values);
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
    }
}
```

**输出:**

```cs
Initial Array: 0 128 63 0 0 112 65 0 255 127 71 0 
               0 128 59 0 0 128 47 73 70 131 5 75
               6 158 63 24 

index     Array elements       float values

  0        00-80-3F-00         5.831554E-39
  4        00-70-41-00         6.009485E-39
  8        FF-7F-47-00         6.566237E-39
  12        00-80-3B-00         5.464212E-39
  16        00-80-2F-49         718848
  20        46-83-05-4B         8749894
  24        06-9E-3F-18         2.476595E-24

startIndex is greater than the length of bytes minus 1.
Exception Thrown: System.ArgumentOutOfRangeException

```

**示例 4:** 适用于*参数异常*

```cs
// C# program to demonstrate
// BitConverter.ToSingle(Byte[], Int32)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Define an array of byte
            // values with null value
            byte[] bytes = null;

            // getting the float value
            float values = BitConverter.ToSingle(bytes, 0);

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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . bit converter . to single？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.tosingle?view=netframework-4.7.2)