# TimeSpan.FromHours() 方法在 C# 中的应用

> 原文：[https://www.geeksforgeeks.org/timespan-fromhours-method-in-c-sharp/](https://www.geeksforgeeks.org/timespan-fromhours-method-in-c-sharp/)

此方法用于获取表示指定小时数的 `TimeSpan`，精确到最接近的毫秒。

## 语法
```cs
public static TimeSpan FromHours(double value);
```

## 参数
- `value`：该参数指定小时数，精确到最近的毫秒。

## 返回值
返回一个新的表示 `value` 的 `TimeSpan` 对象。

## 异常
- `OverflowException`：当给定的 `double` 值小于最小可能值或大于最大可能值，或者值为正无穷大或负无穷大时出现。
- `ArgumentException`：如果 `value` 等于 `NaN`。

## 示例
以下程序说明了 `TimeSpan.FromHours(Double)` 方法的使用。

### 程序 1
```cs
// C# program to demonstrate the
// TimeSpan.FromHours(Double) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            TimeSpan interval = TimeSpan.FromHours(12.3459);
            Console.WriteLine("The Timespan is : {0}", interval);
        }
        catch (OverflowException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```
**输出：**
```cs
The Timespan is : 12:20:45.2400000
```

### 程序 2：为 `OverflowException`
```cs
// C# program to demonstrate the
// TimeSpan.FromHours(Double) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            TimeSpan interval = TimeSpan.FromHours(Double.NegativeInfinity);
            Console.WriteLine("The Timespan is : {0}", interval);
        }
        catch (OverflowException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```
**输出：**
```cs
Exception Thrown: System.OverflowException
```

## 参考
- [https://docs.microsoft.com/en-us/dotnet/api/system.timespan.fromhours?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.timespan.fromhours?view=netframework-4.7.2)