# DateTime.FromFileTimeUtc() 方法在 C# 中

> 原文：[https://www.geeksforgeeks.org/datetime-fromfiletimeutc-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-fromfiletimeutc-method-in-c-sharp/)

`DateTime.FromFileTimeUtc(Int64)` 方法用于将指定的 Windows 文件时间转换为等效的 UTC 时间。

## 语法

```cs
public static DateTime FromFileTimeUtc (long fileTime);
```

这里，`fileTime` 参数是一个用刻度表示的 Windows 文件时间。

## 返回值

该方法返回一个 `DateTime` 对象，该对象表示 `fileTime` 参数所表示的日期和时间的 UTC 等价物。

## 异常

如果 `fileTime` 小于 0 或代表大于最大值的时间，此方法将给出 `ArgumentOutOfRangeException`。

## 示例

以下程序说明了 `DateTime.FromFileTimeUtc()` 方法的使用：

### 示例 1

```cs
// C# program to demonstrate the
// DateTime.FromFileTimeUtc(Int64) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // converting 2500000000000 file
            // time represented in ticks
            // into UTC Time format
            // using FromFileTimeUtc() method
            DateTime date2 = DateTime.FromFileTimeUtc(2500000000000);

            // Display the date2
            System.Console.WriteLine("DateTime after"
                + " operation: {0:y} {0:dd}", date2);

        }

        catch (ArgumentOutOfRangeException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出：**

```cs
DateTime after operation: 1601 January 03
```

### 示例 2

此示例演示了 `ArgumentOutOfRangeException` 异常。

```cs
// C# program to demonstrate the
// DateTime.FromFileTimeUtc(Int64) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // converting -1 file time
            // represented in ticks
            // into DateTime format
            // using FromFileTimeUtc() method
            DateTime date2 = DateTime.FromFileTimeUtc(-1);

            // Display the date2
            System.Console.WriteLine("\nDateTime after"
                  + " operation: {0:y} {0:dd}", date2);

        }

        catch (ArgumentOutOfRangeException e)
        {
            Console.WriteLine("fileTime is less than 0 ");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出：**

```cs
fileTime is less than 0 
Exception Thrown: System.ArgumentOutOfRangeException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetime.fromfiletimeutc?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.fromfiletimeutc?view=netframework-4.7.2)