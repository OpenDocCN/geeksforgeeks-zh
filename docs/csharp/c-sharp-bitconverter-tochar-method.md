# C# | BitConverter。ToChar()方法

> 原文:[https://www . geesforgeks . org/c-sharp-bit converter-to char-method/](https://www.geeksforgeeks.org/c-sharp-bitconverter-tochar-method/)

此方法用于返回从字节数组中指定位置的两个字节转换而来的 Unicode 字符。
**语法:**

```cs
public static char ToChar (byte[] value, int startIndex);
```

**参数:**

> **值:**是数组。
> **startIndex:** 是数值内的起始位置。

**返回值:**这个方法返回一个由两个字节组成的字符，从*开始索引*开始。
**例外:**

> **参数异常:**如果*开始索引*等于值的长度减 1。
> **参数空异常:**如果*值*为空。
> **ArgumentOutOfRangeException:**如果 startIndex 小于零或大于值的长度减 1。

以下程序说明了**位转换器的使用。ToChar(Byte[]，Int32)** 方法:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// BitConverter.ToChar(Byte[], Int32);
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array of byte values.
        byte[] bytes = { 32, 0, 0, 42, 0, 65, 0, 125, 0,
                        197, 0, 168, 3, 41, 4, 125, 32 };

        // Display the values of the myArr.
        Console.Write("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

        // print char value
        for (int index = 1; index < bytes.Length - 1;
                                index = index + 2) {

            char values = BitConverter.ToChar(bytes, index);
            Console.WriteLine("index element   char");
            Console.WriteLine(" {0}     {1}     {2}",
                            index, bytes[index], values);
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
Initial Array: 32 0 0 42 0 65 0 125 0 197 0 168 3 41 4 125 32 

initial Array in string: 20-00-00-2A-00-41-00-7D-00-C5-00-A8-03-29-04-7D-20 

index  element     char
  1      0         
index  element     char
  3      42         *
index  element     char
  5      65         A
index  element     char
  7      125         }
index  element     char
  9      197         ?
index  element     char
  11      168         ?
index  element     char
  13      41         ?
index  element     char
  15      125         ?
```

**例 2:** 为**议论文异常**为

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// BitConverter.ToChar(Byte[], Int32);
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array of byte values.
        byte[] bytes = { 32, 0, 0, 42, 0, 65, 0, 125, 0,
                        197, 0, 168, 3, 41, 4, 125 };

        // Display the values of the myArr.
        Console.Write("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

        // print char value
        for (int index = 1; index < bytes.Length;
                            index = index + 2) {

            if (index == bytes.Length - 1) {
                Console.WriteLine();
                Console.WriteLine("startIndex equals the "+
                               "length of value minus 1.");
                char values = BitConverter.ToChar(bytes, index);
            }
            else {
                char values = BitConverter.ToChar(bytes, index);
                Console.WriteLine("index element     char");
                Console.WriteLine(" {0}     {1}      {2}",
                                index, bytes[index], values);
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

index  element     char
  1      0         
index  element     char
  3      42         *
index  element     char
  5      65         A
index  element     char
  7      125         }
index  element     char
  9      197         ?
index  element     char
  11      168         ?
index  element     char
  13      41         ?

startIndex equals the length of value minus 1.
Exception Thrown: System.ArgumentException
```

**例 3:** 为**argumentout of rangeexception**为

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// BitConverter.ToChar(Byte[], Int32);
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array of byte values.
        byte[] bytes = { 32, 0, 0, 42, 0, 65, 0, 125, 0,
                        197, 0, 168, 3, 41, 4, 125 };

        // Display the values of the myArr.
        Console.Write("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

        // print char value
        for (int index = 0; index < bytes.Length + 1;
                                 index = index + 2) {

            if (index == bytes.Length) {
                Console.WriteLine();
                Console.WriteLine("startIndex is greater than "+
                                "the length of value minus 1.");
                char values = BitConverter.ToChar(bytes, index);
            }
            else {
                char values = BitConverter.ToChar(bytes, index);
                Console.WriteLine("index element     char");
                Console.WriteLine(" {0}     {1}      {2}",
                                index, bytes[index], values);
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

index  element     char
  0      32          
index  element     char
  2      0         ?
index  element     char
  4      0         ?
index  element     char
  6      0         ?
index  element     char
  8      0         ?
index  element     char
  10      0         ?
index  element     char
  12      3         ?
index  element     char
  14      4         ?

startIndex is greater than the length of value minus 1.
Exception Thrown: System.ArgumentOutOfRangeException
```

**例 4:** 为 **ArgumentNullException** 为

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// BitConverter.ToChar(Byte[], Int32);
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

            char values = BitConverter.ToChar(bytes, 0);
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

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . bit converter . tochar？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.tochar?view=netframework-4.7.2)