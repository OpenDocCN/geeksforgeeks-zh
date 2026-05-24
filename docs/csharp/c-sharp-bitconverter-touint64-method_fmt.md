# C# BitConverter.ToUInt64 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-bitconverter-touint64-method/](https://www.geeksforgeeks.org/c-sharp-bitconverter-touint64-method/)

此方法用于返回从字节数组中指定位置的八个字节转换而来的 64 位无符号整数。

## 语法

```cs
public static ulong ToUInt64 (byte[] value, int startIndex);
```

## 参数

- `value`：是字节数组。
- `startIndex`：是 `value` 内的起始位置。

## 返回值

该方法返回一个 64 位无符号整数，由从 `startIndex` 的八个字节组成。

## 异常

- `ArgumentException`：如果 `startIndex` 大于等于 `value` 的长度减 7，小于等于 `value` 的长度减 1。
- `ArgumentNullException`：如果 `value` 为空。
- `ArgumentOutOfRangeException`：如果 `startIndex` 小于零或者大于 `value` 的长度减 1。

以下程序说明了 `BitConverter.ToUInt64` 方法的使用：

## 示例 1

```cs
// C# program to demonstrate
// BitConverter.ToUInt64(Byte[], Int32);
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
                      168, 3, 41, 4, 125,32};

// Display the values of the myArr.
        Console.Write("Initial Array: ");

// calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

// print char value
        Console.WriteLine("index         byte Array"+
                          "             ulong value");

for (int index = 0; index < bytes.Length - 7;
                            index = index + 8) {

ulong values = BitConverter.ToUInt64(bytes, index);

Console.WriteLine(" {0}     {1}     {2}", index, 
                         BitConverter.ToString(bytes, 
                                  index, 8), values);
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

**输出：**

```cs
Initial Array: 32 0 0 42 0 65 0 125 0 197 0 168 3 41 4 125 32

index         byte Array             ulong value
 0     20-00-00-2A-00-41-00-7D     9007270723701440544
 8     00-C5-00-A8-03-29-04-7D     9008370250328098048
```

## 示例 2：适用于 `ArgumentException`

```cs
// C# program to demonstrate
// BitConverter.ToUInt64(Byte[], Int32);
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
                      168, 3, 41, 4, 125,32};

// Display the values of the myArr.
        Console.Write("Initial Array: ");

// calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

// print char value
        Console.WriteLine("index           element"+
                    "                 ulong value");

for (int index = 0; index < bytes.Length + 1;
                            index = index + 8) {

if (index == bytes.Length) {

Console.WriteLine();
                Console.WriteLine("startindex is {0} which is greater than "
                               + "the length of Array minus 1.", index);

ulong values = BitConverter.ToUInt64(bytes, index);

Console.WriteLine("  {0}      {1}      {2}", index,
                   BitConverter.ToString(bytes, index, 8), values);
            }

else {
                ulong values = BitConverter.ToUInt64(bytes, index);

Console.WriteLine("  {0}      {1}      {2}", index,
                   BitConverter.ToString(bytes, index, 8), values);
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
    Console.WriteLine("intial Array in string: {0} ",
                      BitConverter.ToString(myArr));
    Console.WriteLine();
}
}
```

**输出：**

```cs
Initial Array: 32 0 0 42 0 65 0 125 0 197 0 168 3 41 4 125 32

intial Array in string: 20-00-00-2A-00-41-00-7D-00-C5-00-A8-03-29-04-7D-20

index           element                 ulong value
  0      20-00-00-2A-00-41-00-7D      9007270723701440544
  8      00-C5-00-A8-03-29-04-7D      9008370250328098048
Exception Thrown: System.ArgumentException
```

## 示例 3：适用于 `ArgumentNullException`

```cs
// C# program to demonstrate
// BitConverter.ToUInt64(Byte[], Int32);
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

ulong values = BitConverter.ToUInt64(bytes, 0);
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

**输出：**

```cs
Exception Thrown: System.ArgumentNullException
```

## 参考

- [https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.touint64?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.touint64?view=netframework-4.7.2)