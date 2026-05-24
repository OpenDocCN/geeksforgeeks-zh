# DateTime.FromBinary() 方法在 C# 中

> 原文: [https://www.geeksforgeeks.org/datetime-frombinary-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-frombinary-method-in-c-sharp/)

`DateTime.FromBinary(Int64)` 方法用于反序列化 64 位二进制值，并重新创建原始序列化的 `DateTime` 对象。

## 语法

```cs
public static DateTime FromBinary(long dateData);
```

这里，它采用 64 位有符号整数，在 2 位字段中编码 `Kind` 属性，在 62 位字段中编码 `Ticks` 属性。

## 返回值

该方法返回一个对象，该对象相当于由 `ToBinary()` 方法序列化的 `DateTime` 对象。

## 异常

如果 `dateData` 小于 `MinValue` 或大于 `MaxValue`，该方法将给出 `ArgumentOutOfRangeException`。

以下程序说明了 `DateTime.FromBinary(Int64)` 方法的使用：

### 示例 1

```cs
// C# program to demonstrate the
// DateTime.FromBinary(Int64) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            // creating object of DateTime
            DateTime date1 = new DateTime(2010, 1, 1,
                                           8, 0, 15);

            // getting a 64-bit signed integer
            // using ToBinary() method
            long binLocal = date1.ToBinary();

            // converting 64-bit into DateTime format
            // using FromBinary() method
            DateTime date2 = DateTime.FromBinary(binLocal);

            // Display the date1
            System.Console.WriteLine("DateTime before "
                     + "operation: {0:y} {0:dd}",date1);

            // Display the date2
            System.Console.WriteLine("\nDateTime after"
                  + " operation: {0:y} {0:dd}", date2);
        }
        catch (ArgumentOutOfRangeException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```cs
DateTime before operation: 2010 January 01

DateTime after operation: 2010 January 01
```

### 示例 2

为 `ArgumentOutOfRangeException` 的示例：

```cs
// C# program to demonstrate the
// DateTime.FromBinary() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            // converting 64-bit into DateTime format
            // using FromBinary() method
            DateTime date = DateTime.FromBinary(-100000000000000000);

            // Display the date
            System.Console.WriteLine("\nDateTime: + {0:y} {0:dd} ", date);
        }
        catch (ArgumentException e)
        {
            Console.WriteLine("The resulting dateData"
                     + " is less than the MinValue ");

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```cs
The resulting dateData is less than the MinValue 
Exception Thrown: System.ArgumentException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetime.frombinary?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.frombinary?view=netframework-4.7.2)