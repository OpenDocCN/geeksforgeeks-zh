# DateTimeOffset.AddSeconds() 方法在 C# 中的应用

> 原文：[https://www.geeksforgeeks.org/datetimeoffset-addseconds-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-addseconds-method-in-c-sharp/)

此方法用于返回一个新的 `DateTimeOffset` 对象，该对象将指定数量的整数秒和小数秒添加到当前实例的值中。

### 语法
```csharp
public DateTimeOffset AddSeconds(double seconds);
```
这里，`seconds` 参数表示需要添加的整数和小数秒。该数字可以是负数或正数。

### 返回值
该方法返回一个 `DateTimeOffset` 对象，其值是当前 `DateTimeOffset` 对象表示的日期和时间与 `seconds` 参数表示的秒数之和。

### 异常
如果结果日期时间偏移值小于 `DateTimeOffset.MinValue` 或结果日期时间偏移值大于 `DateTimeOffset.MaxValue`，该方法将抛出 `ArgumentOutOfRangeException`。

以下程序说明了 `DateTimeOffset.AddSeconds(Double)` 方法的使用：

#### 例 1
```csharp
// C# program to demonstrate the
// DateTimeOffset.AddSeconds(Double)
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// creating object of  DateTimeOffset
            DateTimeOffset offset = new DateTimeOffset(2007,
                    6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

// adding a specified number of whole and
            // fractional seconds to the value of this
            // instance using AddSeconds() method
            DateTimeOffset value = offset.AddSeconds(10);

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
DateTimeOffset is 06/01/2007 07:55:10 -05:00
```

#### 例 2：`ArgumentOutOfRangeException` 示例
```csharp
// C# program to demonstrate the
// DateTimeOffset.AddSeconds(Double)
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// creating object of  DateTimeOffset
            DateTimeOffset offset = DateTimeOffset.MaxValue;

// adding a specified number of whole and
            // fractional seconds to the value of this
            // instance using AddSeconds() method
            DateTimeOffset value = offset.AddSeconds(10);

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

### 参考
*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.addseconds?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.addseconds?view=netframework-4.7.2)