# 日期时间。C# 中的 FromBinary()方法

> 原文:[https://www . geesforgeks . org/datetime-from binary-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-frombinary-method-in-c-sharp/)

**日期时间。FromBinary(Int64)方法**用于反序列化 64 位二进制值，并重新创建原始序列化的 DateTime 对象。

> **语法:**public static DateTime from binary(长日期数据)；
> 这里，它采用 64 位有符号整数，在 2 位字段中编码 Kind 属性，在 62 位字段中编码 Ticks 属性。
> **返回值:**该方法返回一个对象，该对象相当于由 ToBinary()方法序列化的 DateTime 对象。
> **异常:**如果日期数据小于最小值或大于最大值，该方法将给出*参数异常*。

以下程序说明了*日期时间的使用。FromBinary(Int64)* 方法:
T3】例 1:

## c sharp . c sharp . c sharp . c sharp

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

**例 2:** 为*argumentout of rangeexception*为

## c sharp . c sharp . c sharp . c sharp

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

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . from binary？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.frombinary?view=netframework-4.7.2)