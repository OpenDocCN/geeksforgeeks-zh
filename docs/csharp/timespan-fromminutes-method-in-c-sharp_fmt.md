# TimeSpan.FromMinutes() 方法在 C# 中

> 原文：[https://www.geeksforgeeks.org/timespan-fromminutes-method-in-c-sharp/](https://www.geeksforgeeks.org/timespan-fromminutes-method-in-c-sharp/)

此方法用于获取表示指定分钟数的 `TimeSpan`，其中规格精确到最接近的毫秒。

## 语法

```cs
public static TimeSpan FromMinutes(double value);
```

## 参数

- `value`：该参数指定分钟数，精确到最近的毫秒。

## 返回值

返回一个新的表示值的 `TimeSpan` 对象。

## 异常

- `OverflowException`：如果给定的 `double` 值小于最小可能值或大于最大可能值，或者该值为正无穷大或负无穷大。
- `ArgumentException`：如果 `value` 为 `NaN`。

## 示例

以下程序说明了 `TimeSpan.FromMinutes(Double)` 方法的使用：

### 例 1

```cs
// C# program to demonstrate the
// TimeSpan.FromMinutes(Double) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            TimeSpan interval = TimeSpan.FromMinutes(8.12345);
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
The Timespan is : 00:08:07.4070000
```

### 例 2：为 `OverflowException`

```cs
// C# program to demonstrate the
// TimeSpan.FromMinutes(Double) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            TimeSpan interval = TimeSpan.FromMinutes(Double.PositiveInfinity);
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

- [https://docs.microsoft.com/en-us/dotnet/api/system.timespan.fromminutes?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.timespan.fromminutes?view=netframework-4.7.2)