# C# BitConverter.ToInt32() 方法

> 原文：[`https://www.geeksforgeeks.org/c-sharp-bitconverter-toint32-method/`](https://www.geeksforgeeks.org/c-sharp-bitconverter-toint32-method/)

`BitConverter.ToInt32(Byte[], Int32)` 方法用于返回从字节数组中指定位置的四个字节转换而来的 32 位有符号整数。

## 语法

```cs
public static int ToInt32 (byte[] value, int startIndex);
```

## 参数

- `value`：是字节数组。
- `startIndex`：是数值内的起始位置。

## 返回值

这个方法返回一个 32 位有符号整数，由 `startIndex` 开始的四个字节组成。

## 例外

- `ArgumentException`：如果 `startIndex` 大于或等于 `value` 的长度减 3，并且小于或等于 `value` 的长度减 1。
- `ArgumentNullException`：如果 `value` 为空。
- `ArgumentOutOfRangeException`：如果 `startIndex` 小于零或大于 `value` 的长度减 1。

以下程序说明了 `BitConverter.ToInt32()` 方法的使用。

### 示例 1

```cs
// C# program to demonstrate
// BitConverter.ToInt32(Byte[], Int32);
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array
        // of byte values.
        byte[] bytes = {32, 0, 0, 42, 0,
                        65, 0, 125, 0, 197,
                        0, 168, 3, 41, 4,
                             125, 32 };

        // Display the values of the myArr.
        Console.Write("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

        // print char value
        Console.WriteLine("index     byte Array           int value");
        for (int index = 0; index < bytes.Length - 3;
                          index = index + 4) {

            int values = BitConverter.ToInt16(bytes, index);

            Console.WriteLine(" {0}     {1}         {2}",
             index, BitConverter.ToString(bytes, index,
                                       4), values);
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

**输出**

```cs
Initial Array: 32 0 0 42 0 65 0 125 0 197 0 168 3 41 4 125 32 

index      byte Array       int value
  0        20-00-00-2A         32
  4        00-41-00-7D         16640
  8        00-C5-00-A8         -15104
  12        03-29-04-7D         10499
```

### 示例 2：为 `ArgumentException` 示例

```cs
// C# program to demonstrate
// BitConverter.ToInt32(Byte[], Int32);
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array
        // of byte values.
        byte[] bytes = {32, 0, 0, 42, 0,
                        65, 0, 125, 0, 197,
                        0, 168, 3, 41, 4, 125};

        // Display the values of the myArr.
        Console.Write("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

        // print char value
        Console.WriteLine("index      element          int value");
        for (int index = 1; index < bytes.Length - 2;
                             index = index + 4) {

            if (index == bytes.Length - 3) {
                Console.WriteLine();
                Console.WriteLine("startIndex equals the "+
                           "length of value minus 3.");
                int values = BitConverter.ToInt32(bytes, index);
                Console.WriteLine("  {0}      {1}         {2}",
                 index, BitConverter.ToString(bytes, index, 4), values);
            }
            else {
                int values = BitConverter.ToInt32(bytes, index);
                Console.WriteLine("  {0}      {1}         {2}",
                 index, BitConverter.ToString(bytes, index, 4), values);
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

**输出**

```cs
Initial Array: 32 0 0 42 0 65 0 125 0 197 0 168 3 41 4 125 

initial Array in string: 20-00-00-2A-00-41-00-7D-00-C5-00-A8-03-29-04-7D 

index      element          int value
  1      00-00-2A-00         2752512
  5      41-00-7D-00         8192065
  9      C5-00-A8-03         61341893

startIndex equals the length of value minus 3.
Exception Thrown: System.ArgumentException
```

### 示例 3：为 `ArgumentOutOfRangeException` 示例

# C# BitConverter.ToInt32(Byte[], Int32) 方法示例

## 示例 1：基本用法与索引遍历

```cs
// C# program to demonstrate
// BitConverter.ToInt32(Byte[], Int32);
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array
        // of byte values.
        byte[] bytes = {32, 0, 0, 42, 0, 65,
                        0, 125, 0, 197, 0,
                        168, 3, 41, 4, 125};

        // Display the values of the myArr.
        Console.Write("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

        // print char value
        Console.WriteLine("index      element          int value");

        for (int index = 0; index < bytes.Length + 1;
                                index = index + 4) {

            if (index == bytes.Length) {
                Console.WriteLine();
                Console.WriteLine("startIndex is greater than "+
                                 "the length of value minus 1");
                int values = BitConverter.ToInt32(bytes, index);
                Console.WriteLine("  {0}      {1}         {2}",
                 index, BitConverter.ToString(bytes, index, 4), values);
            }
            else {
                int values = BitConverter.ToInt32(bytes, index);
                Console.WriteLine("  {0}      {1}         {2}",
                 index, BitConverter.ToString(bytes, index, 4), values);
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

index      element          int value
  0      20-00-00-2A         704643104
  4      00-41-00-7D         2097168640
  8      00-C5-00-A8         -1476344576
  12      03-29-04-7D         2097424643

startIndex is greater than the length of value minus 1
Exception Thrown: System.ArgumentOutOfRangeException
```

## 示例 2：处理 ArgumentNullException

```cs
// C# program to demonstrate
// BitConverter.ToInt32(Byte[], Int32);
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array of byte values.
        byte[] bytes = null;

        // get the int value

        int values = BitConverter.ToInt32(bytes, 0);
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

*   [https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.toint32?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.toint32?view=netframework-4.7.2)