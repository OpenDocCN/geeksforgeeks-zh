# DateTimeOffset.AddMinutes() 方法在 C# 中的应用

> 原文：[https://www.geeksforgeeks.org/datetimeoffset-addminutes-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-addminutes-method-in-c-sharp/)

此方法用于获取一个新的 `DateTimeOffset` 对象，该对象将指定数量的整数和分数分钟添加到当前实例的值中。

## 语法
```csharp
public DateTimeOffset AddMinutes(double minutes);
```
这里，`minutes` 参数表示需要添加的整分钟和分数分钟数。该数字可以是负数或正数。

## 返回值
返回一个 `DateTimeOffset` 对象，其值为当前 `DateTimeOffset` 对象表示的日期和时间与 `minutes` 参数表示的分钟数之和。

## 异常
如果结果日期时间偏移值小于 `DateTimeOffset.MinValue` 或结果日期时间偏移值大于 `DateTimeOffset.MaxValue`，该方法将给出 `ArgumentOutOfRangeException`。

以下程序说明了 `DateTimeOffset.AddMinutes(Double)` 方法的使用：

### 示例 1
```csharp
// C# program to demonstrate the
// DateTimeOffset.AddMinutes(Double)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTimeOffset
            DateTimeOffset offset = new DateTimeOffset(2007,
                     6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

            // adding a specified number of whole and
            // fractional minutes to the value of this
            // instance using AddMinutes() method
            DateTimeOffset value = offset.AddMinutes(10);

            // Display the time
            Console.WriteLine("DateTimeOffset is {0}", value);
        }

        catch (ArgumentOutOfRangeException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```
**输出：**
```csharp
DateTimeOffset is 06/01/2007 08:05:00 -05:00
```

### 示例 2：处理 `ArgumentOutOfRangeException`
```csharp
// C# program to demonstrate the
// DateTimeOffset.AddMinutes(Double)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTimeOffset
            DateTimeOffset offset = DateTimeOffset.MaxValue;

            // adding a specified number of whole and
            // fractional minutes to the value of this
            // instance using AddMinutes() method
            DateTimeOffset value = offset.AddMinutes(10);

            // Display the time
            Console.WriteLine("DateTimeOffset is {0}", value);
        }

        catch (ArgumentOutOfRangeException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```
**输出：**
```csharp
Exception Thrown: System.ArgumentOutOfRangeException
```

## 参考
*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.addminutes?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.addminutes?view=netframework-4.7.2)