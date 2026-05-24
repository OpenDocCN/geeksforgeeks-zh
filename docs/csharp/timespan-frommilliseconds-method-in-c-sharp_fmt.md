# TimeSpan.FromMilliseconds 方法 (C#)

> 原文：[https://www.geeksforgeeks.org/timespan-frommilliseconds-method-in-c-sharp/](https://www.geeksforgeeks.org/timespan-frommilliseconds-method-in-c-sharp/)

此方法用于获取表示指定毫秒数的 `TimeSpan`。

## 语法

```cs
public static TimeSpan FromMilliseconds(double value);
```

## 参数

- `value`：该参数指定毫秒数。

## 返回值

返回一个新的表示 `value` 的 `TimeSpan` 对象。

## 异常

- `OverflowException`：当给定的 `double` 值小于最小可能值或大于最大可能值，或者值为正无穷或负无穷时出现。
- `ArgumentException`：如果 `value` 等于 `NaN`。

以下程序说明了 `TimeSpan.FromMilliseconds(Double)` 方法的使用：

### 程序 1

```cs
// C# program to demonstrate the
// TimeSpan.FromMilliseconds(Double)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            TimeSpan interval = 
                TimeSpan.FromMilliseconds(8233567398261.2);

            Console.WriteLine("The Timespan is : {0}",
                              interval);
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
The Timespan is : 95295.22:03:18.2610000
```

### 程序 2：处理 `OverflowException`

```cs
// C# program to demonstrate the
// TimeSpan.FromMilliseconds(Double)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            TimeSpan interval = 
                TimeSpan.FromMilliseconds(Double.NegativeInfinity);

            Console.WriteLine("The Timespan is : {0}",
                              interval);
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

- [https://docs.microsoft.com/en-us/dotnet/api/system.timespan.frommilliseconds?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.timespan.frommilliseconds?view=netframework-4.7.2)