# DateTimeOffset.AddYears() 方法在 C# 中

> 原文: [https://www.geeksforgeeks.org/datetimeoffset-addyears-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-addyears-method-in-c-sharp/)

此方法用于返回一个新的 `DateTimeOffset` 对象，该对象将指定的年数添加到当前实例的值中。

### 语法
```csharp
public DateTimeOffset AddYears(int years);
```
在这里，`years` 表示要添加的年数。该数字可以是负数或正数。

### 返回值
该方法返回一个对象，该对象的值是当前 `DateTimeOffset` 对象表示的日期和时间与 `years` 表示的年数之和。

### 异常
如果结果日期时间偏移值小于 `DateTimeOffset.MinValue` 或结果日期时间偏移值大于 `DateTimeOffset.MaxValue`，该方法将给出 `ArgumentOutOfRangeException`。

以下程序说明了 `DateTimeOffset.AddYears(Int32)` 方法的使用：

## 例 1

```csharp
// C# program to demonstrate the
// DateTimeOffset.AddYears(Int32)
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
            // fractional year to the value of this
            // instance using AddYears() method
            DateTimeOffset value = offset.AddYears(10);

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

**Output:**

```csharp
DateTimeOffset is 06/01/2017 07:55:00 -05:00
```

## 例 2: 为 `ArgumentOutOfRangeException`

```csharp
// C# program to demonstrate the
// DateTimeOffset.AddYears(Int32)
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
            // fractional year to the value of this
            // instance using AddYears() method
            DateTimeOffset value = offset.AddYears(10);

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

**Output:**

```csharp
Exception Thrown: System.ArgumentOutOfRangeException
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.addyears?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.addyears?view=netframework-4.7.2)