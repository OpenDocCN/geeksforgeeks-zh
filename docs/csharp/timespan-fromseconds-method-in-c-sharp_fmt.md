# TimeSpan.FromSeconds 方法 (C#)

> 原文：[https://www.geeksforgeeks.org/timespan-fromseconds-method-in-c-sharp/](https://www.geeksforgeeks.org/timespan-fromseconds-method-in-c-sharp/)

此方法用于获取表示指定秒数的时间跨度，精确到最接近的毫秒。

## 语法

```cs
public static TimeSpan FromSeconds(double value);
```

## 参数

- `value`：该参数指定秒数，精确到最近的毫秒。

## 返回值

返回一个新的表示值的 `TimeSpan` 对象。

## 异常

- `OverflowException`：当给定的 `double` 值小于最小可能值或大于最大可能值，或者值为正无穷大或负无穷大时。
- `ArgumentException`：当值为 `NaN` 时。

## 示例

以下程序说明了 `TimeSpan.FromSeconds(Double)` 方法的使用。

### 例 1

```cs
// C# program to demonstrate the
// TimeSpan.FromSeconds(Double)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            TimeSpan interval = TimeSpan.FromSeconds(0.43459);
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
The Timespan is : 00:00:00.4350000
```

### 例 2：针对 `OverflowException`

```cs
// C# program to demonstrate the
// TimeSpan.FromSeconds(Double)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            TimeSpan interval = TimeSpan.FromSeconds(Double.NegativeInfinity);
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

- [https://docs.microsoft.com/en-us/dotnet/api/system.timespan.fromseconds?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.timespan.fromseconds?view=netframework-4.7.2)