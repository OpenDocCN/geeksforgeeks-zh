# TimeSpan.Subtract 方法 (C#)

> 原文: [https://www.geeksforgeeks.org/timespan-subtract-method-in-c-sharp/](https://www.geeksforgeeks.org/timespan-subtract-method-in-c-sharp/)

此方法用于获取一个新的 `TimeSpan` 对象，该对象的值是指定的 `TimeSpan` 对象和此实例的差值。

## 语法

```cs
public TimeSpan Subtract(TimeSpan t);
```

## 参数

- **t**: 该参数指定要减去的时间间隔。

## 返回值

返回一个新的 `TimeSpan` 对象，其值为当前实例与 `t` 的值之差。

## 异常

当产生的时间跨度小于最小可能值或大于最大可能值时，该方法将给出 `OverflowException`。

## 示例

以下程序说明了 `TimeSpan.Subtract(TimeSpan)` 方法的使用：

### 示例 1

```cs
// C# program to demonstrate the
// TimeSpan.Subtract(TimeSpan) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating the TimeSpan object
            TimeSpan t1 = new TimeSpan(3, 22, 35, 33);
            TimeSpan t2 = new TimeSpan(1, 11, 15, 16);
            TimeSpan variable = t1.Subtract(t2);

            Console.WriteLine("The Timespan is : {0}",
                                            variable);
        }

        catch (OverflowException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```cs
The Timespan is : 2.11:20:17
```

### 示例 2 (溢出异常)

```cs
// C# program to demonstrate the
// TimeSpan.Subtract(TimeSpan) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // the TimeSpan object
            TimeSpan t1 = TimeSpan.MinValue;
            TimeSpan t2 = new TimeSpan(3, 22, 35, 33);
            TimeSpan variable = t1.Subtract(t2);

            Console.WriteLine("The Timespan is : {0}",
                                            variable);
        }

        catch (OverflowException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```cs
Exception Thrown: System.OverflowException
```

## 参考

- [https://docs.microsoft.com/en-us/dotnet/api/system.timespan.subtract?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.timespan.subtract?view=netframework-4.7.2)